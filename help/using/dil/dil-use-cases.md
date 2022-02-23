---
description: 特定DIL使用案例的代碼示例和說明。
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL 使用案例和程式碼範例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# DIL 使用案例和程式碼範例{#dil-use-cases-and-code-samples}

特定DIL使用案例的代碼示例和說明。

<!-- 

c_dil_use_case.xml

 -->

## 將資料元素發送到Audience Manager,DIL {#send-data-elements-dil}

建立一個對象變數，該對象變數將有關頁面元素的資訊發送到Audience Manager。 這對於一般資料收集或使用分析變數收集資料的替代方法非常有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**說明**

以下代碼演示了如何收集頁資料並將其發送到Audience Manager [!UICONTROL DIL]。 這些示例使用變數將資料元素保存在平面清單或陣列中。 記住，將變數傳遞為 [鍵值對](../reference/key-value-pairs-explained.md)。 另外，請注意 `c_` 鍵值對中鍵前的前置詞。 此 [必需前置詞](../features/traits/trait-variable-prefixes.md) 將資訊標識為用戶定義的資料。 在第一個示例中，需要手動追加 `c_` 鍵。 在第二個例子中， [!UICONTROL DIL] 自動為你做這個。

**保持值屬性一致**

切記在傳遞資料時保持值屬性相同。 例如，如果您有兩個具有相同鍵且具有不同的值，則最後一個鍵值對的值優先於前面的值對象。 例如， `color:blue` 和 `color:red` 將返回的值設定為紅色（覆蓋藍色）。

**示例1:將資料作為鍵值對發送**

此基本示例以鍵值對的形式將顏色和價格資料發送到Audience Manager。 您的代碼可能與以下內容類似：

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**示例2:在對象中發送資料**

此高級示例演示如何將對象中的資料發送到Audience Manager。 使用這種方法時， [!UICONTROL DIL] 允許您將對象作為函式參數傳遞到 [!DNL signals()] 的雙曲餘切值。 [!UICONTROL DIL] 您的代碼可能與以下內容類似：

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**示例3:在陣列中發送頁資料**

在這種情況下，變數 `my_object` 使用陣列來保存資料。 此示例基於上面推薦的方法傳遞的資訊，但添加了附加層以適應產品類型和模型。 您的代碼可能與以下內容類似：

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

## 捕獲引用URL {#capture-referring-url}

捕獲併發送引用URL到Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>僅當用戶在具有類似協定（HTTP與HTTPS）的頁面之間移動時，此方法才起作用。 例如，當您從安全站點導航到另一個安全站點時，瀏覽器會保留引用URL。 在安全站點和不安全站點之間移動時，瀏覽器不會保留引用URL。 此行為是正常的瀏覽器功能，無法通過 [!UICONTROL DIL]。

**程式碼範例**

您的代碼可能與以下內容類似：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 捕獲搜索引擎類型和關鍵字搜索詞 {#capture-search-engine-types}

將有關搜索引擎類型和關鍵字搜索的資訊發送到Audience Manager。

>[!IMPORTANT]
>
>本節介紹舊版功能，在最新版本的DIL中不支援舊版功能。

**支援的搜索引擎**

預設情況下， `DIL.getSearchReferrer` 識別來自這些搜索引擎的搜索（包括國際變體）:

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**說明**

以下代碼演示如何獲取任何受支援的搜索引擎的搜索引用者。 在這種情況下，假設用戶從 [!DNL Google] 加拿大( `www.google.ca`)。 此代碼將幫助您捕獲這些搜索詞並將它們發送到Audience Manager。

**基本程式碼**

用於獲取搜索引用程式的基本代碼(從 `google.com`，例如：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜索引擎代碼示例**

在本例中，假設用戶從 [!DNL Google] 加拿大( `www.google.ca`)。 注意代碼前置詞的要求 `c_` 搜索引擎的參數( `c_se`)和搜索術語( `c_st`)。 `c_` 是 [必需前置詞](../features/traits/trait-variable-prefixes.md) 將其標識為要Audience Manager的客戶定義變數。

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

**未列出的搜索引擎代碼示例**

在本例中，假設用戶從 `dogpile.com`。 因為 [!DNL Dogpile] 預設情況下不支援，您可以配置DIL以識別此搜索引擎並將搜索項返回Audience Manager。 您的代碼可能與以下內容類似：

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

## 將鍵值映射到其他鍵 {#map-key-values}

將值從鍵值對關聯到另一個鍵。

<!-- 

c_dil_map_keys.xml

 -->

**說明**

在鍵值對中， `c_` 附加在鍵上的前置詞將信號標識為客戶定義的資料。 客戶定義的資料用於針對在事件呼叫中傳遞資料的特定站點。 但是，有時您希望此資訊在您的Audience Manager帳戶中的所有屬性中都可用。 為此，請映射 `c_` 鍵值對到平台級鍵。 平台級鍵的前置詞為 `d_` 並使該信號可用於帳戶中所有屬性的目標。

例如，您從特定站點收集郵遞區號資料，但希望將其目標定位到所有Audience Manager屬性。 要使郵遞區號在平台級別可用，您可以映射客戶定義的郵遞區號密鑰(例如， `c_zip`)到平台定義的密鑰，如下所示。

**程式碼範例**

您的代碼可能與以下內容類似：

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

此過程假定您 [!DNL Google Tag Manager] 帳戶、某些產品的工作知識，以及您的Audience Manager `dil.js` 的子菜單。

要通過 `dil.js` GTM中的檔案：

1. 建立新容器或開啟現有容器。
1. 向容器添加新標籤。
1. 開啟標籤以編輯它，並：

   * 命名標籤。
   * 選擇 **[!UICONTROL Custom HTML Tag]** 從 **[!UICONTROL Tag Type]** 的子菜單。
   * 在HTML欄位中，將 [!UICONTROL DIL] 指令碼標籤內的代碼（庫+自定義代碼） `<script>DIL code</script>`。
   * 按一下 **[!UICONTROL Save]**.

1. 發佈容器。
1. 生成容器標籤代碼並將其放在庫存上。

>[!MORELIKETHIS]
>
>* [Google標籤管理器幫助中心](https://support.google.com/tagmanager#topic=3441530)
>* [信號](../dil/dil-instance-methods.md#signals)
>* [關鍵變數的前置詞要求](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

