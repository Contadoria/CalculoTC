---
title: Resultado
category: Processamento
order: 2
---

##### **AnosAcrescimoTempoEspecial** `F20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(TotalAcrescimoTempoEspecial/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **AnosDER** `F27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E27/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **AnosDERReafirmada1** `F28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E28);ROUNDDOWN(E28/360);""){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **AnosDERReafirmada2** `F29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E29);ROUNDDOWN(E29/360);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **AnosDPE** `F22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E22/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosDPL** `F26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E26/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DER

* * *

##### **AnosFaltantesComPedagio** `F24`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E24/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **AnosPedagio** `F23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E23/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosTCMinimo** `F25`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E25/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DPL

* * *

##### **BeneficioIntegralDER** `M27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDER>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDER>=360)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na primeira data reafirmada

* * *

##### **BeneficioIntegralDERReafirmada1** `M28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);OR(AND(Especie=42;TotalDiasDERReafirmada1>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDERReafirmada1>=360));""){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na segunda data reafirmada

* * *

##### **BeneficioIntegralDERReafirmada2** `M29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);OR(AND(Especie=42;TotalDiasDERReafirmada2>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDERReafirmada2>=360));""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **BeneficioIntegralDPE** `M22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDPE>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDPE>=360)){% endhighlight %}


~~~
0%
~~~




* * *

##### **BeneficioIntegralDPL** `M26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDPL>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDPL>=360)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na DER.
Adicionado critério para aposentadoria por idade (alterado em 21/10/2017)

* * *

##### **CarenciaDER** `I27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DER;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DER;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a primeira data reafirmada

* * *

##### **CarenciaDERReafirmada1** `I28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;CarenciaTCAdicionado);""){% endhighlight %}



> Carência (número de contribuições) apuradas até a segunda data reafirmada

* * *

##### **CarenciaDERReafirmada2** `I29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada2;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DERReafirmada2;CarenciaTCAdicionado);""){% endhighlight %}





* * *

##### **CarenciaDPE** `I22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;CarenciaTCAdicionado){% endhighlight %}





* * *

##### **CarenciaDPL** `I26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPL;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a DER

**18/10/2017**: alterado de "<" para "<="

* * *

##### **CoeficienteDER** `N27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AjustarMarcosTemporais="Não";"";IF(ISNUMBER(INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7));INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7);IF(DireitoAoBeneficioDER;IF(Especie=42;IF(BeneficioIntegralDER;1;MIN((ROUNDDOWN((TotalDiasDER-TotalDiasTCMinimo)/360)*0,05)+0,7;1));IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDER/12)*0,01)+0,7;1);""));""))){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na primeira data reafirmada

* * *

##### **CoeficienteDERReafirmada1** `N28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);IF(ISNUMBER(INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7));INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7);IF(ISNUMBER(DERReafirmada1);IF(DireitoAoBeneficioDERReafirmada1;IF(Especie=42;IF(BeneficioIntegralDERReafirmada1;1;MIN((ROUNDDOWN((TotalDiasDERReafirmada1-TotalDiasTCMinimo)/360)*0,05)+0,7;1));IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDERReafirmada1/12)*0,01)+0,7;1);""));"");""));""){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na segunda data reafirmada

* * *

##### **CoeficienteDERReafirmada2** `N29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);IF(ISNUMBER(INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7));INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7);IF(ISNUMBER(DERReafirmada2);IF(DireitoAoBeneficioDERReafirmada2;IF(Especie=42;IF(BeneficioIntegralDERReafirmada2;1;MIN((ROUNDDOWN((TotalDiasDERReafirmada2-TotalDiasTCMinimo)/360)*0,05)+0,7;1));IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDERReafirmada2/12)*0,01)+0,7;1);""));"");""));""){% endhighlight %}


~~~
0%
~~~




* * *

##### **CoeficienteDPE** `N22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7));INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7);IF(DireitoAoBeneficioDPE;IF(Especie=42;IF(BeneficioIntegralDPE;1;MIN((ROUNDDOWN((TotalDiasDPE-TotalDiasTCMinimoDPE)/360)*0,06)+0,7;1));IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDER/12)*0,01)+0,7;1);""));"")){% endhighlight %}


~~~
0%
~~~




* * *

