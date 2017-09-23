---
title: Resultado
category: Processamento
order: 3
---

##### **AnosDER** `F10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E10/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DER

* * *

##### **AnosDERReafirmada1** `F11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E11);ROUNDDOWN(E11/360);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **AnosDERReafirmada2** `F12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E12);ROUNDDOWN(E12/360);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **AnosDPE** `F5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E5/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosDPL** `F9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E9/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para efeito de tempo de contribuição até a DPL

* * *

##### **AnosFaltantesComPedagio** `F7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E7/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosPedagio** `F6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E6/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **AnosTCMinimo** `F8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E8/360){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Anos apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **BeneficioIntegralDER** `M10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=TotalDiasDER>=TCAposentadoriaIntegral*360{% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na DER

* * *

##### **BeneficioIntegralDERReafirmada1** `M11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=TotalDiasDERReafirmada1>=TCAposentadoriaIntegral*360{% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na primeira data reafirmada

* * *

##### **BeneficioIntegralDERReafirmada2** `M12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=TotalDiasDERReafirmada2>=TCAposentadoriaIntegral*360{% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na segunda data reafirmada

* * *

##### **BeneficioIntegralDPE** `M5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=TotalDiasDPE>=TCAposentadoriaIntegral*360{% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral até a Emenda Constitucional nº 20 de 1.998

* * *

##### **BeneficioIntegralDPL** `M9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=TotalDiasDPL>=TCAposentadoriaIntegral*360{% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão de aposentadoria integral na DPL

* * *

##### **CarenciaDER** `I10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DER;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a DER

* * *

##### **CarenciaDERReafirmada1** `I11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;CarenciaTCAdicionado);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a primeira data reafirmada

* * *

##### **CarenciaDERReafirmada2** `I12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DERReafirmada2;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<="&DERReafirmada2;CarenciaTCAdicionado);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a segunda data reafirmada

* * *

##### **CarenciaDPE** `I5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a Emenda Constitucional nº 20 de 1.998

* * *

##### **CarenciaDPL** `I9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;CarenciaTCDiscriminado)+SUMIF(LimitesTCAdicionado;"<"&DPL;CarenciaTCAdicionado){% endhighlight %}



> Carência (número de contribuições) apuradas até a DPL

* * *

##### **CoeficienteDER** `N10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(DireitoAoBeneficioDER;IF(BeneficioIntegralDER;1;MIN(((ROUNDDOWN(TotalDiasDER/360)-ROUNDDOWN(TotalDiasTCMinimo/360))*0,05)+0,7;1));""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Coeficiente de cálculo apurado na DER

* * *

##### **CoeficienteDERReafirmada1** `N11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);IF(BeneficioIntegralDERReafirmada1;1;IF(DireitoAoBeneficioDERReafirmada1;MIN((ROUNDDOWN((TotalDiasDERReafirmada1-TotalDiasTCMinimo)/360)*0,05)+0,7;1);""));""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Coeficiente de cálculo apurado na primeira data reafirmada

* * *

##### **CoeficienteDERReafirmada2** `N12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);IF(BeneficioIntegralDERReafirmada2;1;IF(DireitoAoBeneficioDERReafirmada2;MIN((ROUNDDOWN((TotalDiasDERReafirmada2-TotalDiasTCMinimo)/360)*0,05)+0,7;1);""));""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Coeficiente de cálculo apurado na segunda data reafirmada

* * *

##### **CoeficienteDPE** `N5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(DireitoAoBeneficioDPE;IF(BeneficioIntegralDPE;1;MIN((ROUNDDOWN((TotalDiasDPE-TotalDiasTCMinimoDPE)/360)*0,06)+0,7;1));""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Coeficiente de cálculo apurado até a Emenda Constitucional nº 20 de 1.998

* * *

##### **CoeficienteDPL** `N9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(DireitoAoBeneficioDPL;IF(BeneficioIntegralDPL;1;MIN(((ROUNDDOWN(TotalDiasDPL/360)-ROUNDDOWN(TotalDiasTCMinimo/360))*0,05)+0,7;1));""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Coeficiente de cálculo apurado na DPL

* * *

##### **DPE** `B5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}

+ **Formato**:
~~~
d/m/yyyy
~~~


