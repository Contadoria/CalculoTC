---
title: Resultado
category: Processamento
order: 3
---

##### **AnosAcrescimoTempoEspecial** `F9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(TotalAcrescimoTempoEspecial/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **AnosDER** `F16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E16/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **AnosDERReafirmada1** `F17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E17);ROUNDDOWN(E17/360);""){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **AnosDERReafirmada2** `F18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E18);ROUNDDOWN(E18/360);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **AnosDPE** `F11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E11/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosDPL** `F15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E15/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DER

* * *

##### **AnosFaltantesComPedagio** `F13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E13/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **AnosPedagio** `F12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E12/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosTCMinimo** `F14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E14/360){% endhighlight %}


~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DPL

* * *

##### **BeneficioIntegralDER** `M16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDER>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDER>=360)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na primeira data reafirmada

* * *

##### **BeneficioIntegralDERReafirmada1** `M17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);OR(AND(Especie=42;TotalDiasDERReafirmada1>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDERReafirmada1>=360));""){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na segunda data reafirmada

* * *

##### **BeneficioIntegralDERReafirmada2** `M18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);OR(AND(Especie=42;TotalDiasDERReafirmada2>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDERReafirmada2>=360));""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **BeneficioIntegralDPE** `M11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDPE>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDPE>=360)){% endhighlight %}


~~~
0%
~~~




* * *

##### **BeneficioIntegralDPL** `M15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(AND(Especie=42;TotalDiasDPL>=TCAposentadoriaIntegral*360);AND(Especie=41;CarenciaDPL>=360)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na DER.
Adicionado critério para aposentadoria por idade (alterado em 21/10/2017)

* * *

##### **CarenciaDER** `I16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DER;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DER;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a primeira data reafirmada

* * *

##### **CarenciaDERReafirmada1** `I17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;CarenciaTCAdicionado);""){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a segunda data reafirmada

* * *

##### **CarenciaDERReafirmada2** `I18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada2;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DERReafirmada2;CarenciaTCAdicionado);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **CarenciaDPE** `I11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;CarenciaTCAdicionado){% endhighlight %}





* * *

##### **CarenciaDPL** `I15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPL;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a DER

**18/10/2017**: alterado de "<" para "<="

* * *

##### **CoeficienteDER** `N16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(DireitoAoBeneficioDER;IF(BeneficioIntegralDER;1;IF(Especie=42;MIN((ROUNDDOWN((TotalDiasDER-TotalDiasTCMinimo)/360)*0,05)+0,7;1);IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDER/12)*0,01)+0,7;1))));""){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na primeira data reafirmada

* * *

##### **CoeficienteDERReafirmada1** `N17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);IF(DireitoAoBeneficioDERReafirmada1;IF(BeneficioIntegralDERReafirmada1;1;IF(Especie=42;MIN((ROUNDDOWN((TotalDiasDERReafirmada1-TotalDiasTCMinimo)/360)*0,05)+0,7;1);IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDERReafirmada1/12)*0,01)+0,7;1);"")));"");""){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na segunda data reafirmada

* * *

##### **CoeficienteDERReafirmada2** `N18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);IF(DireitoAoBeneficioDERReafirmada2;IF(BeneficioIntegralDERReafirmada2;1;IF(Especie=42;MIN((ROUNDDOWN((TotalDiasDERReafirmada2-TotalDiasTCMinimo)/360)*0,05)+0,7;1);IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDERReafirmada2/12)*0,01)+0,7;1);"")));"");""){% endhighlight %}


~~~
0%
~~~




* * *

##### **CoeficienteDPE** `N11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DireitoAoBeneficioDPE);IF(BeneficioIntegralDPE;1;MIN((ROUNDDOWN((TotalDiasDPE-TotalDiasTCMinimoDPE)/360)*0,06)+0,7;1));""){% endhighlight %}


~~~
0%
~~~




* * *

##### **CoeficienteDPL** `N15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(DireitoAoBeneficioDPL;IF(BeneficioIntegralDPL;1;IF(Especie=42;MIN((ROUNDDOWN((TotalDiasDPL-TotalDiasTCMinimo)/360)*0,05)+0,7;1);IF(Especie=41;MIN((ROUNDDOWN(TotalCarenciaDPL/12)*0,01)+0,7;1))));""){% endhighlight %}


