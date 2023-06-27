---
description: 說明DIL.tools名稱空間中的方法。 這些公用程式功能可協助您執行特定工作。
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL 工具
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---

# DIL 工具

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

說明中的方法 `DIL.tools` 名稱空間。 這些公用程式功能可協助您執行特定工作。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

傳回用來存取目前頁面的搜尋字詞。

<!-- 

r_dil_get_search_referrer.xml

 -->

### 用途 `getSearchReferrer`

在DIL中， `getSearchReferrer` 傳回用來存取您的網站的搜尋結果（名稱和關鍵字）。 您可以將特定搜尋詞傳入此函式，或讓此函式搜尋支援的搜尋引擎( [!DNL AOL]， [!DNL Ask]， [!DNL Bing]， [!DNL Google]、和 [!DNL Yahoo])對 `document.referrer` 依預設。

### 函式簽章

函式簽章： `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函式引數

`getSearchReferrer` 接受：

* *`{string}`*： *（可選）* 包含搜尋URL的字串(使用 `document.referrer` （如果未定義）。
* *`{object}`*： *（可選）* 一個物件，其中包含下列專案的設定： `hostPattern`， `queryParam`，或 `queryPattern`.

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
   <td> <b>比對URL主機名稱與自訂規則運算式</b></td> 
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
   <td> <b>比對搜尋模式與自訂規則運算式</b> </td> 
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

## decompositouri

分解統一資源識別碼( [!DNL URI])作為其組成元件： `hash`， `host`， `href`， `pathname`， `protocol`， `search`、和 `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

函式簽章： `DIL.tools.decomposeURI`

### 函式引數

`decomposeURI` 接受：

* *`uri {string}`*： *（可選）* 包含URI的字串。 預設為 `document.location.href` 若未指定。

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

搜尋在網頁上的中繼標籤中定義的特定內容，並在物件中傳回該資料。

<!-- 

r_dil_get_metatags.xml

 -->

### 函式簽章

函式簽章： `DIL.tools.getMetaTags( 1 or more parameters)`

### 函式引數

`getMetaTags` 接受要搜尋的一或多個名稱引數（字串型別）。 它會傳回由索引鍵值配對組成的物件。

### 程式碼範例

<pre class="javascript"><code>
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
