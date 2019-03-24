---
title: ConfigurarContagem
category: Entrada
order: 2
---

##### **AjustarMarcosTemporais** `H6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Selecionar opção automática para ajuste dos marcos temporais.

* * *

##### **AplicarLei11718** `H7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


~~~
VALUE_IN_LIST 1 - Não,2 - A partir de sua vigência,3 - Retroativamente
~~~

> Selecionar opção de contagem de carência na aposentadoria por idade do trabalhador rural, nos termos do art. 3º, da [Lei nº 11.718/2008](http://www.planalto.gov.br/ccivil_03/_ato2007-2010/2008/lei/l11718.htm).

* * *

##### **DERReafirmada1** `H11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Inserir nova DER no caso de 1ª reafirmação.


* * *

##### **DERReafirmada2** `H12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Inserir nova DER no caso de 2ª reafirmação.

* * *

##### **DLB** `D6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Indica primeiro marco temporal, vigência da Lei nº 8.213/91 (Lei de Benefícios).


* * *

##### **DPEMaisUm** `D7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DPE+1{% endhighlight %}


~~~
dd/MM/yyyy
~~~


> Indica o marco temporal relativo à EC nº 20/98.


* * *

##### **DPL** `D8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Indica o marco temporal relativo à Lei nº 9.876/99,

* * *

##### **EliminarConcomitancia** `H5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Selecionar opção de eliminação automática de concomitância de períodos entre vínculos/recolhimentos.

* * *

##### **MarcoCarencia** `G14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(MarcoCarenciaModificado="";IF(Especie=41;OpcoesCarencia!A1;OpcoesCarencia!A2);MarcoCarenciaModificado){% endhighlight %}





* * *

##### **MarcoCarenciaModificado** `H14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE OpcoesCarencia!A:A
~~~



* * *

##### **MarcosTemporais** `D6:D17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DPE+1
=DER+1
=DERReafirmada1
=DERReafirmada2{% endhighlight %}


~~~
dd/MM/yyyy
~~~


> Indica primeiro marco temporal, vigência da Lei nº 8.213/91 (Lei de Benefícios).

Indica o marco temporal relativo à EC nº 20/98.

Indica o marco temporal relativo à Lei nº 9.876/99,
Indica o marco temporal relativo a MP nº 676/2015, início da vigência dos pontos, permitindo a exclusão do fator previdenciário.

* * *

##### **RotuloDERReafirmada1** `F11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Identificação da primeira DER reafirmada.

* * *

##### **RotuloDERReafirmada2** `F12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Identificação da 2ª DER reafirmada.

* * *

##### **VigenciaPontos** `D9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Indica o marco temporal relativo a MP nº 676/2015, início da vigência dos pontos, permitindo a exclusão do fator previdenciário.