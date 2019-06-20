---
description: 說明DIL. tools命名空間中的方法。這些公用程式函數可協助您執行特定工作。
seo-description: 說明DIL. tools命名空間中的方法。這些公用程式函數可協助您執行特定工作。
seo-title: DIL工具
solution: Audience Manager
title: DIL工具
uuid: 2bc62ce2-16bd-4e80-b493-c816 BA643 b59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL工具

Describes methods in the `DIL.tools` namespace. 這些公用程式函數可協助您執行特定工作。

<!-- 

c_dil_functions.xml

 -->

## getSocialReferrer

傳回用於到達目前頁面的搜尋詞。

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default.

### 函數簽名

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函數參數

`getSearchReferrer` 接受：

* *`{string}`*： *(選用)* 包含搜尋URL的字串( `document.referrer` 若未定義)。
* *`{object}`*： *(可選)* 包含 `hostPattern`、 `queryParam`或 `queryPattern`.

並傳回：

* `{object}` 包含有效名稱和關鍵字的物件。

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
   <td> 傳回AOL、Ask、Bing、Google和Yahoo搜尋引擎所使用的關鍵字搜尋詞。 </td> 
   <td>
      <code>var&amp; amp；nbsp；結果與amp；nbsp；=&amp; amp；nbsp；DIL. tools. getPrevireer()；</code> 
  </td>
  </tr> 
  <tr> 
   <td>傳入自訂URL</td> 
   <td>根據自訂URL傳回搜尋反向連結。</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>搭配使用URL主機名稱與自訂Regex</b></td> 
   <td> 傳入自訂的regex，以符合反向連結URL的主機名稱。 </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>使用自訂Regex比對搜尋模式</b> </td> 
   <td> 傳入自訂Regex以執行自訂搜尋。 </td> 
   <td> 
    <code>
      var  results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## 解壓縮

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### 函數參數

`decomposeURI` 接受：

* *`uri {string}`*： *(選用)* 包含URI的字串。Defaults to `document.location.href` if not specified.

並傳回：

* *`{object}`*：包含有效名稱和關鍵字的物件。

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

搜尋網頁上meta標記中定義的特定內容，並將該資料傳回物件。

<!-- 

r_dil_get_metatags.xml

 -->

### 函數簽名

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### 函數參數

`getMetaTags` 接受一或多個名稱參數(字串類型)以供搜尋。它會傳回由索引鍵值配對組成的物件。

### 程式碼範例

<pre class="&ldquo;javascript&rdquo;"><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName'</i>，
containernSID： <i>containernSID</i> })；
DataAlb. api. documents(DIL. tools. GetMetaAgs('<i>application</i>'，'<i>keywords</i>'，'<i>description</i>')，'c_'). commit()；</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
