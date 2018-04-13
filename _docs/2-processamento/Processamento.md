---
title: Processamento
category: Processamento
order: 0
---

##### **AnosAcrescimoTCDiscriminadoProcessado** `AL:AL`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosAcrescimoTCDiscriminadoProcessado)=1;"Anos acrésc.";IF(ROW(AnosAcrescimoTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasAcrescimoTCDiscriminadoProcessado/360)))){% endhighlight %}





* * *

##### **AnosConvertidosTCDiscriminadoProcessado** `AP:AP`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosConvertidosTCDiscriminadoProcessado)=1;"Anos conv.";IF(ROW(AnosConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasConvertidosTCDiscriminadoProcessado/360)))){% endhighlight %}



> Número de anos referente aos períodos discriminados após a conversão.

* * *

##### **AnosTCDiscriminadoProcessado** `AH:AH`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(AnosTCDiscriminadoProcessado)=1;"Anos";IF(ROW(AnosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(TotalDiasTCDiscriminadoProcessado/360)))){% endhighlight %}



> Número de anos referentes aos períodos discriminados.

* * *

##### **ClassificacaoTCDiscriminado** `AE:AE`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Classificação dos períodos discriminados

* * *

##### **ContarCarenciaTCDiscriminadoProcessado** `AB:AB`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **ContinuaAnterior** `AU:AU`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ContinuaAnterior)=1;"Continua ant.";IF(ROW(ContinuaAnterior)>COUNTA(DataInicialTCDiscriminadoProcessado);"";IF(ROW(ContinuaAnterior)=2;FALSE;EOMONTH({"";DataFinalTCDiscriminadoProcessado};0)=EOMONTH(DataInicialTCDiscriminadoProcessado;0))))){% endhighlight %}


~~~
dd/MM/yyyy
~~~


> Matriz para verificação se o mês de início do presente período é igual ao do período anterior

* * *

##### **DataFinalTCDiscriminadoProcessado** `Y:Y`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Matriz referente às datas finais dos períodos discriminados, considerando os ajustes referentes aos marcos temporais

* * *

##### **DataInicialTCDiscriminadoProcessado** `X:X`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}={"Data inicial"\"Data final"\"Descrição"\"Natureza"\"Contar Carência"\"Motivos"\"Observações"\"Classificação"\"Fator";IF(COUNT(M2:U)>2;
IF(AjustarMarcosTemporais="Sim";jef_ESTABELECER_MARCOS_TEMPORAIS(OFFSET(M2:U2;0;0;COUNT(M:M));MarcosTemporais);OFFSET(M2:U2;0;0;COUNT(M:M)));{TODAY()\TODAY()\""\""\""\""\""\""\""})}{% endhighlight %}


~~~
0.###############
~~~


> Matriz referente às datas iniciais dos períodos discriminados, considerando os ajustes referentes aos marcos temporais

* * *

##### **DescricaoTCDiscriminadoProcessado** `Z:Z`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **DiasAcrescimoTCDiscriminadoProcessado** `AN:AN`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasAcrescimoTCDiscriminadoProcessado)=1;"Dias acrésc.";IF(ROW(DiasAcrescimoTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasAcrescimoTCDiscriminadoProcessado-(AnosAcrescimoTCDiscriminadoProcessado*360)-(MesesAcrescimoTCDiscriminadoProcessado*30)))){% endhighlight %}





* * *

##### **DiasConvertidosTCDiscriminadoProcessado** `AR:AR`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasConvertidosTCDiscriminadoProcessado)=1;"Dias conv.";IF(ROW(DiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360)-(MesesConvertidosTCDiscriminadoProcessado*30)))){% endhighlight %}



> Número de dias referente aos períodos discriminados após a conversão.

* * *

##### **DiasTCDiscriminadoProcessado** `AJ:AJ`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DiasTCDiscriminadoProcessado)=1;"Dias";IF(ROW(DiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360)-(MesesTCDiscriminadoProcessado*30)))){% endhighlight %}



> Número de dias referentes aos períodos discriminados.

* * *

##### **FatorConversaoTCDiscriminadoProcessado** `AF:AF`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.00
~~~


> Fator de conversão dos períodos discriminados

* * *

