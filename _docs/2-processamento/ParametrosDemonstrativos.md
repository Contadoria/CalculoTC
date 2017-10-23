---
title: ParametrosDemonstrativos
category: Processamento
order: 2
---

##### **DadosObrigatoriosFaltantes** `B28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(LEN(Sexo)>0;"";"Sexo#")& IF(ISNUMBER(DataNascimento);"";"Nascimento#")&IF(ISNUMBER(Especie);"";"Espécie#")&IF(ISNUMBER(DER);"";"DER#"){% endhighlight %}


~~~
0.###############
~~~


> Texto em branco para utilização nos demonstrativos quando não há dados obrigatórios preenchidos

* * *

##### **ObservacoesPeriodosAdicionados** `B23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=JOIN(CHAR(10);FILTER(OFFSET(ObservacoesTCAdicionadoDemonstrativo;1;0);OFFSET(ObservacoesTCAdicionadoDemonstrativo;1;0)<>"")){% endhighlight %}


~~~
0.###############
~~~


> Observações dos períodos adicionados para demonstrativo

* * *

##### **ObservacoesPeriodosDiscriminados** `B20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=JOIN(CHAR(10);FILTER(OFFSET(ObservacoesTCDiscriminadoDemonstrativo;1;0);OFFSET(ObservacoesTCDiscriminadoDemonstrativo;1;0)<>"")){% endhighlight %}


~~~
0.###############
~~~


> Observações dos períodos discriminados para demonstrativo

* * *

##### **TemPeriodosAdicionados** `D23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=NOT(NOT(SUM(ARRAYFORMULA(ISNUMBER(AnosTCAdicionadoDemonstrativo)*ISNUMBER(MesesTCAdicionadoDemonstrativo)*ISNUMBER(COUNTA(DiasTCAdicionadoDemonstrativo)))))){% endhighlight %}


~~~
0.###############
~~~


> Verificação se há períodos adicionados (para demonstrativo)

* * *

##### **TextoAnosDER** `L5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(AnosDER;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até DER (para demonstrativo)

* * *

##### **TextoAnosDERReafirmada1** `N5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);TEXT(AnosDERReafirmada1;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até primeira data reafirmada (para demonstrativo)

* * *

##### **TextoAnosDERReafirmada2** `P5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);TEXT(AnosDERReafirmada2;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até segunda data reafirmada (para demonstrativo)

* * *

##### **TextoAnosDPE** `B5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(AnosDPE;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até DPE (para demonstrativo)

* * *

##### **TextoAnosDPL** `J5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(AnosDPL;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até DPL (para demonstrativo)

* * *

##### **TextoAnosFaltantesComPedagio** `F5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(AnosFaltantesComPedagio;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos faltantes, considerado o pedágio (para demonstrativo)

* * *

##### **TextoAnosPedagio** `D5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(AnosPedagio;"0");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos de pedágio a ser cumprido (para demonstrativo)

* * *

##### **TextoAnosTCMinimo** `H5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(AnosTCMinimo;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos necessários para cumprimento do pedágio (para demonstrativo)

* * *

##### **TextoCarenciaDER** `L11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(CarenciaDER;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à carência apurada até DER (para demonstrativo)

* * *

##### **TextoCarenciaDERReafirmada1** `N11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);TEXT(CarenciaDERReafirmada1;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à carência apurada até primeira data reafirmada (para demonstrativo)

* * *

##### **TextoCarenciaDERReafirmada2** `P11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);TEXT(CarenciaDERReafirmada2;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à carência apurada até segunda data reafirmada (para demonstrativo)

* * *

##### **TextoCarenciaDPE** `B11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(CarenciaDPE;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à carência apurada até DPE (para demonstrativo)

* * *

##### **TextoCarenciaDPL** `J11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(CarenciaDPL;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à carência apurada até DPL (para demonstrativo)

* * *

##### **TextoCarenciaPedagio** `D11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoCarenciaTCMinimo** `H11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoCarenciaTempoFaltante** `F11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoCoeficienteDER** `L13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(DireitoAoBeneficioDER;TEXT(CoeficienteDER;"0%");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao coeficiente apurado na DER (para demonstrativo)

* * *

##### **TextoCoeficienteDERReafirmada1** `N13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);IF(DireitoAoBeneficioDERReafirmada1;TEXT(CoeficienteDERReafirmada1;"0%");" ");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao coeficiente apurado na data da primeira reafirmação (para demonstrativo)