> Data da publicação da Emenda Constitucional nº 20 de 1.998

* * *

##### **DiasDER** `H10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=E10-(F10*360)-(G10*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DER

* * *

##### **DiasDERReafirmada1** `H11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E11);E11-(F11*360)-(G11*30);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Dias apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **DiasDERReafirmada2** `H12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E12);E12-(F12*360)-(G12*30);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Dias apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **DiasDPE** `H5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=E5-(F5*360)-(G5*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasDPL** `H9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=E9-(F9*360)-(G9*30){% endhighlight %}



> Dias apurados para efeito de tempo de contribuição até a DPL

* * *

##### **DiasFaltantesPedagio** `H7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E7-(F7*360)-(G7*30)){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Dias apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasPedagio** `H6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E6-(F6*360)-(G6*30)){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Dias apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **DiasTCMinimo** `H8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN(E8-(F8*360)-(G8*30)){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Dias apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **DireitoAoBeneficioDER** `L10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=AND(IdadeDER>=IdadeMinima;TotalCarenciaDER>=CarenciaDER;TotalDiasDER>=TotalDiasTCMinimo){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na DER

* * *

##### **DireitoAoBeneficioDERReafirmada1** `L11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);AND(IdadeDERReafirmada1>=IdadeMinima;TotalCarenciaDERReafirmada1>=CarenciaDERReafirmada1;TotalDiasDERReafirmada1>=TotalDiasTCMinimo);""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na primeira data reafirmada

* * *

##### **DireitoAoBeneficioDERReafirmada2** `L12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);AND(IdadeDERReafirmada2>=IdadeMinima;TotalCarenciaDERReafirmada2>=CarenciaDERReafirmada2;TotalDiasDERReafirmada2>=TotalDiasTCMinimo);""){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na segunda data reafirmada

* * *

##### **DireitoAoBeneficioDPE** `L5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=AND(TotalCarenciaDPE>=CarenciaDPE;TotalDiasDPE>=TotalDiasTCMinimoDPE){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria até a Emenda Constitucional nº 20 de 1.998

* * *

##### **DireitoAoBeneficioDPL** `L9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=AND(IdadeDPL>=IdadeMinima;TotalCarenciaDPL>=CarenciaDPL;TotalDiasDPL>=TotalDiasTCMinimo){% endhighlight %}

+ **Formato**:
~~~
0%
~~~


> Verificação dos requisitos para concessão da aposentadoria na DPL

* * *

##### **IdadeDER** `C10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=DAYS360(DataNascimento;DER-1)/360{% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Idade na DER

* * *

##### **IdadeDERReafirmada1** `C11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);DAYS360(DataNascimento;DERReafirmada1-1)/360;""){% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Idade na data da primeira reafirmação

* * *

##### **IdadeDERReafirmada2** `C12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);DAYS360(DataNascimento;DERReafirmada2-1)/360;""){% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Idade na data da segunda reafirmação

* * *

##### **IdadeDPE** `C5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=DAYS360(DataNascimento;DPE)/360{% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Idade até a Emenda Constitucional nº 20 de 1.998

* * *

##### **IdadeDPL** `C9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=DAYS360(DataNascimento;DPL-1)/360{% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Idade na DPL

* * *

##### **MesesDER** `G10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E10-(F10*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DER

* * *

##### **MesesDERReafirmada1** `G11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E11);ROUNDDOWN((E11-(F11*360))/30);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a primeira data reafirmada

* * *

##### **MesesDERReafirmada2** `G12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(E12);ROUNDDOWN((E12-(F12*360))/30);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a segunda data reafirmada

* * *

##### **MesesDPE** `G5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E5-(F5*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesDPL** `G9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E9-(F9*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para efeito de tempo de contribuição até a DPL

* * *

##### **MesesFaltantesComPedagio** `G7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E7-(F7*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados referentes ao tempo mínimo necessário para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesPedagio** `G6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E6-(F6*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para cumprimento do pedágio exigido pela Emenda Constitucional nº 20 de 1.998.

* * *

##### **MesesTCMinimo** `G8`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=ROUNDDOWN((E8-(F8*360))/30){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Meses apurados para cumprimento de tempo mínimo para concessão de aposentadoria

