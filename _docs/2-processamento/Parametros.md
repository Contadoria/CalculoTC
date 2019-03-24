---
title: Parametros
category: Processamento
order: 1
---

##### **CarenciaExigida** `B11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(MID(MarcoCarencia;1;1)="1";CarenciaMinimaIdade;CarenciaMinimaDER){% endhighlight %}


~~~
0
~~~




* * *

##### **CarenciaMinimaDER** `B8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DER-1);TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) exigidas na DER

* * *

##### **CarenciaMinimaDERReafirmada1** `B9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DERReafirmada1-1);TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) exigidas na primeira data reafirmada

* * *

##### **CarenciaMinimaDERReafirmada2** `B10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DERReafirmada2-1);TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) exigidas na segunda data reafirmada

* * *

##### **CarenciaMinimaDPE** `B6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DPE);TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) exigidas até a Emenda Constitucional nº 20 de 1.998

* * *

##### **CarenciaMinimaDPL** `B7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DPL-1);TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) exigidas na DPL

* * *

##### **CarenciaMinimaIdade** `B5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(IF(MIN(DataInicialTCDiscriminadoProcessado)>=DLB;180;INDEX(TabelaCarencia!A:B;MATCH(YEAR(DataNascimento)+IdadeMinima;TabelaCarencia!A:A;1);2));180){% endhighlight %}


~~~
0
~~~


> Carência (número de contribuições) exigidas na data em que completa o requisito etário (aposentadoria por idade)

* * *

##### **ComputarPedagio** `B3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=AND(Especie=42;TotalDiasDPE>0;TotalDiasFaltantesComPedagio>0;TotalDiasFaltantesComPedagio+TotalDiasDPE<(IF(Sexo="Mulher";30;35)*360)){% endhighlight %}


~~~
mm"/"yyyy
~~~


> Verificação da necessidade de apuração do pedágio

* * *

##### **DireitoAdquiridoDPE** `B13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=AND(TotalCarenciaDPE>=CarenciaDPE;TotalDiasDPE>=TotalDiasTCMinimoDPE){% endhighlight %}


~~~
mm"/"yyyy
~~~


> Verificação do direito adquirido até a Emenda Constitucional nº 20 de 1.998

* * *

##### **IdadeMinima** `B4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(Especie=41;IF(BeneficioRural="Sim";IF(Sexo="Homem";60;55);IF(Sexo="Homem";65;60));IF(ComputarPedagio;IF(Sexo="Mulher";48;53);0)){% endhighlight %}


~~~
0
~~~


> Idade mínima exigida para concessão da aposentadoria

* * *

##### **PontuacaoMinimaDER** `B15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DER>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DER-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica"){% endhighlight %}


~~~
0.###############
~~~


> Pontuação mínima necessária na DER para possibilitar exclusão do fator previdenciário

* * *

##### **PontuacaoMinimaDERReafirmada1** `B16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada1>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DERReafirmada1-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica"){% endhighlight %}



> Pontuação mínima necessária na primeira data reafirmada para possibilitar exclusão do fator previdenciário

* * *

##### **PontuacaoMinimaDERReafirmada2** `B17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada2>=VigenciaPontos);INDEX(TabelaPontuacao!A:C;MATCH(DERReafirmada2-1;TabelaPontuacao!A:A;1);IF(Sexo="Homem";2;3));"não se aplica"){% endhighlight %}



> Pontuação mínima necessária na segunda data reafirmada para possibilitar exclusão do fator previdenciário

* * *

##### **TotalDiasTCMinimo** `B14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(Especie=42;IF(ComputarPedagio;MIN(TotalDiasDPE+TotalDiasFaltantesComPedagio;IF(Sexo="Homem";35*360;30*360));IF(DireitoAdquiridoDPE;IF(Sexo="Homem";30*360;25*360);TCAposentadoriaIntegral*360));TCAposentadoriaIntegral*360){% endhighlight %}


~~~
0
~~~


> Tempo mínimo de contribuição exigido para concessão do benefício aposentadoria por tempo de contribuição

* * *

##### **TotalDiasTCMinimoDPE** `B12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(Especie=42;IF(Sexo="Homem";30*360;25*360);0){% endhighlight %}


~~~
0
~~~


> Tempo de contribuição mínimo exigido para concessão da aposentadoria por tempo de contribuição até Emenda Constitucional nº 20 de 1.998