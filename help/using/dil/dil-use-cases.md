---
description: 特定DIL使用案例的程式碼範例和說明。
seo-description: 特定DIL使用案例的程式碼範例和說明。
seo-title: DIL使用案例和程式碼範例
solution: Audience Manager
title: DIL使用案例和程式碼範例
uuid: 27995c2d-65272-438e-af99-b5477 f090 ae9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# DIL使用案例和程式碼範例{#dil-use-cases-and-code-samples}

特定DIL使用案例的程式碼範例和說明。

<!-- 

c_dil_use_case.xml

 -->

## 使用DIL傳送資料元素至Audience Manager {#send-data-elements-dil}

建立物件變數，將頁面元素相關資訊傳送至Audience Manager。這對於一般資料收集很有用，或者是收集資料與Analytics變數的替代方法。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

下列程式碼示範如何收集頁面資料並將 [!UICONTROL DIL]其傳送至Audience Manager。這些範例使用變數來放置平面清單或陣列中的資料元素。請記住，將變數傳入 [為關鍵值配對](../reference/key-value-pairs-explained.md)。此外，請注意 `c_` 索引鍵值對中索引鍵之前的首碼。此 [必要的首碼會](../features/traits/trait-variable-prefixes.md) 將資訊識別為使用者定義的資料。在第一個範例中，您需要手動附加 `c_` 索引鍵。在第二個範例中，自動為您 [!UICONTROL DIL] 執行此動作。

**保持值屬性的一致性**

在傳入資料時，請記住值屬性相同。例如，如果您有兩個具有不同值的相同索引鍵，最後一個機碼值配對的值優先於前述值物件。例如，傳入並 `color:blue``color:red` 將傳回的值設為紅色(覆寫藍色)。

**範例1：將資料傳送為索引鍵值配對**

此基本範例會以關鍵值配對的形式傳送顏色和價格資料至Audience Manager。您的程式碼看起來類似下列：

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；
sample_ dil. api. documents({
c_ color：「blue」，
c_ price：「900」})；
sample_ dil. api. mit()；</code>
</pre>

**範例2：在物件中傳送資料**

此進階範例示範如何將物件中的資料傳送至Audience Manager。使用此方法時， [!UICONTROL DIL] 可讓您將物件傳遞為函數參數 [!DNL signals()] 。[!UICONTROL DIL] 您的程式碼看起來類似下列：

<pre class="java"><code>var my_ object={
顏色：「blue」，
價格：「900」}；

var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；
//Load物件並附加「c_」至索引鍵值配對中的所有索引鍵，並傳送資料至AudienceManager。 
sample_ dil. api. documents(my_ object，「c_」). mit()；</code>
</pre>

**範例3：在Array中傳送頁面資料**

在此情況下，變數會 `my_object` 使用陣列來保留資料。此範例以上述建議方法傳入的資訊為基礎，但新增了其他圖層以容納產品類型和模型。您的程式碼看起來類似下列：

