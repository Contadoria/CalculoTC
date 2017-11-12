---
title: TCDiscriminado
category: Entrada
order: 2
---

##### **ClassificacaoTCInformado1** `H:H`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE TabelaConversao!A:A
~~~

> Selecionar classificação do período para contagem diferenciada (ex.: especial)

* * *

##### **DataFinalTCDiscriminado** `D:D`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
d/m/yyyy
~~~


> Inserir data final do período discriminado.

* * *

##### **DataFinalTratada** `F:F`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DataFinalTratada)=1;"DF Tratada";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;DataFinalTCDiscriminado-(HOUR(DataFinalTCDiscriminado)/24);""))){% endhighlight %}


~~~
dd/MM/yyyy
~~~




* * *

##### **DataInicialTCDiscriminado** `C:C`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Inserir a data inicial do período discriminado.

* * *

##### **DataInicialTratada** `E:E`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(DataInicialTratada)=1;"DI Tratada";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;DataInicialTCDiscriminado-(HOUR(DataInicialTCDiscriminado)/24);""))){% endhighlight %}


~~~
dd/MM/yyyy
~~~




* * *

##### **DescricaoTCDiscriminado** `A:A`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Descrição do período informado.

* * *

##### **ErrosTCDiscriminado** `G:G`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ErrosTCDiscriminado)=1;"Erros";IF(DataInicialTratada*DataFinalTratada;IF(MMULT((DataInicialTratada<=TRANSPOSE(DataFinalTratada))*(DataFinalTratada>=TRANSPOSE(DataInicialTratada));SIGN(ROW(DataInicialTratada)))>1;"Concomitância";IF(DataFinalTratada<DataInicialTratada;"Final < Inicial";""));" "))){% endhighlight %}



> Fórmula matriz (ArrayFormula) indica concomitância ou erros apurados quando do processamento das datas.

* * *

##### **FatorConversaoTCDiscriminado** `J:J`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(FatorConversaoTCDiscriminado)=1;"Fator Conv.";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(FatorConversaoTCDiscriminadoModificado;FatorConversaoTCDiscriminadoModificado;IF(ReferenciaFatorTCDiscriminado="N";0;ROUND(TCAposentadoriaIntegral/(IF(ReferenciaFatorTCDiscriminado="V";{" ";ReferenciaFatorTCDiscriminado};ReferenciaFatorTCDiscriminado));2)));""))){% endhighlight %}


~~~
0.00
~~~


> digite aqui

Fórmula matriz (ArrayFormula) indica fator de conversão relacionado ao tempo discriminado.
Arredondamento até segunda casa consistente com Decreto 8.145/2013 (alterado em 09/11/2017)

* * *

##### **FatorConversaoTCDiscriminadoModificado** `K:K`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Modificador do fator de conversão

* * *

##### **MotivosTCDiscriminado** `N:N`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE ListaMotivos!A:A
~~~

> Preenchimento opcional do motivo  da inserção do período discriminado

* * *

##### **NaturezaTCDiscriminado** `B:B`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Natureza do vínculo referente ao período discriminado

* * *

##### **ObservacoesTCDiscriminado** `O:O`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Observações referentes ao período discriminado

* * *

##### **PrioridadeTCDiscriminado** `L:L`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(PrioridadeTCDiscriminado)=1;"Prioridade";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(PrioridadeTCDiscriminadoModificada="Sim";TRUE;IF(PrioridadeTCDiscriminadoModificada="Não";FALSE;MID(ClassificacaoTCInformado1;1;1)="9"));""))){% endhighlight %}





* * *

##### **PrioridadeTCDiscriminadoModificada** `M:M`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~



* * *

##### **ReferenciaFatorTCDiscriminado** `I:I`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ARRAYFORMULA(IF(ROW(ReferenciaFatorTCDiscriminado)=1;"Referência";IF(DataInicialTCDiscriminado*DataFinalTCDiscriminado;IF(ClassificacaoTCInformado1<>"";VLOOKUP(ClassificacaoTCInformado1;TabelaConversao!A:C;IF(Sexo="Homem";2;3);FALSE);VLOOKUP("1 - Comum";TabelaConversao!A:C;IF(Sexo="Homem";2;3);FALSE));""))){% endhighlight %}



> Fórmula matriz (ArrayFormula) indica tempo de contribuição necessário para concessão do benefício (referência para apuração do fator de conversão)

* * *

##### **TCInformado** `A:A`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Descrição do período informado.