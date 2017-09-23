---
title: UDF_EstabelecerMarcosTemporais
category: Funções Customizadas
order: 2
---
{% highlight javascript linenos %}
/**
* Ajusta períodos de contribuição utilizando os marcos temporais fornecidos.
*
* @param {array} periodos Matriz com os períodos de contribuição. 
*  As duas primeiras colunas devem corresponder às datas inicial e final.
* @param {array} marcosTemporais Matriz de uma só coluna contendo todos os marcos temporais.
* @return {array} A matriz com os períodos ajustados.
*
* @customfunction
*/
function jef_ESTABELECER_MARCOS_TEMPORAIS(periodos, marcosTemporais) {
  
  marcosTemporais = Utilidades.validarMarcosTemporais(marcosTemporais);
  if (marcosTemporais.length === 0) {
    return periodos;
  }
  
  periodos = Utilidades.validarPeriodos(periodos);
  periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
  
  var contador = 0;
  
  do { 
    var acrescimos = [];
    contador += 1;
    
    periodos.forEach(function(periodo) {
      marcosTemporais.forEach(function(marcoTemporal) {
        if (Utilidades.incluiMarcoTemporal(periodo[0], periodo[1], marcoTemporal)) {
          var novoPeriodo = Utilidades.copiarMatriz(periodo);
          periodo[1] = Utilidades.diaAnterior(marcoTemporal);
          novoPeriodo[0] = marcoTemporal; 
          acrescimos.push(novoPeriodo);
        }
      });
    });
    
    if (acrescimos.length > 0) {
      acrescimos.forEach(function(acrescimo) {
        periodos.push(acrescimo);
      });
    }
    
    periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
    
    if (contador > 1000) {
      throw new Error('Falha no programa. Loop infinito.');
    }
    
  } while (acrescimos.length > 0);
  
  return periodos.sort(Utilidades.ordenarPorDataInicial);
}
{% endhighlight %}