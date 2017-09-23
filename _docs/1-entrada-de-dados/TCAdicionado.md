---
title: TCAdicionado
category: Entrada
order: 3
---

##### **AnosAdicionados** `B:B`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de anos referente a tempo líquido a ser adicionado.

* * *

##### **AnosConvertidosTCAdicionado** `P:P`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosConvertidosTCAdicionado)=1;"Anos conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROUNDDOWN(TotalDiasConvertidosTCAdicionado/360);""))){% endhighlight %}



> Número de anos referente aos períodos adicionados após a conversão.

* * *

##### **AnosTCAdicionado** `B:B`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de anos referente a tempo líquido a ser adicionado.

* * *

##### **AnosTCAdicionadoDemonstrativo** `E:E`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosTCAdicionadoDemonstrativo)=1;"Anos";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(AnosAdicionados="";0;AnosAdicionados);""))){% endhighlight %}

+ **Formato**:
~~~
0
~~~


> Demonstração do número de anos referente a tempo líquido a ser adicionado.

* * *

##### **CarenciaTCAdicionado** `T:T`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCAdicionado)=1;"Carência";IF(ISNUMBER(CarenciaTCAdicionadoModificada);CarenciaTCAdicionadoModificada; IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ContarCarenciaTCAdicionado="Não";0;ROUNDUP(TotalDiasTCAdicionado/30));"")))){% endhighlight %}



> Carência (número de contribuições) referentes ao período adicionado

* * *

##### **CarenciaTCAdicionadoModificada** `U:U`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~


> Modificador referente aos meses de carência que devem ser computados

* * *

##### **ClassificacaoTCAdicionado** `K:K`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~

+ **Regra de validação**:
~~~
VALUE_IN_RANGE TabelaConversao!A:A
~~~

> Selecionar classificação do período para contagem diferenciada (ex.: especial)

* * *

##### **ContarCarenciaTCAdicionado** `S:S`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~

+ **Regra de validação**:
~~~
VALUE_IN_LIST Sim,Não
~~~

> Modificador que possibilita excluir período da contagem para efeito de carência

* * *

##### **DiasAdicionados** `D:D`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de dias referente a tempo líquido a ser adicionado.

* * *

##### **DiasConvertidosTCAdicionado** `R:R`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasConvertidosTCAdicionado)=1;"Dias conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;TotalDiasConvertidosTCAdicionado-(AnosConvertidosTCAdicionado*360)-(MesesConvertidosTCAdicionado*30);""))){% endhighlight %}



> Número de dias referente aos períodos adicionados após a conversão.

* * *

##### **DiasTCAdicionado** `D:D`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de dias referente a tempo líquido a ser adicionado.

* * *

##### **DiasTCAdicionadoDemonstrativo** `G:G`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasTCAdicionadoDemonstrativo)=1;"Dias";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(DiasAdicionados="";0;DiasAdicionados);""))){% endhighlight %}

+ **Formato**:
~~~
0
~~~


> Demonstração do número de dias referente a tempo líquido a ser adicionado.

* * *

##### **FatorConversaoTCAdicionado** `M:M`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(FatorConversaoTCAdicionado)=1;"Fator";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(FatorConversaoTCAdicionadoModificado;FatorConversaoTCAdicionadoModificado;IF(ReferenciaFatorTCAdicionado="N";0;TCAposentadoriaIntegral/(IF(ReferenciaFatorTCAdicionado="V";{" ";ReferenciaFatorTCAdicionado};ReferenciaFatorTCAdicionado))));""))){% endhighlight %}

+ **Formato**:
~~~
#,##0.00
~~~


> Matriz referente aos fatores de conversão aplicados aos períodos adicionados

* * *

##### **FatorConversaoTCAdicionadoModificado** `N:N`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~


> Modificador do fator de conversão

* * *

##### **LimitesTCAdicionado** `H:H`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(LimitesTCAdicionado)=1;"Até...";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(LimitesTCAdicionadoModificado;LimitesTCAdicionadoModificado;DER-1);""))){% endhighlight %}