* * *

##### **PontosDER** `D10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(AND(Especie=42;DER>=VigenciaPontos);(TotalDiasDER/360)+IdadeDER;""){% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até DER

* * *

##### **PontosDERReafirmada1** `D11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada1>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada1;""){% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até primeira data reafirmada

* * *

##### **PontosDERReafirmada2** `D12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(AND(Especie=42;DERReafirmada2>=VigenciaPontos);(TotalDiasDER/360)+IdadeDERReafirmada2;""){% endhighlight %}

+ **Formato**:
~~~
0.00
~~~


> Pontuação (tempo de contribuição + idade) até segunda data reafirmada

* * *

##### **TotalAcrescimosDER** `J10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DER;Acrescimos){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a DER

* * *

##### **TotalAcrescimosDERReafirmada1** `J11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;Acrescimos);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a primeira data reafirmada

* * *

##### **TotalAcrescimosDERReafirmada2** `J12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;Acrescimos);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a segunda data reafirmada

* * *

##### **TotalAcrescimosDPE** `J5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;Acrescimos){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a Emenda Constitucional nº 20 de 1.998

* * *

##### **TotalAcrescimosDPL** `J9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;Acrescimos){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Acréscimos da Lei 11.718/2008 até a DPL

* * *

##### **TotalCarenciaDER** `K10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=CarenciaDER+TotalAcrescimosDER{% endhighlight %}



> Carência (número de contribuições) apuradas até a DER (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada1** `K11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada1+TotalAcrescimosDERReafirmada1;""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a primeira data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDERReafirmada2** `K12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);CarenciaDERReafirmada2+TotalAcrescimosDERReafirmada2;""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Carência (número de contribuições) apuradas até a segunda data reafirmada (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDPE** `K5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=CarenciaDPE+TotalAcrescimosDPE{% endhighlight %}



> Carência (número de contribuições) apuradas até a Emenda Constitucional nº 20 de 1.998 (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalCarenciaDPL** `K9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=CarenciaDPL+TotalAcrescimosDPL{% endhighlight %}



> Carência (número de contribuições) apuradas até a DPL (após acréscimos da Lei 11.718/2008)

* * *

##### **TotalDiasDER** `E10`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<="&DER;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<="&DER;TotalDiasConvertidosTCAdicionado)

{% endhighlight %}



> Tempo de contribuição apurado até DER (em dias)

* * *

##### **TotalDiasDERReafirmada1** `E11`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada1);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada1;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada1;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Tempo de contribuição apurado até primeira data reafirmada (em dias)

* * *

##### **TotalDiasDERReafirmada2** `E12`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=IF(ISNUMBER(DERReafirmada2);SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DERReafirmada2;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DERReafirmada2;TotalDiasConvertidosTCAdicionado);""){% endhighlight %}

+ **Formato**:
~~~
0.###############
~~~


> Tempo de contribuição apurado até segunda data reafirmada (em dias)

* * *

##### **TotalDiasDPE** `E5`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPEMaisUm;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPEMaisUm;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo de contribuição apurado até Emenda Constitucional nº de 1.998 (em dias)

* * *

##### **TotalDiasDPL** `E9`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=SUMIF(DataFinalTCDiscriminadoProcessado;"<"&DPL;TotalDiasConvertidosTCDiscriminadoProcessado)+SUMIF(LimitesTCAdicionado;"<"&DPL;TotalDiasConvertidosTCAdicionado){% endhighlight %}



> Tempo de contribuição apurado até DPL (em dias)

* * *

##### **TotalDiasFaltantesComPedagio** `E7`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)+TotalDiasPedagio)-TotalDiasDPE{% endhighlight %}



> Tempo de contribuição faltante para cumprimento dos requisitos para concessão de aposentadoria proporcional na Emenda Constitucional nº 20 de 1.998 (considerado o pedágio)

* * *

##### **TotalDiasPedagio** `E6`{: style="background-color: lightgrey; color: black; border-radius: 5px; padding:3px;"}
+ **Fórmula**:
{% highlight erlang %}=((IF(Sexo="Mulher";25;30)*360)-TotalDiasDPE)*0,4{% endhighlight %}



> Tempo referente ao pedágio a ser cumprido (em dias)