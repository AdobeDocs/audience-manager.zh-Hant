---
description: 特定DIL使用案例的程式碼範例和說明。
seo-description: 特定DIL使用案例的程式碼範例和說明。
seo-title: DIL使用案例和程式碼範例
solution: Audience Manager
title: DIL使用案例和程式碼範例
uuid: 27995c2d-65272-438e-af99-b5477 f090 ae9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

特定DIL使用案例的程式碼範例和說明。

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

建立物件變數，將頁面元素相關資訊傳送至Audience Manager。這對於一般資料收集很有用，或者是收集資料與Analytics變數的替代方法。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. 這些範例使用變數來放置平面清單或陣列中的資料元素。Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**保持值屬性的一致性**

在傳入資料時，請記住值屬性相同。例如，如果您有兩個具有不同值的相同索引鍵，最後一個機碼值配對的值優先於前述值物件。For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**範例1：將資料傳送為索引鍵值配對**

此基本範例會以關鍵值配對的形式傳送顏色和價格資料至Audience Manager。您的程式碼看起來類似下列：

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；
sample_ dil. api. documents({
c_ color：「blue」，
c_ price：「900」})；
sample_ dil. api. mit()；</code>
</pre>

**範例2：在物件中傳送資料**

此進階範例示範如何將物件中的資料傳送至Audience Manager。When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] 您的程式碼看起來類似下列：

<pre class="java"><code>var my_ object={
顏色：「blue」，
價格：「900」}；

var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；
//Load物件並附加「c_」至索引鍵值配對中的所有索引鍵，並傳送資料至AudienceManager。 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**範例3：在Array中傳送頁面資料**

In this case, the variable `my_object` uses an array to hold data. 此範例以上述建議方法傳入的資訊為基礎，但新增了其他圖層以容納產品類型和模型。您的程式碼看起來類似下列：

<pre class="java"><code>var my_ objects=[{{
顏色：「blue」，
價格：「900」}，{
type：「acura」，
模型：「tl」}]；

var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；

for(var i=0；i&lt; my_ objects. length；i++)//Load物件並附加「c_」至索引鍵值配對中的所有索引鍵。 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_贊_ this]
>
>* [訊號](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

擷取並傳送Audience Manager的反向連結URL。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>只有當使用者在具有類似通訊協定的頁面之間移動(HTTP與HTTPS)時，才會運作。例如，當您從安全網站導覽至另一個安全網站時，瀏覽器會保留反向連結URL。當您在安全和不安全的網站之間移動時，瀏覽器不會保留反向連結URL。This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**程式碼範例**

您的程式碼看起來類似下列：

<pre class="java"><code>var adobe_ dil= DIL. create({合作夥伴：<i>「合作夥伴名稱</i>」})；
adobe_ dil. api. documents({d_ referer：document. referrer}). mit()；</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

將搜尋引擎類型和關鍵字搜尋的相關資訊傳送至Audience Manager。

<!-- 

c_dil_search_engine_valid.xml

 -->

**支援的搜尋引擎**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

下列程式碼示範如何取得任何支援搜尋引擎的搜尋反向連結。In this case, let&#39;s assume a user searched on the term &quot;homes&quot; from [!DNL Google] Canada ( `www.google.ca`). 此程式碼可協助您擷取這些搜尋詞，並將其傳送至Audience Manager。

**基本程式碼**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出搜尋引擎代碼範例**

In this case, let&#39;s assume that a user searched for the term &quot;homes&quot; from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` 是 [必要首碼](../features/traits/trait-variable-prefixes.md) ，可將客戶定義的變數識別為Audience Manager。

<pre class="java"><code>var adobe_ dil= DIL. create({合作夥伴：<i>「合作夥伴名稱</i>」})；
var search_ referrer= DIL. tools. getPrevireer()；

if(search_ referrer&amp;&amp; search_ referrer.有效){
adobe_ dil. api. documents({
c_ se：se. name，
c_ st：se. keywords
}). mit()；
}</code>
</pre>

**未列出的搜尋引擎程式碼範例**

In this case, let&#39;s assume that a user searched for the term &quot;homes&quot; from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. 您的程式碼看起來類似下列：

<pre class="java"><code>var adobe_ dil= DIL. create({合作夥伴：<i>「合作夥伴名稱</i>」})；
var search_ referrer= DIL. tools. getPrevireer(document. referrer，{
hostPattern：/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

將值從索引鍵值配對關聯到另一個索引鍵。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. 客戶定義的資料用於定位在事件呼叫資料傳入的特定網站上。不過，有時您會想要在Audience Manager帳戶中所有屬性中提供此資訊。To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

例如，您可以從特定網站收集郵遞區號資料，但想要將其定位至所有Audience Manager屬性。To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**程式碼範例**

您的程式碼看起來類似下列：

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_贊_ this]
>
>* [關鍵變數的首碼需求](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

使用GTM標籤設定並提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. 建立新容器或開啓現有容器。
1. 新增標記至容器。
1. 開啓標籤以進行編輯和：

   * 命名標籤。
   * **[!UICONTROL Custom HTML Tag]** 從 **[!UICONTROL Tag Type]** 下拉式清單中選取。
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Click **[!UICONTROL Save]**.

1. 發佈容器。
1. 產生容器標記程式碼並將它放置在您的庫存上。

>[!MORE_贊_ this]
>
>* [Google Tag Manager說明中心](https://support.google.com/tagmanager#topic=3441530)