* * *

##### **TextoCoeficienteDERReafirmada2** `P13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);IF(DireitoAoBeneficioDERReafirmada2;TEXT(CoeficienteDERReafirmada2;"0%");" ");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao coeficiente apurado na data da segunda reafirmação (para demonstrativo)

* * *

##### **TextoCoeficienteDPE** `B13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(DireitoAoBeneficioDPE;TEXT(CoeficienteDPE;"0%");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao coeficiente apurado na DPE (para demonstrativo)

* * *

##### **TextoCoeficienteDPL** `J13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(DireitoAoBeneficioDPL;TEXT(CoeficienteDPL;"0%");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao coeficiente apurado na DPL (para demonstrativo)

* * *

##### **TextoCoeficientePedagio** `D13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoCoeficienteTCMinimo** `H13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoCoeficienteTempoFaltante** `F13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoDER** `L3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&TEXT(DER;"dd/mm/yyyy")&" (DER)"{% endhighlight %}


~~~
0.###############
~~~


> Texto referente à data do requerimento administrativo (para demonstrativo)

* * *

##### **TextoDERReafirmada1** `N3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);CHAR(9)&TEXT(DERReafirmada1;"dd/mm/yyyy")&" ("&RotuloDERReafirmada1&")";""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à data da primeira data reafirmada (para demonstrativo)

* * *

##### **TextoDERReafirmada2** `P3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);CHAR(9)&TEXT(DERReafirmada2;"dd/mm/yyyy")&" ("&RotuloDERReafirmada2&")";""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente à data da segunda data reafirmada (para demonstrativo)

* * *

##### **TextoDPE** `B3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&TEXT(DPE;"dd/mm/yyyy")&" (DPE)"{% endhighlight %}


~~~
0.###############
~~~


> Texto referente à data da publicação da Emenda Constitucional nº 20 de 1.998 (para demonstrativo)

* * *

##### **TextoDPL** `J3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&TEXT(DPL;"dd/mm/yyyy")&" (DPL)"{% endhighlight %}


~~~
0.###############
~~~


> Texto referente à data da publicação da Lei 9.876/99 (para demonstrativo)

* * *

##### **TextoDiasDER** `L9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(DiasDER;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias apurados até DER (para demonstrativo)

* * *

##### **TextoDiasDERReafirmada1** `N9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);TEXT(DiasDERReafirmada1;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias apurados até primeira data reafirmada (para demonstrativo)

* * *

##### **TextoDiasDERReafirmada2** `P9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);TEXT(DiasDERReafirmada2;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias apurados até segunda data reafirmada (para demonstrativo)

* * *

##### **TextoDiasDPE** `B9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(DiasDPE;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias apurados até DPE (para demonstrativo)

* * *

##### **TextoDiasDPL** `J9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(DiasDPL;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos anos apurados até DPL (para demonstrativo)

* * *

##### **TextoDiasFaltantesComPedagio** `F9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(DiasFaltantesPedagio;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias faltantes, considerado o pedágio (para demonstrativo)

* * *

##### **TextoDiasPedagio** `D9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(DiasPedagio;"0");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias de pedágio a ser cumprido (para demonstrativo)

* * *

##### **TextoDiasTCMinimo** `H9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(DiasTCMinimo;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos dias necessários para cumprimento do pedágio (para demonstrativo)

* * *

##### **TextoIdadeDER** `L15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(IdadeDER;"0.00"){% endhighlight %}


~~~
0.###############
~~~


> Idade na DER (para demonstrativo)

* * *

##### **TextoIdadeDERReafirmada1** `N15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);TEXT(IdadeDERReafirmada1;"0.00");""){% endhighlight %}


~~~
0.###############
~~~


> Idade na data da primeira reafirmação (para demonstrativo)

* * *

##### **TextoIdadeDERReafirmada2** `P15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);TEXT(IdadeDERReafirmada2;"0.00");""){% endhighlight %}


~~~
0.###############
~~~


> Idade na data da segunda reafirmação (para demonstrativo)

* * *

##### **TextoIdadeDPE** `B15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Idade na DPE (para demonstrativo)

* * *

