---
title: Processamento
category: Processamento
order: 0
---

##### **AnosConvertidosTCDiscriminadoProcessado** `AG:AG`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosConvertidosTCDiscriminadoProcessado)=1;"Anos conv.";IF(ROW(AnosConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasConvertidosTCDiscriminadoProcessado/360)))){% endhighlight %}



> Número de anos referente aos períodos discriminados após a conversão.

* * *

##### **AnosTCDiscriminadoProcessado** `AC:AC`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosTCDiscriminadoProcessado)=1;"Anos";IF(ROW(AnosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasTCDiscriminadoProcessado/360)))){% endhighlight %}



> Número de anos referentes aos períodos discriminados.

* * *

##### **ClassificacaoTCDiscriminado** `Z:Z`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~


> Classificação dos períodos discriminados

* * *

##### **ContinuaAnterior** `AL:AL`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ContinuaAnterior)=1;"Continua ant.";IF(ROW(ContinuaAnterior)>COUNTA(DataInicialTCDiscriminadoProcessado);"";IF(ROW(ContinuaAnterior)=2;FALSE;EOMONTH({"";DataFinalTCDiscriminadoProcessado};0)=EOMONTH(DataInicialTCDiscriminadoProcessado;0))))){% endhighlight %}

+ **Formato**:
~~~
dd/MM/yyyy
~~~


> Matriz para verificação se o mês de início do presente período é igual ao do período anterior

* * *

##### **DataFinalTCDiscriminadoProcessado** `U:U`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~


> Matriz referente às datas finais dos períodos discriminados, considerando os ajustes referentes aos marcos temporais

* * *

##### **DataInicialTCDiscriminadoProcessado** `T:T`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}={"Data inicial"\"Data final"\"Descrição"\"Natureza"\"Motivos"\"Observações"\"Classificação"\"Fator";
IF(AjustarMarcosTemporais="Sim";jef_ESTABELECER_MARCOS_TEMPORAIS(K2:R;MarcosTemporais);K2:R)}{% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Matriz referente às datas iniciais dos períodos discriminados, considerando os ajustes referentes aos marcos temporais

* * *

##### **DescricaoTCDiscriminadoProcessado** `V:V`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~




* * *

##### **DiasConvertidosTCDiscriminadoProcessado** `AI:AI`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasConvertidosTCDiscriminadoProcessado)=1;"Dias conv.";IF(ROW(DiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360)-(MesesConvertidosTCDiscriminadoProcessado*30)))){% endhighlight %}



> Número de dias referente aos períodos discriminados após a conversão.

* * *

##### **DiasTCDiscriminadoProcessado** `AE:AE`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasTCDiscriminadoProcessado)=1;"Dias";IF(ROW(DiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360)-(MesesTCDiscriminadoProcessado*30)))){% endhighlight %}



> Número de dias referentes aos períodos discriminados.

* * *

##### **FatorConversaoTCDiscriminadoProcessado** `AA:AA`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.00
~~~


> Fator de conversão dos períodos discriminados

* * *

##### **MesesConvertidosTCDiscriminadoProcessado** `AH:AH`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesConvertidosTCDiscriminadoProcessado)=1;"Meses conv.";IF(ROW(MesesConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360))/30)))){% endhighlight %}



> Número de meses referente aos períodos discriminados após a conversão.

* * *

##### **MesesTCDiscriminadoProcessado** `AD:AD`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesTCDiscriminadoProcessado)=1;"Meses";IF(ROW(MesesTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360))/30)))){% endhighlight %}



> Número de meses referentes aos períodos discriminados.

* * *

##### **MesmoAno** `AJ:AJ`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesmoAno)=1;"Mesmo Ano";IF(ROW(MesmoAno)>COUNTA(DataInicialTCDiscriminadoProcessado);"";YEAR(DataInicialTCDiscriminadoProcessado)=YEAR(DataFinalTCDiscriminadoProcessado)))){% endhighlight %}



> Matriz para verificação se o período possui data inicial e final dentro do mesmo ano

* * *

##### **MesmoMes** `AK:AK`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesmoMes)=1;"Mesmo Mês";IF(ROW(MesmoMes)>COUNTA(DataInicialTCDiscriminadoProcessado);"";EOMONTH(DataInicialTCDiscriminadoProcessado;0)=EOMONTH(DataFinalTCDiscriminadoProcessado;0)))){% endhighlight %}



> Matriz para verificação se o período possui data inicial e final dentro do mesmo mês

* * *

##### **MotivosTCDiscriminadoProcessado** `X:X`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~




* * *

##### **NaturezaTCDiscriminadoProcessado** `W:W`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~




* * *

##### **ObservacoesTCDiscriminadoProcessado** `Y:Y`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
0.###############
~~~




* * *

##### **TCProcessado** `A:A`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}={DataInicialTratada\DataFinalTratada\DescricaoTCDiscriminado\NaturezaTCDiscriminado\MotivosTCDiscriminado\ObservacoesTCDiscriminado\ARRAYFORMULA(IF(ROW(ClassificacaoTCInformado1)>COUNTA(DataInicialTCDiscriminado);"";IF(ClassificacaoTCInformado1="";"1 - Comum";ClassificacaoTCInformado1)))\FatorConversaoTCDiscriminado}{% endhighlight %}

+ **Formato**:
~~~
dd/MM/yyyy
~~~


> Processamento dos períodos discriminados informados

* * *

##### **TotalDiasConvertidosTCDiscriminadoProcessado** `AF:AF`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)=1;"Total conv.";IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1)*FatorConversaoTCDiscriminadoProcessado)))){% endhighlight %}



> Matriz referente ao tempo dos períodos discriminados após conversão (em dias)

* * *

##### **TotalDiasTCDiscriminadoProcessado** `AB:AB`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasTCDiscriminadoProcessado)=1;"Total (dias)";IF(ROW(TotalDiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1)))){% endhighlight %}



> Matriz referente ao tempo dos períodos discriminados (em dias)