---
description: 描述DIL.tools命名空間中的方法。 這些實用程式功能可幫助您執行特定任務。
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL 工具
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# DIL 工具

介紹中的方法 `DIL.tools` 命名空間。 這些實用程式功能可幫助您執行特定任務。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

返回用於訪問當前頁面的搜索詞。

<!-- 

r_dil_get_search_referrer.xml

 -->

### 目的 `getSearchReferrer`

在DIL, `getSearchReferrer` 返回用於訪問您的站點的搜索結果（名稱和關鍵字）。 您可以將特定搜索詞傳遞到此函式，或讓其搜索支援的搜索引擎( [!DNL AOL]。 [!DNL Ask]。 [!DNL Bing]。 [!DNL Google], [!DNL Yahoo]針對 `document.referrer` 預設值。

### 函式簽名

函式簽名： `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函式參數

`getSearchReferrer` 接受：

* *`{string}`*: *（可選）* 包含搜索URL的字串(使用 `document.referrer` 如果未定義)。
* *`{object}`*: *（可選）* 包含的對象 `hostPattern`。 `queryParam`或 `queryPattern`。

並返回：

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
   <td> 預設搜索</td> 
   <td> 返回AOL、Ask、Bing、Google和Yahoo搜索引擎使用的關鍵字搜索詞。 </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>傳遞自定義URL</td> 
   <td>根據自定義URL返回搜索引用者。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>將URL主機名與自定義規則運算式匹配</b></td> 
   <td> 以自定義規則運算式傳遞以匹配引用URL的主機名。 </td> 
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
   <td> <b>將搜索模式與自定義規則運算式匹配</b> </td> 
   <td> 以自定義規則運算式傳遞以執行自定義搜索。 </td> 
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

## 分解URI

分解統一資源標識符( [!DNL URI])到其組成元件中： `hash`。 `host`。 `href`。 `pathname`。 `protocol`。 `search`, `[!DNL uriParams]`。

<!-- 

r_dil_decompose.xml

 -->

函式簽名： `DIL.tools.decomposeURI`

### 函式參數

`decomposeURI` 接受：

* *`uri {string}`*: *（可選）* 包含URI的字串。 預設為 `document.location.href` 的子菜單。

並返回：

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

搜索網頁上元標籤中定義的特定內容並返回對象中的資料。

<!-- 

r_dil_get_metatags.xml

 -->

### 函式簽名

函式簽名： `DIL.tools.getMetaTags( 1 or more parameters)`

### 函式參數

`getMetaTags` 接受要搜索的一個或多個名稱參數（字串類型）。 它返回由鍵值對組成的對象。

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
