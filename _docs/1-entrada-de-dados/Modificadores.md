---
title: Modificadores
category: Entrada
order: 4
---

##### **AcrescimoModificado** `X4:X204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Modificador referente ao acréscimo da Lei 11.718/2008

* * *

##### **Acrescimos** `W4:W204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ISNUMBER(AcrescimoModificado);AcrescimoModificado;IF(ROW(Acrescimos)=4;"Acréscimos Lei 11.718/2008";IF(D4:D*E4:E;IF(MID(AplicarLei11718;1;1)="1";0;IF(AND(Especie=41;BeneficioRural="Sim");{" ";jef_CALCULAR_ACRESCIMOS_LEI_11718(D5:E;MID(AplicarLei11718;1;1)="3")};0));"")))){% endhighlight %}



> Acréscimos apurados com base na no artigo 3º da Lei 11.718/2008.

* * *

##### **CarenciaTCDiscriminado** `U4:U204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ISNUMBER(CarenciaTCDiscriminadoModificada);CarenciaTCDiscriminadoModificada;IF(ROW(CarenciaTCDiscriminado)=4;"Carência";IF(ROW(CarenciaTCDiscriminado)>COUNTA(DataInicialTCDiscriminadoProcessado)+3;"";IF(ContarCarenciaTCDiscriminado<>"Não";IF(MesmoMes;1;IF(MesmoAno;MONTH(DataFinalTCDiscriminadoProcessado)-MONTH(DataInicialTCDiscriminadoProcessado)+1;(12-MONTH(DataInicialTCDiscriminadoProcessado)+1+MONTH(DataFinalTCDiscriminadoProcessado)+((YEAR(DataFinalTCDiscriminadoProcessado)-YEAR(DataInicialTCDiscriminadoProcessado)-1)*12))))-IF(ContinuaAnterior*{TRUE;ContarCarenciaTCDiscriminado<>"Não"};1;0);0))))){% endhighlight %}



> Carência apurada dos períodos discriminados.

* * *

##### **CarenciaTCDiscriminadoModificada** `V4:V204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Modificador referente aos meses de carência que devem ser computados

* * *

##### **ContarCarenciaTCDiscriminado** `T4:T204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Modificador que possibilita excluir período da contagem para efeito de carência

* * *

##### **DescricaoTCDiscriminadoDemonstrativo** `F4:F204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **MotivosTCDiscriminadoDemonstrativo** `R4:R204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}={"Motivos Demonstrativo";ARRAYFORMULA(IF(OFFSET(DataInicialTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado))*OFFSET(DataFinalTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado));IF(OFFSET(MotivosTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado))="";"";" ("&MID(OFFSET(MotivosTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado));1;1)&")");""))}{% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ObservacoesTCDiscriminadoDemonstrativo** `S4:S204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}={"Observacoes Demonstrativo";ARRAYFORMULA(IF(OFFSET(DataInicialTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado;1;0))*OFFSET(DataFinalTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado;1;0));IF(OFFSET(ObservacoesTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado;1;0))="";"";"Seq. "&ROW(OFFSET(ObservacoesTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado;1;0)))-1&". "&OFFSET(ObservacoesTCDiscriminadoProcessado;1;0;COUNT(DataInicialTCDiscriminadoProcessado;1;0)));""))}{% endhighlight %}


~~~
0.###############
~~~




* * *

##### **SequenciaTCDiscriminado** `C4:C204`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(SequenciaTCDiscriminado)=4;"Seq.";IF(ROW(SequenciaTCDiscriminado)>COUNT(DataInicialTCDiscriminadoProcessado)+4;"";ROW(SequenciaTCDiscriminado)-4))){% endhighlight %}



> Sequência dos períodos discriminados