~~~
0%
~~~


> Coeficiente de cálculo apurado na DER.
Substituído (ARREDONDAR.PARA.BAIXO(TotalDiasDER/360)-ARREDONDAR.PARA.BAIXO(TotalDiasTCMinimo/360)) por ARREDONDAR.PARA.BAIXO((TotalDIasDER-TotalDiasMinimo)/360) (alterado em 20/10/2017).
Adicionado critério para aposentadoria por idade (alterado em 21/10/2017)

* * *

##### **DPE** `B11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}


~~~
dd/MM/yyyy
~~~




* * *

##### **DiasAcrescimoTempoEspecial** `H9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=TotalAcrescimoTempoEspecial-(AnosAcrescimoTempoEspecial*360)-(MesesAcrescimoTempoEspecial*30){% endhighlight %}





* * *

##### **DiasDER** `H16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E16-(F16*360)-(G16*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **DiasDERReafirmada1** `H17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E17);E17-(F17*360)-(G17*30);""){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **DiasDERReafirmada2** `H18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E18);E18-(F18*360)-(G18*30);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **DiasDPE** `H11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E11-(F11*360)-(G11*30){% endhighlight %}



> Dias apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasDPL** `H15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=E15-(F15*360)-(G15*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DER

* * *

##### **DiasFaltantesPedagio** `H13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E13-(F13*360)-(G13*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **DiasPedagio** `H12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E12-(F12*360)-(G12*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasTCMinimo** `H14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(E14-(F14*360)-(G14*30)){% endhighlight %}


~~~
0.###############
~~~


> Dias apurados para efeito de tempo de contribuição até a DPL

* * *

##### **DireitoAoBeneficioDER** `L16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(BeneficioIntegralDER;AND(Especie=42;IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaDER;TotalDiasDER>=TotalDiasTCMinimo);AND(Especie=41;IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaMinimaDER)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na primeira data reafirmada

* * *

##### **DireitoAoBeneficioDERReafirmada1** `L17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);OR(BeneficioIntegralDERReafirmada1;AND(Especie=42;IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaDERReafirmada1;TotalDiasDERReafirmada1>=TotalDiasTCMinimo);AND(Especie=41;IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaMinimaDERReafirmada1));""){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na segunda data reafirmada

* * *

##### **DireitoAoBeneficioDERReafirmada2** `L18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);OR(BeneficioIntegralDERReafirmada2;AND(Especie=42;IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaDERReafirmada2;TotalDiasDERReafirmada2>=TotalDiasTCMinimo);AND(Especie=41;IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaMinimaDERReafirmada2));""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **DireitoAoBeneficioDPE** `L11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=AND(Especie=42;IdadeDPE>=IdadeMinima;TotalCarenciaDPE>=CarenciaMinimaDPE;TotalDiasDPE>=TotalDiasTCMinimo){% endhighlight %}


~~~
0%
~~~




* * *

##### **DireitoAoBeneficioDPL** `L15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=OR(BeneficioIntegralDPL;AND(Especie=42;IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaDPL;TotalDiasDPL>=TotalDiasTCMinimo);AND(Especie=41;IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaMinimaDPL)){% endhighlight %}


~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na DER.
Adicionado critério para aposentadoria por idade (alterado em 21/10/2017)


* * *

##### **IdadeDER** `C16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DER-1)/360{% endhighlight %}


~~~
0
~~~


> Idade na data da primeira reafirmação

* * *

##### **IdadeDERReafirmada1** `C17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);DAYS360(DataNascimento;DERReafirmada1-1)/360;""){% endhighlight %}


~~~
0
~~~


> Idade na data da segunda reafirmação

* * *

##### **IdadeDERReafirmada2** `C18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);DAYS360(DataNascimento;DERReafirmada2-1)/360;""){% endhighlight %}


~~~
0
~~~




* * *

##### **IdadeDPE** `C11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DPE)/360{% endhighlight %}


~~~
0
~~~




* * *

##### **IdadeDPL** `C15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=DAYS360(DataNascimento;DPL-1)/360{% endhighlight %}


~~~
0
~~~


> Idade na DER

* * *

##### **MesesAcrescimoTempoEspecial** `G9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((TotalAcrescimoTempoEspecial-(AnosAcrescimoTempoEspecial*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **MesesDER** `G16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E16-(F16*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **MesesDERReafirmada1** `G17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E17);ROUNDDOWN((E17-(F17*360))/30);""){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **MesesDERReafirmada2** `G18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(E18);ROUNDDOWN((E18-(F18*360))/30);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **MesesDPE** `G11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E11-(F11*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesDPL** `G15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E15-(F15*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DER

* * *

##### **MesesFaltantesComPedagio** `G13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E13-(F13*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **MesesPedagio** `G12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E12-(F12*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesTCMinimo** `G14`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((E14-(F14*360))/30){% endhighlight %}


~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DPL

* * *

##### **PontosDER** `D16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DER>=VigenciaPontos);(TotalDiasDER/360)+IdadeDER;""){% endhighlight %}


~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até primeira data reafirmada

* * *

##### **PontosDERReafirmada1** `D17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada1>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada1;""){% endhighlight %}


~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até segunda data reafirmada

* * *

##### **PontosDERReafirmada2** `D18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada2>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada2;""){% endhighlight %}


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

##### **ResultadoAnosTCComum** `F6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCComum/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCComumEspecial** `F8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCComumEspecial/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoAnosTCConvertido** `F10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCConvertido/360){% endhighlight %}


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

##### **ResultadoAnosTCEspecial** `F7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN(ResultadoTotalDiasTCEspecial/360){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoCarenciaSimples** `I8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(CarenciaTCDiscriminado;CarenciaTCAdicionado){% endhighlight %}





* * *

##### **ResultadoCarenciaTCDiscriminado** `I2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(CarenciaTCDiscriminado){% endhighlight %}





* * *

##### **ResultadoDiasTCAdicionadoComum** `H4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCAdicionadoComum-(ResultadoAnosTCAdicionadoComum*360)-(ResultadoMesesTCAdicionadoComum*30){% endhighlight %}





* * *

##### **ResultadoDiasTCAdicionadoConvertido** `H5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCAdicionadoConvertido-(ResultadoAnosTCAdicionadoConvertido*360)-(ResultadoMesesTCAdicionadoConvertido*30){% endhighlight %}





* * *

##### **ResultadoDiasTCComum** `H6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCComum-(ResultadoAnosTCComum*360)-(ResultadoMesesTCComum*30){% endhighlight %}





* * *

##### **ResultadoDiasTCComumEspecial** `H8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCComumEspecial-(ResultadoAnosTCComumEspecial*360)-(ResultadoMesesTCComumEspecial*30){% endhighlight %}





* * *

##### **ResultadoDiasTCConvertido** `H10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCConvertido-(ResultadoAnosTCConvertido*360)-(ResultadoMesesTCConvertido*30){% endhighlight %}





* * *

##### **ResultadoDiasTCDiscriminadoComum** `H2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDiscriminadoComum-(ResultadoAnosTCDiscriminadoComum*360)-(ResultadoMesesTCDiscriminadoComum*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição (sem conversão)

* * *

##### **ResultadoDiasTCDiscriminadoConvertido** `H3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCDiscriminadoConvertido-(ResultadoAnosTCDiscriminadoConvertido*360)-(ResultadoMesesTCDiscriminadoConvertido*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DER (após conversão)

* * *

##### **ResultadoDiasTCEspecial** `H7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ResultadoTotalDiasTCEspecial-(ResultadoAnosTCEspecial*360)-(ResultadoMesesTCEspecial*30){% endhighlight %}


~~~
0
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

##### **ResultadoMesesTCComum** `G6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCComum-(ResultadoAnosTCComum*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCComumEspecial** `G8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCComumEspecial-(ResultadoAnosTCComumEspecial*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoMesesTCConvertido** `G10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCConvertido-(ResultadoAnosTCConvertido*360))/30){% endhighlight %}


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

##### **ResultadoMesesTCEspecial** `G7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=ROUNDDOWN((ResultadoTotalDiasTCEspecial-(ResultadoAnosTCEspecial*360))/30){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **ResultadoTotalCarencia** `K8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(ResultadoCarenciaSimples;TotalAcrescimosCarencia){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCAdicionadoComum** `E4`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCAdicionadoConvertido** `E5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCComum** `E6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(FILTER(TotalDiasTCDiscriminadoProcessado;FatorConversaoTCDiscriminadoProcessado=1)){% endhighlight %}



> Alteração para somar apenas os dias, mas não o valor do fator. (Alterado em 20/02/18)

* * *

##### **ResultadoTotalDiasTCComumEspecial** `E8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCDiscriminadoProcessado;TotalDiasTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCConvertido** `E10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCDiscriminadoProcessado;TotalDiasConvertidosTCAdicionado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCDiscriminadoComum** `E2`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasTCDiscriminadoProcessado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCDiscriminadoConvertido** `E3`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(TotalDiasConvertidosTCDiscriminadoProcessado){% endhighlight %}





* * *

##### **ResultadoTotalDiasTCEspecial** `E7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(FILTER(TotalDiasTCDiscriminadoProcessado;FatorConversaoTCDiscriminadoProcessado<>1)){% endhighlight %}


~~~
0
~~~


> Alteração para somar apenas os dias, mas não o valor do fator. (Alterado em 20/02/18)

* * *

##### **TotalAcrescimoTempoEspecial** `E9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=(ResultadoTotalDiasTCDiscriminadoConvertido + ResultadoTotalDiasTCAdicionadoConvertido) - (ResultadoTotalDiasTCDiscriminadoComum + ResultadoTotalDiasTCAdicionadoComum){% endhighlight %}





* * *

##### **TotalAcrescimosCarencia** `J8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUM(Acrescimos){% endhighlight %}





* * *

##### **TotalAcrescimosDER** `J16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;Acrescimos){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a primeira data reafirmada

* * *

##### **TotalAcrescimosDERReafirmada1** `J17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;Acrescimos);""){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a segunda data reafirmada

* * *

##### **TotalAcrescimosDERReafirmada2** `J18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;Acrescimos);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalAcrescimosDPE** `J11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;Acrescimos){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalAcrescimosDPL** `J15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;Acrescimos){% endhighlight %}


~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a DER

* * *

##### **TotalCarenciaDER** `K16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDER+TotalAcrescimosDER{% endhighlight %}



> Carência (número de contribuições) apuradas até a primeira data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada1** `K17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);CarenciaDERReafirmada1+TotalAcrescimosDERReafirmada1;""){% endhighlight %}


~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a segunda data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada2** `K18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada2+TotalAcrescimosDERReafirmada2;""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalCarenciaDPE** `K11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDPE+TotalAcrescimosDPE{% endhighlight %}





* * *

##### **TotalCarenciaDPL** `K15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=CarenciaDPL+TotalAcrescimosDPL{% endhighlight %}



> Carência (número de contribuições) apuradas até a DER (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalDiasDER** `E16`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DER;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<="&DER;TotalDiasConvertidosTCAdicionado)

{% endhighlight %}



> Tempo de contribuição apurado até primeira data reafirmada (em dias)

* * *

##### **TotalDiasDERReafirmada1** `E17`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}


~~~
0.###############
~~~


> Tempo de contribuição apurado até segunda data reafirmada (em dias)

* * *

##### **TotalDiasDERReafirmada2** `E18`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada2;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}


~~~
0.###############
~~~




* * *

##### **TotalDiasDPE** `E11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo referente ao pedágio a ser cumprido (em dias)

* * *

##### **TotalDiasDPL** `E15`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPL;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo de contribuição apurado até DER (em dias)

* * *

##### **TotalDiasFaltantesComPedagio** `E13`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)+TotalDiasPedagio)-TotalDiasDPE{% endhighlight %}



> Tempo mínimo de contribuição exigido para concessão do benefício aposentadoria por tempo de contribuição

* * *

##### **TotalDiasPedagio** `E12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)-TotalDiasDPE)*0,4{% endhighlight %}



> Tempo de contribuição faltante para cumprimento dos requisitos para concessão de aposentadoria proporcional na Emenda Constitucional nº 20 de 1.998 (considerado o pedágio)