##### **TextoIdadeDPL** `J15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(IdadeDPL;"0.00"){% endhighlight %}


~~~
0.###############
~~~


> Idade na DPL (para demonstrativo)

* * *

##### **TextoIdadePedagio** `D15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoIdadeTCMinimo** `H15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoIdadeTempoFaltante** `F15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoMesesDER** `L7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(MesesDER;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses apurados até DER (para demonstrativo)

* * *

##### **TextoMesesDERReafirmada1** `N7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);TEXT(MesesDERReafirmada1;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses apurados até primeira data reafirmada (para demonstrativo)

* * *

##### **TextoMesesDERReafirmada2** `P7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);TEXT(MesesDERReafirmada2;"0");""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses apurados até segunda data reafirmada (para demonstrativo)

* * *

##### **TextoMesesDPE** `B7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(MesesDPE;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses apurados até DPE (para demonstrativo)

* * *

##### **TextoMesesDPL** `J7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TEXT(MesesDPL;"0"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses apurados até DPL (para demonstrativo)

* * *

##### **TextoMesesFaltantesComPedagio** `F7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(MesesFaltantesComPedagio;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses faltantes, considerado o pedágio (para demonstrativo)

* * *

##### **TextoMesesPedagio** `D7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(MesesPedagio;"0");" "){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses de pedágio a ser cumprido (para demonstrativo)

* * *

##### **TextoMesesTCMinimo** `H7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ComputarPedagio;TEXT(MesesTCMinimo;"0");0){% endhighlight %}


~~~
0.###############
~~~


> Texto referente aos meses necessários para cumprimento do pedágio (para demonstrativo)

* * *

##### **TextoObservacoes** `D20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(MostrarObservacoesAutomaticas="Sim";IFERROR("Observações períodos discriminados:"&CHAR(10)&CONCATENATE(ObservacoesPeriodosDiscriminados)&CHAR(10)&CHAR(10);"")&IFERROR("Observações períodos adicionados:"&CHAR(10)&CONCATENATE(ObservacoesPeriodosAdicionados)&CHAR(10)&CHAR(10);"");"")&IF(ISTEXT(ObservacoesFinais);"Observações finais:"&CHAR(10)&ObservacoesFinais;""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente às observações (para demonstrativo)

* * *

##### **TextoPedagio** `D3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&"Pedágio "&IF(ComputarPedagio;"("&TEXT(TotalDiasPedagio;"0.00")&" dias)";""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao pedágio a ser cumprido (para demonstrativo)

* * *

##### **TextoPontosDER** `L17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(PontosDER);TEXT(PontosDER;"0.00");" "){% endhighlight %}


~~~
0.###############
~~~


> Pontuação apurada na DER (para demonstrativo)

* * *

##### **TextoPontosDERReafirmada1** `N17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);IF(ISNUMBER(PontosDERReafirmada1);TEXT(PontosDERReafirmada1;"0.00");" ");""){% endhighlight %}


~~~
0.###############
~~~


> Pontuação apurada na data da primeira reafirmação (para demonstrativo)

* * *

##### **TextoPontosDERReafirmada2** `P17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);IF(ISNUMBER(PontosDERReafirmada2);TEXT(PontosDERReafirmada2;"0.00");" ");""){% endhighlight %}


~~~
0.###############
~~~


> Pontuação apurada na data da segunda reafirmação (para demonstrativo)

* * *

##### **TextoPontosDPE** `B17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoPontosDPL** `J17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoPontosPedagio** `D17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoPontosTCMinimo** `H17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoPontosTempoFaltante** `F17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=" "{% endhighlight %}


~~~
0.###############
~~~


> Não utilizado

* * *

##### **TextoTCMinimo** `H3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&"Tempo mínimo "&IF(ComputarPedagio;"("&TEXT(TotalDiasTCMinimo;"0.00")&" dias)";""){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao tempo mínimo necessário para cumprimento do pedágio (para demonstrativo)

* * *

##### **TextoTempoFaltanteComPedagio** `F3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CHAR(9)&"Tempo faltante com pedágio "&IF(DireitoAdquiridoDPE;"";"("&TEXT(TotalDiasFaltantesComPedagio;"0.00")&" dias)"){% endhighlight %}


~~~
0.###############
~~~


> Texto referente ao tempo faltante considerado o pedágio (para demonstrativo)