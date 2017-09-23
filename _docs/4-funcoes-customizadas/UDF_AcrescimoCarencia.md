---
title: UDF_AcrescimoCarencia
category: Funções Customizadas
order: 0
---
{% highlight javascript linenos %}
/**
* Calcula acréscimo previsto no art. 3º da Lei 11.718/2008.
*
* @param {array} periodos Matriz com os períodos de contribuição. As duas primeiras colunas devem corresponder às datas inicial e final.
* @param {boolean} aplicacaoRetroativa Determina se o cálculo deve abranger períodos anteriores a 01/01/2011.
* @return {array} A matriz com os acréscimos por período.
*
* @customfunction
*/
function jef_CALCULAR_ACRESCIMOS_LEI_11718(periodos, aplicacaoRetroativa) {
  
  periodos = Utilidades.validarPeriodos(periodos);
  
  var multiplicador = function(ano) {
    if (ano <= 2010) {
      return aplicacaoRetroativa ? 2 : 0;
    } else if (ano <= 2015) {
      return 2;
    } else if (ano <= 2020) {
      return 1;
    } else {
      return 0;
    }
  };
  
  var contribuicoes = Object.create(null);
  
  periodos.forEach(function(periodo) {
    
    var anoInicial = Utilidades.ano(periodo[0]);
    var mesInicial = Utilidades.mes(periodo[0]);
    var anoFinal = Utilidades.ano(periodo[1]);
    var mesFinal = Utilidades.mes(periodo[1]);

    contribuicoes[anoInicial] = contribuicoes[anoInicial] || [];
    contribuicoes[anoFinal] = contribuicoes[anoFinal] || [];
    
    if (anoInicial === anoFinal) {
      for (var i = mesInicial; i <= mesFinal; i++) {
        contribuicoes[anoInicial].push(i);
      }
    } else {
      for (var i = mesInicial; i <= 12; i++) {
        contribuicoes[anoInicial].push(i);
      }
      for (var i = 1; i <= mesFinal; i++) {
        contribuicoes[anoFinal].push(i);
      }
    }
  });
  
  Object.keys(contribuicoes).forEach(function(key) {
    var arr = [];
    for (var i = 0, l = contribuicoes[key].length; i < l; i++) {
      if (arr.indexOf(contribuicoes[key][i]) < 0) {
        arr.push(contribuicoes[key][i])
      }
    }
    contribuicoes[key] = arr;
  });
  
  var acrescimos = periodos.map(function(periodo, idx) {
    
    var anoInicial = Utilidades.ano(periodo[0]);
    var mesInicial = Utilidades.mes(periodo[0]);
    var anoFinal = Utilidades.ano(periodo[1]);
    var mesFinal = Utilidades.mes(periodo[1]);
    
    if (idx > 0 && anoInicial === Utilidades.ano(periodos[idx - 1][1]) && mesInicial === Utilidades.mes(periodos[idx - 1][1])) {
      var ajuste = -1;
    } else {
      var ajuste = 0;
    }
    
    if (anoInicial === anoFinal) {
      var acrescimoInicial = (mesFinal - mesInicial + 1 + ajuste) * multiplicador(anoInicial);
      var acrescimoFinal = 0;
      var disponivelInicial = 12 - contribuicoes[anoInicial].length;
      var acrescimoInicial = Math.min(acrescimoInicial, disponivelInicial);
      if (acrescimoInicial > 0) {
        for (var i = 1; i <= acrescimoInicial; i++) {
          contribuicoes[anoInicial].push(1);
        }
      }
    } else {
      var acrescimoInicial = (12 - mesInicial + 1 + ajuste) * multiplicador(anoInicial);
      var disponivelInicial = 12 - contribuicoes[anoInicial].length;
      var acrescimoInicial = Math.min(acrescimoInicial, disponivelInicial);
      if (acrescimoInicial > 0) {
        for (var i = 1; i <= acrescimoInicial; i++) {
          contribuicoes[anoInicial].push(1);
        }
      }
      var acrescimoFinal = mesFinal * multiplicador(anoFinal);
      var disponivelFinal = 12 - contribuicoes[anoFinal].length;
      var acrescimoFinal = Math.min(acrescimoFinal, disponivelFinal);
      if (acrescimoFinal > 0) {
        for (var i = 1; i <= acrescimoFinal; i++) {
          contribuicoes[anoFinal].push(1);
        }
      }
    }
    
    return Math.max(acrescimoInicial + acrescimoFinal, 0);
  });
  
  return acrescimos;
}
{% endhighlight %}