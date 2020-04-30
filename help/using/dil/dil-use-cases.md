---
description: 特定DIL使用案例的程式碼範例和說明。
seo-description: 特定DIL使用案例的程式碼範例和說明。
seo-title: DIL使用案例和程式碼範例
solution: Audience Manager
title: DIL使用案例和程式碼範例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# DIL使用案例和程式碼範例{#dil-use-cases-and-code-samples}

特定DIL使用案例的程式碼範例和說明。

<!-- 

c_dil_use_case.xml

 -->

## 使用DIL將資料元素傳送至Audience Manager {#send-data-elements-dil}

建立物件變數，將頁面元素的相關資訊傳送至Audience Manager。 這對於一般資料收集或是使用Analytics變數收集資料的替代方式非常有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

下列程式碼示範如何收集頁面資料，並將其傳送至Audience Manager [!UICONTROL DIL]。 這些範例使用變數將資料元素保存在平面清單或陣列中。 請記住，將變數傳 [入為鍵值配對](../reference/key-value-pairs-explained.md)。 此外，請注意 `c_` 鍵值對中鍵前的前置詞。 此必 [要首碼](../features/traits/trait-variable-prefixes.md) ，將資訊識別為使用者定義的資料。 在第一個範例中，您需要手動附加 `c_` 至索引鍵。 在第二個範例中， [!UICONTROL DIL] 會自動為您執行此動作。

**讓值屬性保持一致**

傳入資料時，請記得保持值屬性相同。 例如，如果您有兩個具有相同值的鍵，則最後一個鍵值對的值優先於前一個值對象。 例如，傳入並 `color:blue` 將傳 `color:red` 回的值設為紅色（覆寫藍色）。

**範例1: 以鍵值配對傳送資料**

此基本範例會以索引鍵值配對的形式，將色彩和價格資料傳送至Audience Manager。 您的程式碼看起來可能類似下列：

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**範例2: 在物件中傳送資料**

此進階範例示範如何將物件中的資料傳送至Audience Manager。 使用此方法時， [!UICONTROL DIL] 可讓您將物件作為函式參數傳遞至方 [!DNL signals()] 法。 [!UICONTROL DIL] 您的程式碼看起來可能類似下列：

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**範例3: 在陣列中傳送頁面資料**

在這種情況下，變數會 `my_object` 使用陣列來儲存資料。 此範例以上述建議方法傳入的資訊為基礎，但會新增額外的圖層以容納產品類型和型號。 您的程式碼看起來可能類似下列：

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

擷取反向連結URL並傳送至Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>此方法僅適用於使用者在使用類似通訊協定（HTTP與HTTPS）的頁面之間移動時。 例如，當您從安全網站導覽至其他安全網站時，瀏覽器會保留反向連結URL。 當您在安全與不安全的網站之間移動時，瀏覽器不會保留反向連結URL。 此行為是一般的瀏覽器功能，無法避免 [!UICONTROL DIL]。

**程式碼範例**

您的程式碼看起來可能類似下列：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 擷取搜尋引擎類型和關鍵字搜尋詞 {#capture-search-engine-types}

傳送搜尋引擎類型和關鍵字搜尋的相關資訊至Audience Manager。

>[!IMPORTANT]
>
>本節說明最新版DIL不支援的舊版功能。

**支援的搜尋引擎**

依預設， `DIL.getSearchReferrer` 會識別這些搜尋引擎的搜尋（包括國際變化）:

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

下列程式碼說明如何取得任何支援搜尋引擎的搜尋反向連結。 在此案例中，假設有使用者從加拿大搜尋「homes」 [!DNL Google] ( `www.google.ca`)。 此程式碼將協助您擷取這些搜尋詞，並傳送至Audience Manager。

**基本程式碼**

用於取得搜尋反向連結的基本程 `google.com`式碼（例如，從）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜尋引擎代碼範例**

在此例中，假設使用者從加拿大搜尋「homes」() [!DNL Google] 一詞 `www.google.ca`。 請注意程式碼如何將必 `c_` 要參數前置於搜尋引擎( `c_se`)和搜尋詞( `c_st`)。 `c_` 是必 [要的首碼](../features/traits/trait-variable-prefixes.md) ，可將這些變數識別為Audience Manager的客戶定義變數。

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

在此案例中，假設使用者從中搜尋詞「homes」 `dogpile.com`。 由 [!DNL Dogpile] 於預設不支援，您可以設定DIL來識別此搜尋引擎，並將搜尋詞傳回Audience Manager。 您的程式碼看起來可能類似下列：

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

## 將索引鍵值映射至其他索引鍵 {#map-key-values}

將鍵值對的值關聯到另一個鍵。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

在鍵值對中，附加在鍵 `c_` 上的前置詞將信號識別為客戶定義的資料。 客戶定義的資料用於定位在事件呼叫中傳入資料的特定網站。 不過，有時您會想要在Audience Manager帳戶的所有屬性中提供這項資訊。 若要這麼做，請將鍵值對 `c_` 應至平台層級鍵。 平台層級金鑰會加上前置詞， `d_` 並讓該訊號可用於您帳戶中所有屬性的定位。

例如，您從特定網站收集郵遞區號資料，但想要將其定位至您的所有Audience Manager屬性。 若要在平台層級提供郵遞區號，您可以對應客戶定義的郵遞區號金鑰(例如 `c_zip`)到平台定義的索引鍵，如下所示。

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

## Google標籤管理器(GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM標籤設定並提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此程式假設您有帳 [!DNL Google Tag Manager] 戶、該產品的一些工作知識，以及您的Audience Manager檔 `dil.js` 案。

若要在GTM中 `dil.js` 傳輸檔案：

1. 建立新容器或開啟現有容器。
1. 新增標籤至容器。
1. 開啟標籤以進行編輯，並：

   * 命名標籤。
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * 在HTML欄位中，將程式 [!UICONTROL DIL] 碼（程式庫+自訂程式碼）放在指令碼標籤內 `<script>DIL code</script>`。
   * 按一下 **[!UICONTROL Save]**.

1. 發佈容器。
1. 產生容器標籤代碼，並將其置於庫存中。

>[!MORELIKETHIS]
>
>* [Google標籤管理員說明中心](https://support.google.com/tagmanager#topic=3441530)
>* [信號](../dil/dil-instance-methods.md#signals)
>* [關鍵變數的前置詞要求](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

