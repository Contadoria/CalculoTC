---
title: UDF_URL
category: Funções Customizadas
order: 3
---
{% highlight javascript linenos %}
/**
* Retorna o url da planilha.
*
* @param {Array} dummy Parâmetro fajuto, apenas para forçar a atualização.
* @return {string} O url. 
*
* @customfunction
*/
function jef_URL(dummy) {
  return SpreadsheetApp.getActiveSpreadsheet().getUrl();
}

{% endhighlight %}