##### **MesesAcrescimoTCDiscriminadoProcessado** `AM:AM`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesAcrescimoTCDiscriminadoProcessado)=1;"Meses acrésc.";IF(ROW(MesesAcrescimoTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasAcrescimoTCDiscriminadoProcessado-(AnosAcrescimoTCDiscriminadoProcessado*360))/30)))){% endhighlight %}





* * *

##### **MesesConvertidosTCDiscriminadoProcessado** `AQ:AQ`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesConvertidosTCDiscriminadoProcessado)=1;"Meses conv.";IF(ROW(MesesConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasConvertidosTCDiscriminadoProcessado-(AnosConvertidosTCDiscriminadoProcessado*360))/30)))){% endhighlight %}



> Número de meses referente aos períodos discriminados após a conversão.

* * *

##### **MesesTCDiscriminadoProcessado** `AI:AI`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesesTCDiscriminadoProcessado)=1;"Meses";IF(ROW(MesesTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN((TotalDiasTCDiscriminadoProcessado-(AnosTCDiscriminadoProcessado*360))/30)))){% endhighlight %}



> Número de meses referentes aos períodos discriminados.

* * *

##### **MesmoAno** `AS:AS`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesmoAno)=1;"Mesmo Ano";IF(ROW(MesmoAno)>COUNTA(DataInicialTCDiscriminadoProcessado);"";YEAR(DataInicialTCDiscriminadoProcessado)=YEAR(DataFinalTCDiscriminadoProcessado)))){% endhighlight %}



> Matriz para verificação se o período possui data inicial e final dentro do mesmo ano

* * *

##### **MesmoMes** `AT:AT`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(MesmoMes)=1;"Mesmo Mês";IF(ROW(MesmoMes)>COUNTA(DataInicialTCDiscriminadoProcessado);"";EOMONTH(DataInicialTCDiscriminadoProcessado;0)=EOMONTH(DataFinalTCDiscriminadoProcessado;0)))){% endhighlight %}



> Matriz para verificação se o período possui data inicial e final dentro do mesmo mês

* * *

##### **MotivosTCDiscriminadoProcessado** `AC:AC`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **NaturezaTCDiscriminadoProcessado** `AA:AA`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **ObservacoesTCDiscriminadoProcessado** `AD:AD`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~




* * *

##### **TCProcessado** `A:A`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}={DataInicialTratada\DataFinalTratada\DescricaoTCDiscriminado\NaturezaTCDiscriminado\ARRAYFORMULA(IF(ROW(ContarCarenciaTCDiscriminado)=1;"Contar Carência";IF(ISNUMBER(DataInicialTratada);ContarCarenciaTCDiscriminado<>"Não";"")))\MotivosTCDiscriminado\ObservacoesTCDiscriminado\ARRAYFORMULA(IF(ROW(ClassificacaoTCInformado1)>COUNT(DataInicialTratada)+1;"";IF(ClassificacaoTCInformado1="";"1 - Comum";ClassificacaoTCInformado1)))\FatorConversaoTCDiscriminado\PrioridadeTCDiscriminado}{% endhighlight %}


~~~
dd/MM/yyyy
~~~


> Processamento dos períodos discriminados informados

* * *

##### **TotalDiasAcrescimoTCDiscriminadoProcessado** `AK:AK`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasAcrescimoTCDiscriminadoProcessado)=1;"Total acrésc.";IF(ROW(TotalDiasAcrescimoTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1)*FatorConversaoTCDiscriminadoProcessado)-TotalDiasTCDiscriminadoProcessado))){% endhighlight %}





* * *

##### **TotalDiasConvertidosTCDiscriminadoProcessado** `AO:AO`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)=1;"Total conv.";IF(ROW(TotalDiasConvertidosTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";ROUNDDOWN(DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1)*FatorConversaoTCDiscriminadoProcessado)))){% endhighlight %}



> Matriz referente ao tempo dos períodos discriminados após conversão (em dias)

* * *

##### **TotalDiasTCDiscriminadoProcessado** `AG:AG`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(TotalDiasTCDiscriminadoProcessado)=1;"Total (dias)";IF(ROW(TotalDiasTCDiscriminadoProcessado)>COUNTA(DataInicialTCDiscriminadoProcessado);"";DAYS360(DataInicialTCDiscriminadoProcessado;DataFinalTCDiscriminadoProcessado+1)))){% endhighlight %}



> Matriz referente ao tempo dos períodos discriminados (em dias)