##### **CoeficienteDPL** `N26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7));INDEX(ListaBeneficios!A:G;MATCH(Especie;ListaBeneficios!A:A;0);7);IF(DireitoAoBeneficioDPL;IF(Especie=42;IF(BeneficioIntegralDPL;1;MIN((ROUNDDOWN((TotalDiasDPL-TotalDiasTCMinimo)/360)*0,05)+0,7;1));IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDER/12)*0,01)+0,7;1);""));"")){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na DPL
Substituído (ARREDONDAR.PARA.BAIXO(TotalDiasDPL/360)-ARREDONDAR.PARA.BAIXO(TotalDiasTCMinimo/360)) por ARREDONDAR.PARA.BAIXO((TotalDIasDPL-TotalDiasMinimo)/360)
Alterado em 20/10/2017

* * *

##### **DPE** `B22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~




* * *

##### **DiasAcrescimoTempoEspecial** `H20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TotalAcrescimoTempoEspecial-(AnosAcrescimoTempoEspecial*360)-(MesesAcrescimoTempoEspecial*30){% endhighlight %}





* * *

##### **DiasDER** `H27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E27-(F27*360)-(G27*30){% endhighlight %}





* * *

##### **DiasDERReafirmada1** `H28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E28);E28-(F28*360)-(G28*30);""){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **DiasDERReafirmada2** `H29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E29);E29-(F29*360)-(G29*30);""){% endhighlight %}





* * *

##### **DiasDPE** `H22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E22-(F22*360)-(G22*30){% endhighlight %}



