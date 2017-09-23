---
title: UDF_EliminarConcomitancia
category: Funções Customizadas
order: 1
---
{% highlight javascript linenos %}
/**
* Elimina concomitância em matriz de períodos de contribuição, segundo os pesos relativos fornecidos.
*
* @param {array} periodos Matriz com os períodos de contribuição. 
*  As duas primeiras colunas devem corresponder às datas inicial e final. A última, aos pesos relativos.
* @return {array} A matriz com os períodos ajustados e ordenados após a eliminação da concomitância.
*
* @customfunction
*/
function jef_ELIMINAR_CONCOMITANCIA(periodos) {
  
  periodos = Utilidades.validarPeriodos(periodos);
  
  if (periodos.length === 1) { // se tem apenas uma linha, certamente não há conflito
    return periodos;
  }  
  
  periodos = periodos.sort(Utilidades.ordenarPorDataInicial);
  
  var contador = 0;
  
  do { 
    var acrescimos = [];
    var conflitoDetectado = false;
    var maxIdx = periodos.length - 1;
    contador += 1;
    
    for (var i = 0; i < maxIdx; i++) {
      
      if (periodos[i] && periodos[i + 1]) {
        
        var dataInicialPrimeiro = new Date(periodos[i][0].getTime());
        var dataFinalPrimeiro = new Date(periodos[i][1].getTime());
        var pesoPrimeiro = periodos[i][periodos[i].length - 1];
        var dataInicialSegundo = new Date(periodos[i + 1][0].getTime());
        var dataFinalSegundo = new Date(periodos[i + 1][1].getTime());
        var pesoSegundo = periodos[i + 1][periodos[i + 1].length - 1];
        
        var conflito = Utilidades.datasSobrepostas(dataInicialPrimeiro, dataFinalPrimeiro, dataInicialSegundo, dataFinalSegundo);
        
        if (conflito) {
          if (pesoPrimeiro >= pesoSegundo) {
            if (dataFinalSegundo > dataFinalPrimeiro) {
              periodos[i + 1][0] = Utilidades.diaSeguinte(dataFinalPrimeiro)
            } else {
              periodos[i + 1] = null;
            }
          } else {
            if (dataInicialPrimeiro === dataInicialSegundo && dataFinalPrimeiro <= dataFinalSegundo) {
              periodos[i] = null;
            } else {
              if (dataInicialPrimeiro < dataInicialSegundo) {
                periodos[i][1] = Utilidades.diaAnterior(dataInicialSegundo);
              }
              if (dataFinalPrimeiro > dataFinalSegundo) {
                acrescimos.push(Utilidades.copiarMatriz(periodos[i]));
                acrescimos[acrescimos.length - 1][0] = Utilidades.diaSeguinte(dataFinalSegundo);
                acrescimos[acrescimos.length - 1][1] = dataFinalPrimeiro;
              }
            }
          }
        }
        conflitoDetectado = conflitoDetectado || conflito;
      }
    }
    
    if (conflitoDetectado && acrescimos.length > 0) {
      acrescimos.forEach(function(acrescimo) {
        periodos.push(acrescimo);
      });
    }
    
    periodos = periodos.filter(Utilidades.compactarMatriz).sort(Utilidades.ordenarPorDataInicial);
    
    if (contador > 1000) {
      throw new Error('Falha no programa. Loop infinito.');
    }
    
  } while (acrescimos.length > 0 || conflitoDetectado);
  
  return periodos;
}
{% endhighlight %}