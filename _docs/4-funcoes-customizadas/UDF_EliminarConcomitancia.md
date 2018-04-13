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
*  Disposição das colunas:
*  a) as duas primeiras, devem corresponder às datas inicial e final;
*  b) a penúltima, deve trazer o peso relativo (número); 
*  c) a última, deve trazer valor booleano indicando se o período deve prevalecer sobre os demais, independentemente do peso.
*  As colunas intermediárias podem trazer qualquer tipo de informação adicional.
* @return {array} A matriz com os períodos ajustados e ordenados após a eliminação da concomitância.
*
* @customfunction
*
* Alterado em 14/09/2017 - Comparação entre datas deve ser feita com uso de valueOf() ou getTime()
* Alterado em 20/10/2017 - Corrigida a omissão quanto à hipótese em que as datas iniciais são iguais, 
*  mas a data final do primeiro supera a do segundo (nos casos em que o segundo tem maior peso).
* Alterado em 10/11/2017 - Incluída a variável de "prioridade", que permite fazer um período prevalecer
*  sobre os demais, independentemente de seu peso.
*
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
        var pesoPrimeiro = periodos[i][periodos[i].length - 2];
        var prioridadePrimeiro = periodos[i][periodos[i].length - 1];
        var dataInicialSegundo = new Date(periodos[i + 1][0].getTime());
        var dataFinalSegundo = new Date(periodos[i + 1][1].getTime());
        var pesoSegundo = periodos[i + 1][periodos[i + 1].length - 2];
        var prioridadeSegundo = periodos[i + 1][periodos[i + 1].length - 1];
        
        var conflito = Utilidades.datasSobrepostas(dataInicialPrimeiro, dataFinalPrimeiro, dataInicialSegundo, dataFinalSegundo);

        if (conflito) {
          if ((prioridadePrimeiro === prioridadeSegundo && pesoPrimeiro >= pesoSegundo) || prioridadePrimeiro) {
            if (dataFinalSegundo.valueOf() > dataFinalPrimeiro.valueOf()) { // As datas devem ser sempre comparadas com valueOf() ou getTime()
              periodos[i + 1][0] = Utilidades.diaSeguinte(dataFinalPrimeiro)
            } else {
              periodos[i + 1] = null;
            }
          } else {
            if (dataInicialPrimeiro.valueOf() === dataInicialSegundo.valueOf()) {
              
              if (dataFinalPrimeiro.valueOf() <= dataFinalSegundo.valueOf()) {
                periodos[i] = null;
              } else {
                periodos[i][0] = Utilidades.diaSeguinte(dataFinalSegundo) // Hipótese introduzida com a alteração de 20/10/2017
              }
              
            } else {
              if (dataInicialPrimeiro.valueOf() === dataInicialSegundo.valueOf()) {
                periodos[i][1] = Utilidades.diaAnterior(dataInicialSegundo);
              }
              if (dataInicialPrimeiro.valueOf() < dataInicialSegundo.valueOf()) {
                periodos[i][1] = Utilidades.diaAnterior(dataInicialSegundo);
              }
              if (dataFinalPrimeiro.valueOf() > dataFinalSegundo.valueOf()) {
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