---
description: 說明DIL.tools命名空間中的方法。 這些實用程式功能可幫助您執行特定任務。
seo-description: 說明DIL.tools命名空間中的方法。 這些實用程式功能可幫助您執行特定任務。
seo-title: DIL 工具
solution: Audience Manager
title: DIL 工具
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL實作
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 5%

---

# DIL 工具

說明`DIL.tools`命名空間中的方法。 這些實用程式功能可幫助您執行特定任務。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

傳回用來存取目前頁面的搜尋詞。

<!-- 

r_dil_get_search_referrer.xml

 -->

### `getSearchReferrer`的用途

在DIL中， `getSearchReferrer`傳回用來存取您網站的搜尋結果（名稱和關鍵字）。 您可以傳遞特定搜尋詞至此函式，或讓其依預設對`document.referrer`搜尋支援的搜尋引擎（[!DNL AOL]、[!DNL Ask]、[!DNL Bing]、[!DNL Google]及[!DNL Yahoo]）。

### 函式簽名

函式簽名：`DIL.tools.getSearchReferrer(uri, initConfig)`

### 函式參數

`getSearchReferrer` 接受：

* *`{string}`*: *（選用）* 包含搜尋URL的字串(若未定義則 `document.referrer` 使用)。
* *`{object}`*: *（選用）* 包含、或的組態 `hostPattern`的 `queryParam`物件 `queryPattern`。

和傳回：

* `{object}` 包含有效名稱和關鍵字的對象。

### 範例

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> 搜尋類型 </th> 
   <th> 說明 </th> 
   <th> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 預設搜尋</td> 
   <td> 傳回AOL、Ask、Bing、Google和Yahoo搜尋引擎使用的關鍵字搜尋詞。 </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>傳入自訂URL</td> 
   <td>根據自訂URL傳回搜尋反向連結。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>將URL主機名稱與自訂規則運算式相符</b></td> 
   <td> 傳入自訂規則運算式以符合反向連結URL的主機名稱。 </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>使用自訂規則運算式比對搜尋模式</b> </td> 
   <td> 傳入自訂規則運算式以執行自訂搜尋。 </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## dencutURI

將統一資源標識符([!DNL URI])拆分到其組成元件中：`hash`、`host`、`href`、`pathname`、`protocol`、`search`和`[!DNL uriParams]`。

<!-- 

r_dil_decompose.xml

 -->

函式簽名：`DIL.tools.decomposeURI`

### 函式參數

`decomposeURI` 接受：

* *`uri {string}`*: *（選用）* 包含URI的字串。若未指定，則預設為`document.location.href`。

和傳回：

* *`{object}`*:包含有效名稱和關鍵字的對象。

### 程式碼範例


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

搜尋網頁上中繼標籤中定義的特定內容，並在物件中傳回該資料。

<!-- 

r_dil_get_metatags.xml

 -->

### 函式簽名

函式簽名：`DIL.tools.getMetaTags( 1 or more parameters)`

### 函式參數

`getMetaTags` 接受要搜索的一個或多個名稱參數（字串類型）。它會傳回由機碼值組組成的物件。

### 程式碼範例

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