<pre class="java"><code>var my_ objects=[{{
顏色：「blue」，
價格：「900」}，{
type：「acura」，
模型：「tl」}]；

var sample_ dil= DIL. create({partner：<i>「合作夥伴名稱</i>」})；

for(var i=0；i&lt; my_ objects. length；i++)//Load物件並附加「c_」至索引鍵值配對中的所有索引鍵。 
{
sample_ dil. api. documents(my_ objects[i]，「c_」)；
} 
sample_ dil. api. mit()；</code>
</pre>

>[!MORE_贊_ this]
>
>* [訊號](../dil/dil-instance-methods.md#signals)


## 擷取轉介URL {#capture-referring-url}

擷取並傳送Audience Manager的反向連結URL。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>只有當使用者在具有類似通訊協定的頁面之間移動(HTTP與HTTPS)時，才會運作。例如，當您從安全網站導覽至另一個安全網站時，瀏覽器會保留反向連結URL。當您在安全和不安全的網站之間移動時，瀏覽器不會保留反向連結URL。此行為為一般瀏覽器功能，無法加以規避 [!UICONTROL DIL]。

**程式碼範例**

您的程式碼看起來類似下列：

<pre class="java"><code>var adobe_ dil= DIL. create({合作夥伴：<i>「合作夥伴名稱</i>」})；
adobe_ dil. api. documents({d_ referer：document. referrer}). mit()；</code>
</pre>

## 擷取搜尋引擎類型和關鍵字搜尋詞 {#capture-search-engine-types}

將搜尋引擎類型和關鍵字搜尋的相關資訊傳送至Audience Manager。

>[!IMPORTANT]
>
>本節說明舊版功能，並不支援最新版本的DIL。

**支援的搜尋引擎**

依預設 `DIL.getSearchReferrer` ，可識別這些搜尋引擎的搜尋(包括國際變化)：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

下列程式碼示範如何取得任何支援搜尋引擎的搜尋反向連結。在這種情況下，假設使用者在「home」一詞中搜尋 [!DNL Google] 了加拿大( `www.google.ca`)。此程式碼可協助您擷取這些搜尋詞，並將其傳送至Audience Manager。

**基本程式碼**

取得搜尋反向連結(例如，) `google.com`的基本程式碼如下：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出搜尋引擎代碼範例**

在這種情況下，假設使用者從 [!DNL Google] 加拿大( `www.google.ca`)搜尋「home」一詞。請注意程式碼如何預先修正 `c_` 搜尋引擎( `c_se`)和搜尋詞( `c_st`)的必要參數。`c_` 是 [必要首碼](../features/traits/trait-variable-prefixes.md) ，可將客戶定義的變數識別為Audience Manager。

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

在這種情況下，假設使用者搜尋「 `dogpile.com`home」一詞。由於 [!DNL Dogpile] 預設不支援，您可以設定DIL識別此搜尋引擎，並將搜尋詞傳回Audience Manager。您的程式碼看起來類似下列：

<pre class="java"><code>var adobe_ dil= DIL. create({合作夥伴：<i>「合作夥伴名稱</i>」})；
var search_ referrer= DIL. tools. getPrevireer(document. referrer，{
hostPattern：/dogpile\./
QueryParam：「q」})；

if(search_ referrer&amp;&amp; search_ referrer.有效){
adobe_ dil. api. documents({
c_ se：se. name，
c_ st：se. keywords
}). mit()；
}</code>
</pre>

## 將關鍵值映射至其他索引鍵 {#map-key-values}

將值從索引鍵值配對關聯到另一個索引鍵。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

在索引鍵值配對中，附加至索引鍵的 `c_` 首碼會將信號識別為客戶定義的資料。客戶定義的資料用於定位在事件呼叫資料傳入的特定網站上。不過，有時您會想要在Audience Manager帳戶中所有屬性中提供此資訊。若要這麼做，請將 `c_` 索引鍵值配對中的值對應至平台層級索引鍵。平台層級金鑰已前置詞， `d_` 並讓該訊號可用於您帳戶中所有屬性的定位。

例如，您可以從特定網站收集郵遞區號資料，但想要將其定位至所有Audience Manager屬性。為了讓平台層級提供郵遞區號，您可以將客戶定義的郵遞區號金鑰(例如 `c_zip`)對應至平台定義的索引鍵，如下所示。

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


## Google Tag Manager(GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM標籤設定並提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此程序假定您擁有 [!DNL Google Tag Manager] 帳戶、部分產品的相關知識，以及您的Audience Manager `dil.js` 檔案。

若要在GTM中傳輸 `dil.js` 檔案：

1. 建立新容器或開啓現有容器。
1. 新增標記至容器。
1. 開啓標籤以進行編輯和：

   * 命名標籤。
   * **[!UICONTROL Custom HTML Tag]** 從 **[!UICONTROL Tag Type]** 下拉式清單中選取。
   * 在HTML欄位中，將 [!UICONTROL DIL] 程式碼(程式庫+自訂代碼)置於指令碼標記 `<script>DIL code</script>`中。
   * Click **[!UICONTROL Save]**.

1. 發佈容器。
1. 產生容器標記程式碼並將它放置在您的庫存上。

>[!MORE_贊_ this]
>
>* [Google Tag Manager說明中心](https://support.google.com/tagmanager#topic=3441530)

