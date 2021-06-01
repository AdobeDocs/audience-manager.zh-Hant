---
description: 特定DIL使用案例的程式碼範例和說明。
seo-description: 特定DIL使用案例的程式碼範例和說明。
seo-title: DIL 使用案例和程式碼範例
solution: Audience Manager
title: DIL 使用案例和程式碼範例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL實作
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 3%

---

# DIL 使用案例和程式碼範例{#dil-use-cases-and-code-samples}

特定DIL使用案例的程式碼範例和說明。

<!-- 

c_dil_use_case.xml

 -->

## 傳送資料元素至Audience Manager，並DIL{#send-data-elements-dil}

建立物件變數，將頁面元素的相關資訊傳送至Audience Manager。 這對於一般資料收集或使用Analytics變數收集資料的替代方法非常有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

下列程式碼示範如何收集頁面資料，並透過[!UICONTROL DIL]將其傳送至Audience Manager。 這些範例使用變數將資料元素保留在平面清單或陣列中。 請記住，將變數傳入為[機碼值組](../reference/key-value-pairs-explained.md)。 另外，請注意機碼值組中機碼前面的`c_`前置詞。 此[必要前置詞](../features/traits/trait-variable-prefixes.md)將資訊標識為用戶定義的資料。 在第一個範例中，您需要手動將`c_`附加至索引鍵。 在第二個範例中， [!UICONTROL DIL]會自動為您執行此動作。

**保持值屬性一致**

傳入資料時，請記得保持值屬性相同。 例如，如果您有兩個具有相同鍵值的不同值，則最後一個鍵值對的值優先於前一個值對象。 例如，傳入`color:blue`和`color:red`會將傳回的值設為紅色（覆寫藍色）。

**範例1:以索引鍵值配對傳送資料**

此基本範例會以索引鍵值配對的形式，將顏色和價格資料傳送至Audience Manager。 您的程式碼看起來可能類似下列：

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**範例2:在物件中傳送資料**

此進階範例示範如何將物件中的資料傳送至Audience Manager。 使用此方法時，[!UICONTROL DIL]可讓您將物件作為函式參數傳遞至[!DNL signals()]方法。 [!UICONTROL DIL] 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**範例3:以陣列傳送頁面資料**

在此情況下，變數`my_object`會使用陣列來保留資料。 此範例以上述建議方法傳入的資訊為基礎，但新增了額外的層來容納產品類型和模型。 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## 擷取反向連結URL {#capture-referring-url}

擷取並傳送轉介URL至Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>只有當使用者在具有類似通訊協定（HTTP與HTTPS）的頁面之間移動時，此方法才有效。 例如，當您從安全網站導覽至另一個安全網站時，瀏覽器會保留反向連結URL。 當您在安全和不安全的網站之間移動時，瀏覽器不會保留反向連結URL。 此行為是一般瀏覽器功能，無法透過[!UICONTROL DIL]規避。

**程式碼範例**

您的程式碼看起來可能類似下列：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 擷取搜尋引擎類型和關鍵字搜尋詞{#capture-search-engine-types}

將搜尋引擎類型和關鍵字搜尋的相關資訊傳送至Audience Manager。

>[!IMPORTANT]
>
>本節說明最新版本DIL不支援的舊版功能。

**支援的搜尋引擎**

依預設，`DIL.getSearchReferrer`會辨識來自這些搜尋引擎的搜尋（包括國際變數）:

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

下列程式碼示範如何取得任何受支援搜尋引擎的搜尋反向連結。 在此案例中，假設有使用者從[!DNL Google]加拿大(`www.google.ca`)搜尋了&quot;homes&quot;一詞。 此程式碼可協助您擷取這些搜尋詞，並將其傳送至Audience Manager。

**基本程式碼**

取得搜尋反向連結的基本程式碼（例如從`google.com`取得）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜尋引擎代碼範例**

在此案例中，假設使用者從[!DNL Google]加拿大(`www.google.ca`)搜尋「homes」一詞。 請注意，程式碼會如何將必要的`c_`參數前置到搜尋引擎(`c_se`)和搜尋詞(`c_st`)。 `c_` 是必要 [的](../features/traits/trait-variable-prefixes.md) 前置詞，可將這些識別為客戶定義的變數以Audience Manager。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**未列出的搜尋引擎代碼範例**

在此案例中，假設使用者從`dogpile.com`搜尋「homes」一詞。 因為預設不支援[!DNL Dogpile]，您可以設定DIL來識別此搜尋引擎，並將搜尋詞傳回Audience Manager。 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## 將鍵值映射到其他鍵{#map-key-values}

將值從機碼值組關聯至另一個機碼。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

在機碼值組中，附加至機碼的`c_`前置詞會將訊號識別為客戶定義的資料。 客戶定義的資料用於定位在事件呼叫中傳入資料的特定網站。 不過，有時候您會想要將這項資訊提供給Audience Manager帳戶中的所有屬性。 若要這麼做，請將`c_`索引鍵值組中的值對應至平台層級索引鍵。 平台層級金鑰的前置詞為`d_`，可讓您的帳戶中所有屬性的目標定位都能使用該訊號。

例如，您從特定網站收集郵遞區號資料，但想將其定位至所有Audience Manager屬性。 若要讓郵遞區號在平台層級可用，您可以對應您客戶定義的郵遞區號金鑰(例如`c_zip`)轉換為平台定義的索引鍵，如下所示。

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

## Google Tag Manager(GTM){#traffic-dil-gtm}中的流量DIL

使用GTM標籤設定和提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此過程假定您有[!DNL Google Tag Manager]帳戶、該產品的一些工作知識，以及您的Audience Manager`dil.js`檔案。

若要在GTM中傳輸`dil.js`檔案：

1. 建立新容器或開啟現有容器。
1. 新增標籤至容器。
1. 開啟標籤以進行編輯，然後：

   * 為標籤命名。
   * 從&#x200B;**[!UICONTROL Tag Type]**&#x200B;下拉清單中選擇&#x200B;**[!UICONTROL Custom HTML Tag]**。
   * 在HTML欄位中，將[!UICONTROL DIL]程式碼（程式庫+自訂程式碼）放置在指令碼標籤`<script>DIL code</script>`中。
   * 按一下 **[!UICONTROL Save]**.

1. 發佈容器。
1. 產生容器標籤代碼並將其放置在庫存中。

>[!MORELIKETHIS]
>
>* [Google Tag Manager說明中心](https://support.google.com/tagmanager#topic=3441530)
>* [訊號](../dil/dil-instance-methods.md#signals)
* [關鍵變數的前置詞要求](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

