---
title: Configuracoes
category: Entrada
order: 0
---

##### **EstatisticaUrl** `D7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=HYPERLINK("https://script.google.com/macros/s/AKfycbz-yl2lxDMQ3yai5VIayuyospcF6FArZ81d6p8KtR_UhWOcRNc/exec"; "Teste_Estatistica (ESTATISTICA)"){% endhighlight %}


~~~
0.###############
~~~


> Link para planilha vinculada de estatística

* * *

##### **Identificador** `D14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Indicador que será exibido na parte superior à direita do demonstrativo

* * *

##### **Juizo** `D10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE ListaJuizos!A:A
~~~



* * *

##### **MostrarObservacoesAutomaticas** `D15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~



* * *

##### **ObservacoesFinais** `D16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Observações que serão exibidas na parte final do demonstrativo

* * *

##### **Secao** `D11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE ListaJuizos!B:B
~~~



* * *

##### **Subsecao** `D12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE ListaJuizos!C:C
~~~



* * *

##### **TituloTC** `D13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Título que será exibido no demonstrativo

* * *

##### **UrlPlanilha** `D4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=jef_URL(Demonstrativo!C16){% endhighlight %}


