---
title: Modificadores
category: Entrada
order: 4
---

##### **AcrescimoModificado** `X4:X63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Modificador referente ao acréscimo da Lei 11.718/2008

* * *

##### **Acrescimos** `W4:W63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ISNUMBER(AcrescimoModificado);AcrescimoModificado;IF(ROW(Acrescimos)=4;"Acréscimos Lei 11.718/2008";IF(D4:D*E4:E;IF(MID(AplicarLei11718;1;1)="1";0;IF(AND(Especie=41;BeneficioRural="Sim");{" ";jef_CALCULAR_ACRESCIMOS_LEI_11718(D5:E;MID(AplicarLei11718;1;1)="3")};0));"")))){% endhighlight %}



> Acréscimos apurados com base na no artigo 3º da Lei 11.718/2008.

* * *

##### **CarenciaTCDiscriminado** `U4:U62`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ISNUMBER(CarenciaTCDiscriminadoModificada);CarenciaTCDiscriminadoModificada;IF(ROW(CarenciaTCDiscriminado)=4;"Carência";IF(ROW(CarenciaTCDiscriminado)>COUNTA(DataInicialTCDiscriminadoProcessado)+3;"";IF(ContarCarenciaTCDiscriminado<>"Não";IF(MesmoMes;1;IF(MesmoAno;MONTH(DataFinalTCDiscriminadoProcessado)-MONTH(DataInicialTCDiscriminadoProcessado)+1;(12-MONTH(DataInicialTCDiscriminadoProcessado)+1+MONTH(DataFinalTCDiscriminadoProcessado)+((YEAR(DataFinalTCDiscriminadoProcessado)-YEAR(DataInicialTCDiscriminadoProcessado)-1)*12))))-IF(ContinuaAnterior*{TRUE;ContarCarenciaTCDiscriminado<>"Não"};1;0);0))))){% endhighlight %}



> Carência apurada dos períodos discriminados.

* * *

##### **CarenciaTCDiscriminadoModificada** `V4:V62`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Modificador referente aos meses de carência que devem ser computados

* * *

##### **ContarCarenciaTCDiscriminado** `T4:T63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Modificador que possibilita excluir período da contagem para efeito de carência

* * *

##### **MotivosTCDiscriminadoDemonstrativo** `R4:R63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MotivosTCDiscriminadoDemonstrativo)=4;"Motivos Demonstrativo";IF(DataInicialTCDiscriminadoProcessado*DataFinalTCDiscriminadoProcessado;IF(MotivosTCDiscriminadoProcessado="";" ";" ("&MID(MotivosTCDiscriminadoProcessado;1;1)&")");""))){% endhighlight %}





* * *

##### **ObservacoesTCDiscriminadoDemonstrativo** `S4:S63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ObservacoesTCDiscriminadoDemonstrativo)=4;"Observacoes Demonstrativo";IF(DataInicialTCDiscriminadoProcessado*DataFinalTCDiscriminadoProcessado;IF(ObservacoesTCDiscriminadoProcessado="";"";"Seq. "&ROW(ObservacoesTCDiscriminadoProcessado)-1&". "&ObservacoesTCDiscriminadoProcessado);""))){% endhighlight %}





* * *

##### **SequenciaTCDiscriminado** `C4:C63`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(SequenciaTCDiscriminado)=4;"Seq";IF(DataInicialTCDiscriminadoProcessado;ROW(SequenciaTCDiscriminado)-4;""))){% endhighlight %}



> Sequência dos períodos discriminados