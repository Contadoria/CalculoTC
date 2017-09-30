---
title: Processo
category: Entrada
order: 0
---

##### **Autor** `D6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Nome do autor


* * *

##### **BeneficioDeficiente** `K9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Selecionar se trata-se de benefício para deficiente.

* * *

##### **BeneficioRural** `K8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


~~~
VALUE_IN_LIST Sim,Não
~~~

> Selecionar se trata-se de benefício rural.

* * *

##### **Citacao** `D9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Data da citação do réu.

* * *

##### **DER** `K7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}



~~~
DATE_IS_VALID_DATE 
~~~

> Indica a data da DER.


* * *

##### **DataNascimento** `D13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Data de nascimento do autor.

* * *

##### **Especie** `K6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_RANGE ListaBeneficios!A:A
~~~

> Seleciona a espécie do benefício.

* * *

##### **NB** `K5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Número do benefício.

* * *

##### **Processo** `D5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Número do processo


* * *

##### **Protocolo** `D8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~


> Data do protocolo inicial.


* * *

##### **Reu** `D7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
#,##0
~~~


> Nome do réu.

* * *

##### **Sexo** `D12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


~~~
VALUE_IN_LIST Homem,Mulher
~~~

> Seleciona o sexo do segurado.

* * *

##### **TCAposentadoriaIntegral** `K12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(TCAposentadoriaIntegralModificado);TCAposentadoriaIntegralModificado;IF(Especie=46;25;IF(Sexo="Homem";35;30))){% endhighlight %}


~~~
#,##0
~~~


> Indica tempo necessário à aposentadoria integral, observado o sexo do segurado e espécie do benefício,assumindo modificadores se houver.

* * *

##### **TCAposentadoriaIntegralModificado** `L12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
0.###############
~~~


> Inserir manualmente tempo de contribuição para aposentadoria integral.