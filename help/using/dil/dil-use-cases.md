---
description: 特定DIL使用案例的程式碼範例和說明。
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL使用案例和程式碼範例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# DIL使用案例和程式碼範例{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe在此點之後不會開發[!DNL DIL]。 建議客戶針對[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)。

特定DIL使用案例的程式碼範例和說明。

<!-- 

c_dil_use_case.xml

 -->

## 傳送資料元素以DIL進行Audience Manager {#send-data-elements-dil}

建立物件變數，將頁面元素的相關資訊傳送至Audience Manager。 這對一般資料收集或是使用Analytics變數收集資料的替代方法相當實用。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

下列程式碼示範如何收集頁面資料，並透過[!UICONTROL DIL]傳送給Audience Manager。 這些範例使用變數將資料元素儲存在平面清單或陣列中。 請記住，傳入變數做為[機碼值組](../reference/key-value-pairs-explained.md)。 此外，請記下機碼值組中機碼的前置詞`c_`。 此[必要的字首](../features/traits/trait-variable-prefixes.md)會將資訊識別為使用者定義的資料。 在第一個範例中，您需要手動將`c_`附加至機碼。 在第二個範例中，[!UICONTROL DIL]會自動為您執行此動作。

**保持值屬性一致**

傳入資料時，請記得保持值屬性相同。 例如，如果您有兩個值不同的相同索引鍵，則最後一個索引鍵 — 值組的值會優先於前面的值物件。 例如，傳入`color:blue`和`color:red`會將傳回的值設定為紅色（覆寫藍色）。

**範例1：以索引鍵值配對傳送資料**

這個基本範例會以索引鍵值配對的形式將色彩和價格資料傳送至Audience Manager。 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**範例2：在物件中傳送資料**

此進階範例示範如何將物件中的資料傳送至Audience Manager。 使用此方法時，[!UICONTROL DIL]可讓您將物件作為函式引數傳遞至[!DNL signals()]方法。 [!UICONTROL DIL]您的程式碼可能如下所示：

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**範例3：在陣列中傳送頁面資料**

在此情況下，變數`my_object`會使用陣列來儲存資料。 此範例以上述建議方法傳入的資訊為基礎，但會新增一個額外的圖層來配合產品型別和模型。 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## 擷取反向連結URL {#capture-referring-url}

擷取轉介URL並傳送給Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>只有當使用者在具有類似通訊協定（HTTP與HTTPS）的頁面之間移動時，此方法才有效。 例如，從安全網站導覽至另一個安全網站時，瀏覽器會保留反向連結URL。 您在安全和不安全的網站之間移動時，瀏覽器不會保留反向連結URL。 此行為是正常的瀏覽器功能，無法被[!UICONTROL DIL]規避。

**程式碼範例**

您的程式碼看起來可能類似下列：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 擷取搜尋引擎型別和關鍵字搜尋詞 {#capture-search-engine-types}

傳送搜尋引擎型別和關鍵字搜尋的相關資訊給Audience Manager。

>[!IMPORTANT]
>
>本節說明最新版本DIL不支援的舊版功能。

**支援的搜尋引擎**

根據預設，`DIL.getSearchReferrer`會辨識來自這些搜尋引擎的搜尋（包括國際變數）：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

下列程式碼會示範如何取得任何受支援搜尋引擎的搜尋反向連結。 在此案例中，假設使用者從[!DNL Google]加拿大( `www.google.ca`)搜尋「本位目錄」一詞。 此程式碼可協助您擷取這些搜尋辭彙，並將其傳送給Audience Manager。

**基本代碼**

用於取得搜尋反向連結的基本程式碼（例如，從`google.com`）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜尋引擎程式碼範例**

在此案例中，假設使用者從[!DNL Google]加拿大( `www.google.ca`)搜尋「本位目錄」一詞。 請注意程式碼如何為搜尋引擎( `c_se`)和搜尋字詞( `c_st`)的必要`c_`引數加上前置詞。 `c_`是[必要的首碼](../features/traits/trait-variable-prefixes.md)，可將其識別為要Audience Manager的客戶定義變數。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**未列出的搜尋引擎程式碼範例**

在此案例中，假設使用者從`dogpile.com`中搜尋「本位目錄」一詞。 因為預設不支援[!DNL Dogpile]，您可以設定DIL以辨識此搜尋引擎，並將搜尋字詞傳回Audience Manager。 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## 將索引鍵值對應到其他索引鍵 {#map-key-values}

將索引鍵/值組的值與另一個索引鍵建立關聯。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

在索引鍵/值組中，附加至索引鍵的`c_`首碼會將訊號識別為客戶定義的資料。 客戶定義的資料可用於在事件呼叫時傳入資料的特定網站上進行目標定位。 不過，有時候您會希望此資訊可在Audience Manager帳戶中的所有屬性中使用。 若要這麼做，請將`c_`機碼值組中的值對應至平台層級機碼。 平台層級索引鍵會加上前置詞`d_`，讓訊號可在您帳戶的所有屬性中定位。

例如，您從特定網站收集郵遞區號資料，但想要將其鎖定至所有Audience Manager屬性。 若要在平台層級提供郵遞區號，您可以將客戶定義的郵遞區號金鑰（例如`c_zip`）對應到平台定義的金鑰，如下所示。

**程式碼範例**

您的程式碼看起來可能類似下列：

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

## Google Tag Manager (GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM標籤設定及提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此程式假設您擁有[!DNL Google Tag Manager]帳戶、該產品的一些工作知識，以及您的Audience Manager`dil.js`檔案。

若要在GTM中傳輸`dil.js`檔案：

1. 建立新容器或開啟現有容器。
1. 將新標籤新增至容器。
1. 開啟標籤以編輯它，並：

   * 為標籤命名。
   * 從&#x200B;**[!UICONTROL Tag Type]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Custom HTML Tag]**。
   * 在HTML欄位中，將[!UICONTROL DIL]程式碼（程式庫+自訂程式碼）放置在指令碼標籤`<script>DIL code</script>`中。
   * 按一下 **[!UICONTROL Save]**。

1. Publish容器。
1. 產生貨櫃標籤代碼，並放置在詳細目錄上。

>[!MORELIKETHIS]
>
>* [Google Tag Manager說明中心](https://support.google.com/tagmanager#topic=3441530)
>* [訊號](../dil/dil-instance-methods.md#signals)
>* [關鍵變數的前置詞要求](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html?lang=zh-Hant#prefix-requirements-for-key-variables)