> Dias apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasDPL** `H26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E26-(F26*360)-(G26*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DER

* * *

##### **DiasFaltantesPedagio** `H24`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E24-(F24*360)-(G24*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **DiasPedagio** `H23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E23-(F23*360)-(G23*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasTCMinimo** `H25`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E25-(F25*360)-(G25*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados para efeito de tempo de contribuição até a DPL

* * *

##### **DireitoAoBeneficioDER** `L27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(BeneficioIntegralDER;AND(Especie=42;IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaExigida;TotalDiasDER>=TotalDiasTCMinimo);AND(Especie=41;IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaExigida)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na primeira data reafirmada

* * *

##### **DireitoAoBeneficioDERReafirmada1** `L28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);OR(BeneficioIntegralDERReafirmada1;AND(Especie=42;IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaExigida;TotalDiasDERReafirmada1>=TotalDiasTCMinimo);AND(Especie=41;IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaExigida));""){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na segunda data reafirmada

* * *

##### **DireitoAoBeneficioDERReafirmada2** `L29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);OR(BeneficioIntegralDERReafirmada2;AND(Especie=42;IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaExigida;TotalDiasDERReafirmada2>=TotalDiasTCMinimo);AND(Especie=41;IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaExigida));""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **DireitoAoBeneficioDPE** `L22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=AND(Especie=42;IdadeDPE>=IdadeMinima;TotalCarenciaDPE>=CarenciaMinimaDPE;TotalDiasDPE>=TotalDiasTCMinimo){% endhighlight %}


~~~
0%
~~~




* * *

##### **DireitoAoBeneficioDPL** `L26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(BeneficioIntegralDPL;AND(Especie=42;IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaExigida;TotalDiasDPL>=TotalDiasTCMinimo);AND(Especie=41;IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaExigida)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na DER.
Adicionado critério para aposentadoria por idade (alterado em 21/10/2017)


* * *

##### **IdadeDER** `C27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DER)/360{% endhighlight %}


~~~
0
~~~


> Idade na data da primeira reafirmação

* * *

##### **IdadeDERReafirmada1** `C28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);DAYS360(DataNascimento;DERReafirmada1)/360;""){% endhighlight %}


~~~
0
~~~


> Idade na data da segunda reafirmação

* * *

##### **IdadeDERReafirmada2** `C29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);DAYS360(DataNascimento;DERReafirmada2)/360;""){% endhighlight %}


~~~
0
~~~




* * *

##### **IdadeDPE** `C22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DPE)/360{% endhighlight %}


~~~
0
~~~




* * *

##### **IdadeDPL** `C26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DPL-1)/360{% endhighlight %}


~~~
0
~~~


> Idade na DER

* * *

##### **MesesAcrescimoTempoEspecial** `G20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((TotalAcrescimoTempoEspecial-(AnosAcrescimoTempoEspecial*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **MesesDER** `G27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E27-(F27*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **MesesDERReafirmada1** `G28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E28);ROUNDDOWN((E28-(F28*360))/30);""){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **MesesDERReafirmada2** `G29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E29);ROUNDDOWN((E29-(F29*360))/30);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **MesesDPE** `G22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E22-(F22*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesDPL** `G26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E26-(F26*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DER

* * *

##### **MesesFaltantesComPedagio** `G24`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E24-(F24*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **MesesPedagio** `G23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E23-(F23*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesTCMinimo** `G25`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E25-(F25*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DPL

* * *

##### **PontosDER** `D27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(OR(Especie=42;Especie=57);DER>=VigenciaPontos);(TotalDiasDER/360)+IdadeDER+IF(Especie=57;5;0);""){% endhighlight %}


~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até primeira data reafirmada

* * *

##### **PontosDERReafirmada1** `D28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(OR(Especie=42;Especie=57);DERReafirmada1>=VigenciaPontos);(TotalDiasDERReafirmada1/360)+IdadeDERReafirmada1+IF(Especie=57;5;0);""){% endhighlight %}


~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até segunda data reafirmada

* * *

##### **PontosDERReafirmada2** `D29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(OR(Especie=42;Especie=57);DERReafirmada2>=VigenciaPontos);(TotalDiasDERReafirmada2/360)+IdadeDERReafirmada2+IF(Especie=57;5;0);""){% endhighlight %}


~~~
0
~~~




* * *

##### **ResultadoAnosBIAcidentario** `F15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasBIAcidentario/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosBIIntercalado** `F16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasBIIntercalado/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosBINaoIntercalado** `F17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasBINaoIntercalado/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCAdicionadoComum** `F4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCAdicionadoComum/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCAdicionadoConvertido** `F5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCAdicionadoConvertido/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCComum** `F8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCComum/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCComumEspecial** `F19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCComumEspecial/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCConvertido** `F21`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCConvertido/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCDeficienciaGrave** `F14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCDeficienciaGrave/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCDeficienciaLeve** `F12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCDeficienciaLeve/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCDeficienciaModerada** `F13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCDeficienciaModerada/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCDiscriminadoComum** `F2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCDiscriminadoComum/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição (sem conversão)

* * *

##### **ResultadoAnosTCDiscriminadoConvertido** `F3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCDiscriminadoConvertido/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DER (após conversão)

* * *

##### **ResultadoAnosTCEspecial15** `F9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCEspecial15/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCEspecial20** `F10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCEspecial20/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCEspecial25** `F11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCEspecial25/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCNaoComputado** `F7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCNaoComputado/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoCarenciaSimples** `I19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(CarenciaTCDiscriminado;CarenciaTCAdicionado){% endhighlight %}





* * *

##### **ResultadoCarenciaTCDiscriminado** `I2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(CarenciaTCDiscriminado){% endhighlight %}





* * *

##### **ResultadoDiasBIAcidentario** `H15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasBIAcidentario-(ResultadoAnosBIAcidentario*360)-(ResultadoMesesBIAcidentario*30){% endhighlight %}





* * *

##### **ResultadoDiasBIIntercalado** `H16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasBIIntercalado-(ResultadoAnosBIIntercalado*360)-(ResultadoMesesBIIntercalado*30){% endhighlight %}





* * *

##### **ResultadoDiasBINaoIntercalado** `H17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasBINaoIntercalado-(ResultadoAnosBINaoIntercalado*360)-(ResultadoMesesBINaoIntercalado*30){% endhighlight %}





* * *

##### **ResultadoDiasTCAdicionadoComum** `H4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCAdicionadoComum-(ResultadoAnosTCAdicionadoComum*360)-(ResultadoMesesTCAdicionadoComum*30){% endhighlight %}





* * *

##### **ResultadoDiasTCAdicionadoConvertido** `H5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCAdicionadoConvertido-(ResultadoAnosTCAdicionadoConvertido*360)-(ResultadoMesesTCAdicionadoConvertido*30){% endhighlight %}





* * *

##### **ResultadoDiasTCComum** `H8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCComum-(ResultadoAnosTCComum*360)-(ResultadoMesesTCComum*30){% endhighlight %}





* * *

##### **ResultadoDiasTCComumEspecial** `H19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCComumEspecial-(ResultadoAnosTCComumEspecial*360)-(ResultadoMesesTCComumEspecial*30){% endhighlight %}





* * *

##### **ResultadoDiasTCConvertido** `H21`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCConvertido-(ResultadoAnosTCConvertido*360)-(ResultadoMesesTCConvertido*30){% endhighlight %}





* * *

##### **ResultadoDiasTCDeficienciaGrave** `H14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDeficienciaGrave-(ResultadoAnosTCDeficienciaGrave*360)-(ResultadoMesesTCDeficienciaGrave*30){% endhighlight %}





* * *

##### **ResultadoDiasTCDeficienciaLeve** `H12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDeficienciaLeve-(ResultadoAnosTCDeficienciaLeve*360)-(ResultadoMesesTCDeficienciaLeve*30){% endhighlight %}





* * *

##### **ResultadoDiasTCDeficienciaModerada** `H13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDeficienciaModerada-(ResultadoAnosTCDeficienciaModerada*360)-(ResultadoMesesTCDeficienciaModerada*30){% endhighlight %}





* * *

##### **ResultadoDiasTCDiscriminadoComum** `H2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDiscriminadoComum-(ResultadoAnosTCDiscriminadoComum*360)-(ResultadoMesesTCDiscriminadoComum*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição (sem conversão)

* * *

##### **ResultadoDiasTCDiscriminadoConvertido** `H3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDiscriminadoConvertido-(ResultadoAnosTCDiscriminadoConvertido*360)-(ResultadoMesesTCDiscriminadoConvertido*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DER (após conversão)

* * *

##### **ResultadoDiasTCEspecial15** `H9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCEspecial15-(ResultadoAnosTCEspecial15*360)-(ResultadoMesesTCEspecial15*30){% endhighlight %}





* * *

##### **ResultadoDiasTCEspecial20** `H10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCEspecial20-(ResultadoAnosTCEspecial20*360)-(ResultadoMesesTCEspecial20*30){% endhighlight %}





* * *

##### **ResultadoDiasTCEspecial25** `H11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCEspecial25-(ResultadoAnosTCEspecial25*360)-(ResultadoMesesTCEspecial25*30){% endhighlight %}





* * *

##### **ResultadoDiasTCNaoComputado** `H7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCNaoComputado-(ResultadoAnosTCNaoComputado*360)-(ResultadoMesesTCNaoComputado*30){% endhighlight %}





* * *

##### **ResultadoMesesBIAcidentario** `G15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasBIAcidentario-(ResultadoAnosBIAcidentario*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesBIIntercalado** `G16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasBIIntercalado-(ResultadoAnosBIIntercalado*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesBINaoIntercalado** `G17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasBINaoIntercalado-(ResultadoAnosBINaoIntercalado*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCAdicionadoComum** `G4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCAdicionadoComum-(ResultadoAnosTCAdicionadoComum*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCAdicionadoConvertido** `G5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCAdicionadoConvertido-(ResultadoAnosTCAdicionadoConvertido*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCComum** `G8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCComum-(ResultadoAnosTCComum*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCComumEspecial** `G19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCComumEspecial-(ResultadoAnosTCComumEspecial*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCConvertido** `G21`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCConvertido-(ResultadoAnosTCConvertido*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCDeficienciaGrave** `G14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCDeficienciaGrave-(ResultadoAnosTCDeficienciaGrave*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCDeficienciaLeve** `G12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCDeficienciaLeve-(ResultadoAnosTCDeficienciaLeve*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCDeficienciaModerada** `G13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCDeficienciaModerada-(ResultadoAnosTCDeficienciaModerada*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCDiscriminadoComum** `G2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCDiscriminadoComum-(ResultadoAnosTCDiscriminadoComum*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição (sem conversão)

* * *

##### **ResultadoMesesTCDiscriminadoConvertido** `G3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCDiscriminadoConvertido-(ResultadoAnosTCDiscriminadoConvertido*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DER (após conversão)

* * *

##### **ResultadoMesesTCEspecial15** `G9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCEspecial15-(ResultadoAnosTCEspecial15*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCEspecial20** `G10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCEspecial20-(ResultadoAnosTCEspecial20*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCEspecial25** `G11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCEspecial25-(ResultadoAnosTCEspecial25*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCNaoComputado** `G7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCNaoComputado-(ResultadoAnosTCNaoComputado*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalCarencia** `K19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(ResultadoCarenciaSimples;TotalAcrescimosCarencia){% endhighlight %}





* * *

##### **ResultadoTotalDiasBIAcidentario** `E15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="8"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasBIIntercalado** `E16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="9"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasBINaoIntercalado** `E17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="10"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCAdicionadoComum** `E4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCAdicionadoConvertido** `E5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCComum** `E8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="1"));0){% endhighlight %}


~~~
0.###############
~~~


> Alteração para somar apenas os dias, mas não o valor do fator. (Alterado em 20/02/18)

* * *

##### **ResultadoTotalDiasTCComumEspecial** `E19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCDiscriminadoProcessado;TotalDiasTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCConvertido** `E21`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCDiscriminadoProcessado;TotalDiasConvertidosTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCDeficienciaGrave** `E14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="5"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCDeficienciaLeve** `E12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="7"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCDeficienciaModerada** `E13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="6"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCDiscriminadoComum** `E2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCDiscriminadoProcessado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCDiscriminadoConvertido** `E3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCDiscriminadoProcessado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCEspecial15** `E9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="4"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCEspecial20** `E10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="3"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCEspecial25** `E11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="2"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalDiasTCNaoComputado** `E7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IFERROR(SUM(FILTER(TotalDiasTCDiscriminadoProcessado;

MID(ClassificacaoTCDiscriminado;1;1)="0"));0){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalAcrescimoTempoEspecial** `E20`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=(ResultadoTotalDiasTCDiscriminadoConvertido + ResultadoTotalDiasTCAdicionadoConvertido) - (ResultadoTotalDiasTCDiscriminadoComum + ResultadoTotalDiasTCAdicionadoComum){% endhighlight %}





* * *

##### **TotalAcrescimosCarencia** `J19`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(Acrescimos){% endhighlight %}





* * *

##### **TotalAcrescimosDER** `J27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;Acrescimos){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a primeira data reafirmada

* * *

##### **TotalAcrescimosDERReafirmada1** `J28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;Acrescimos);""){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a segunda data reafirmada

* * *

##### **TotalAcrescimosDERReafirmada2** `J29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;Acrescimos);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalAcrescimosDPE** `J22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;Acrescimos){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalAcrescimosDPL** `J26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;Acrescimos){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a DER

* * *

##### **TotalCarenciaDER** `K27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDER+TotalAcrescimosDER{% endhighlight %}



> Carência (número de contribuições) apuradas até a primeira data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada1** `K28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);CarenciaDERReafirmada1+TotalAcrescimosDERReafirmada1;""){% endhighlight %}



> Carência (número de contribuições) apuradas até a segunda data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada2** `K29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada2+TotalAcrescimosDERReafirmada2;""){% endhighlight %}





