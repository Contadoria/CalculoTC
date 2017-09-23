---
title: UDFs_Comuns
category: Funções Customizadas
order: 3
---
{% highlight javascript linenos %}
var Utilidades = (function(utils) {

  utils.datasSobrepostas = function(inicialPrimeiro, finalPrimeiro, inicialSegundo, finalSegundo) {
    return (inicialPrimeiro <= finalSegundo) && (finalPrimeiro >= inicialSegundo);
  };

  utils.incluiMarcoTemporal = function(dataInicial, dataFinal, marco) {
    return marco > dataInicial && marco <= dataFinal;
  };
  
  utils.ordenarPorDataInicial = function(linha1, linha2) {
    return linha1[0] - linha2[0];
  };
  
  utils.compactarMatriz = function(linha) {
    return linha !== null;
  };

  // https://toddmotto.com/understanding-javascript-types-and-reliable-type-checking/
  utils.isDate = function(elem) {
    return Object.prototype.toString.call(elem).slice(8, -1) === 'Date';
  };
  
  utils.diaSeguinte = function(d) {
    var novaData = new Date(d.getTime());
    novaData.setDate(d.getDate() + 1);
    return novaData;
  };

  utils.diaAnterior = function(d) {
    var novaData = new Date(d.getTime());
    novaData.setDate(d.getDate() - 1);
    return novaData;
  };
  
  utils.ano = function(d) {
    return parseInt(Utilities.formatDate(d, 'UTC', 'yyyy'), 10);
  };
  
  utils.mes = function(d) {
    return parseInt(Utilities.formatDate(d, 'UTC', 'MM'), 10);
  };
  
  utils.copiarMatriz = function(arr) {
    return arr.map(function(item) {
      return item;
    });
  };
  
  utils.validarPeriodos = function(periodos) {
    
    if (!Array.isArray(periodos)) { 
      throw new Error('Dado de entrada "periodos" não é matriz.'); 
    }
    
    periodos = periodos.filter(function(periodo) {
      return periodo[0] !== "" && periodo[1] !== "";
    });
    
    periodos.forEach(function(periodo, idx) {
      if (!utils.isDate(periodo[0]) || !utils.isDate(periodo[1])) {
        throw new Error('A linha ' + (idx + 1) + ' da matriz fornecida contém uma data inválida.');
      }
      if (periodo[0] > periodo[1]) {
        throw new Error('Na linha ' + (idx + 1) + ' da matriz fornecida a data inicial é maior que a final.');
      }
    });
    
    return periodos;
  };
  
  utils.validarMarcosTemporais = function(marcosTemporais) {

    if (!Array.isArray(marcosTemporais)) { 
      throw new Error('Dado de entrada "marcosTemporais" não é matriz.'); 
    }
    
    marcosTemporais = marcosTemporais.map(function(linha) {
      return linha[0];
    }).filter(function(marcoTemporal) {
      return utils.isDate(marcoTemporal);
    }).sort(function(data1, data2) {
      return data1 - data2;
    });
    
    return marcosTemporais;
  };
  
  return utils;

})(Utilidades || Object.create(null));


{% endhighlight %}