+ **Formato**:
~~~
dd/MM/yyyy
~~~


> Termo final para cômputo dos períodos adicionados

* * *

##### **LimitesTCAdicionadoModificado** `I:I`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
dd/MM/yyyy
~~~


> Modificador do termo final a ser considerado do período adicionado.

* * *

##### **MesesAdicionados** `C:C`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de meses referente a tempo líquido a ser adicionado.

* * *

##### **MesesConvertidosTCAdicionado** `Q:Q`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesConvertidosTCAdicionado)=1;"Meses conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROUNDDOWN((TotalDiasConvertidosTCAdicionado-(AnosConvertidosTCAdicionado*360))/30);""))){% endhighlight %}



> Número de meses referente referente aos períodos adicionados após a conversão.

* * *

##### **MesesTCAdicionado** `C:C`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
0
~~~


> Número de meses referente a tempo líquido a ser adicionado.

* * *

##### **MesesTCAdicionadoDemonstrativo** `F:F`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesTCAdicionadoDemonstrativo)=1;"Meses";IF(AnosAdicionados+MesesAdicionados+DiasAdicionados;IF(MesesAdicionados="";0;MesesAdicionados);""))){% endhighlight %}

+ **Formato**:
~~~
0
~~~


> Demonstração do número de meses referente a tempo líquido a ser adicionado.

* * *

##### **MotivosTCAdicionado** `V:V`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~

+ **Regra de validação**:
~~~
VALUE_IN_RANGE ListaMotivos!A:A
~~~

> Preenchimento opcional do motivo  da inserção do período adicionado.

* * *

##### **MotivosTCAdicionadoDemonstrativo** `X:X`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MotivosTCAdicionadoDemonstrativo)=1;"Motivos Demonstrativo";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(MotivosTCAdicionado="";" ";MID(MotivosTCAdicionado;5;100));""))){% endhighlight %}





* * *

##### **ObservacoesTCAdicionado** `W:W`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~


> Observações referentes ao período adicionado.

* * *

##### **ObservacoesTCAdicionadoDemonstrativo** `Y:Y`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ObservacoesTCAdicionadoDemonstrativo)=1;"Observacoes Demonstrativo";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ObservacoesTCAdicionado="";"";"Seq. "&ROW(ObservacoesTCAdicionado)&". "&ObservacoesTCAdicionado);""))){% endhighlight %}





* * *

##### **ReferenciaFatorTCAdicionado** `L:L`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ReferenciaFatorTCAdicionado)=1;"Referência";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;IF(ClassificacaoTCAdicionado<>"";VLOOKUP(ClassificacaoTCAdicionado;TabelaConversao!A:B;IF(Sexo="Homem";2;3);FALSE);VLOOKUP("1 - Comum";TabelaConversao!A:B;IF(Sexo="Homem";2;3);FALSE));""))){% endhighlight %}





* * *

##### **SequenciaTCAdicionado** `A:A`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(SequenciaTCAdicionado)=1;"Seq";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;ROW(SequenciaTCAdicionado)-1;""))){% endhighlight %}

+ **Formato**:
~~~
0
~~~


> Sequência dos períodos adicionados

* * *

##### **TotalDiasConvertidosTCAdicionado** `O:O`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCAdicionado)=1;"Total conv.";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;TotalDiasTCAdicionado*FatorConversaoTCAdicionado;""))){% endhighlight %}



> Matriz referente ao tempo dos períodos adicionados após conversão (em dias)

* * *

##### **TotalDiasTCAdicionado** `J:J`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasTCAdicionado)=1;"Total (dias)";IF(AnosTCAdicionadoDemonstrativo+MesesTCAdicionadoDemonstrativo+DiasTCAdicionadoDemonstrativo;(AnosTCAdicionadoDemonstrativo*360)+(MesesTCAdicionadoDemonstrativo*30)+DiasTCAdicionadoDemonstrativo;""))){% endhighlight %}



> Matriz referente ao tempo dos períodos adicionados (em dias)