* * *

##### **TotalCarenciaDPE** `K22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDPE+TotalAcrescimosDPE{% endhighlight %}





* * *

##### **TotalCarenciaDPL** `K26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDPL+TotalAcrescimosDPL{% endhighlight %}



> Carência (número de contribuições) apuradas até a DER (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalDiasDER** `E27`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DER;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<="&DER;TotalDiasConvertidosTCAdicionado)

{% endhighlight %}



> Tempo de contribuição apurado até primeira data reafirmada (em dias)

* * *

##### **TotalDiasDERReafirmada1** `E28`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada1;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}



> Tempo de contribuição apurado até segunda data reafirmada (em dias)

* * *

##### **TotalDiasDERReafirmada2** `E29`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada2;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada2;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}





* * *

##### **TotalDiasDPE** `E22`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo referente ao pedágio a ser cumprido (em dias)

* * *

##### **TotalDiasDPL** `E26`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPL;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo de contribuição apurado até DER (em dias)

* * *

##### **TotalDiasFaltantesComPedagio** `E24`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)+TotalDiasPedagio)-TotalDiasDPE{% endhighlight %}



> Tempo mínimo de contribuição exigido para concessão do benefício aposentadoria por tempo de contribuição

* * *

##### **TotalDiasPedagio** `E23`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)-TotalDiasDPE)*0,4{% endhighlight %}



> Tempo de contribuição faltante para cumprimento dos requisitos para concessão de aposentadoria proporcional na Emenda Constitucional nº 20 de 1.998 (considerado o pedágio)