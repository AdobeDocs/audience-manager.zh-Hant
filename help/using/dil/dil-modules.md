---
description: 說明DIL.modules命名空間中的方法。 這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。
seo-description: 說明DIL.modules命名空間中的方法。 這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。
seo-title: DIL 模組
solution: Audience Manager
title: DIL 模組
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL實作
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---

# DIL 模組{#dil-modules}

說明`DIL.modules`命名空間中的方法。 這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

與[!UICONTROL DIL]搭配使用，傳送[!DNL Analytics]標籤元素（變數、Prop、eVar等） Audience Manager。 以逗號分隔的清單傳回資料。 2.6版提供。

**函式簽名：** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>您必須將此程式碼放置在&#x200B;*頁面*&#x200B;之前`s.t();`函式。

<!-- 

r_dil_sc_init.xml

 -->

**參數**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>包含未枚舉<span class="keyword"> Analytics </span>變數（如<code> pageName </code>、<code> channel </code>、<code> campaign </code>、<code> product </code>等）的字串陣列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>包含列舉<span class="keyword"> Analytics </span>變數（如prop和evar）的物件陣列(例如<code> prop1 </code>、<code> prop2 </code>、<code> evar3 </code>、<code> evar4 </code>)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整數 </td> 
   <td colname="col3"> <p>指示要返回的迭代名稱數。 例如，若要傳回兩個prop或evar，請設定<code> maxIndex:2 </code>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>代表<span class="keyword"> Analytics </span>物件的物件。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>代表<span class="wintitle">DIL</span>的物件。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>其他選項： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>如果您未指定其他項目，句點將替換為預設底線(_)。 </p> <p>例如， <code> s.contextData = {abc.def = '123'} </code>會在事件呼叫查詢字串中產生<code> c_contextData_abc_def=123 </code>。 </p> <p>此選項僅在<span class="wintitle">DIL</span> 5.0版或更新版本中可用。 </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>例如， <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code>會導致從內容資料的資料收集中篩選出字串陣列。 此選項不包括個人識別資訊(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**由siteCatalyst.init擷取的資料**

此函式返回以下[!DNL Analytics]屬性的詳細資訊：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**程式碼範例**

此程式碼會建立以逗號分隔的[!DNL Analytics]事件清單（prop、eVar等） 如果值存在。

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

要跟蹤所有受監視的[!DNL Analytics]資料點，而不使用上面所示的附加函式，請按如下方式自行調用`siteCatalyst.init`:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();`函式會將資料從Google的[!DNL Universal Analytics]傳送至Audience Manager。 此[!UICONTROL DIL]函式設計為可搭配`analytics.js`使用，此為Google [!DNL Universal Analytics]的最新程式碼庫。

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 對Google程式碼程式庫沒有任何深入分析或 `analytics.js` 控制權。當或當Google發行新版本`analytics.js`時，您應確認[!UICONTROL DIL]資料收集仍然有效。
   >
   >
* 如果您仍在使用Google的舊版分析追蹤代碼（例如`ga.js`或`dc.js`），則無法使用`GA.submitUniversalAnalytics();`。 請改為參閱[GA.init](../dil/dil-modules.md#ga-init)。

>



**函式簽名：** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**屬性**

`GA.submitUniversalAnalytics();`函式接受以下屬性。

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 屬性 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">例項的全域變數Google Analytics</span>。 預設情況下，這通常為<code> ga </code>，除非您已自訂<span class="keyword">Google Analytics</span>代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>代表您的<span class="wintitle">DIL</span>例項的變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（選用）</i> 在程式 <code> analytics.js </code> 庫中，內部屬性為縮制的變 <code> 'b' </code>數。此變數包含<span class="keyword">Google Analytics</span>資料。 </p> <p>此屬性為選用屬性，因為除非Google變更其內部變數的名稱，否則您不需要加以設定。 例如，如果此縮制變數變更為<code> 'a' </code>，您會以下列方式呼叫<code> GA.submitUniversalAnalytics(); </code>: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

請記得先定義[!DNL Google Analytics] `ga`物件，再呼叫[!UICONTROL DIL]和`GA.submitUniversalAnalytics();`。 您的程式碼看起來可能類似以下：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

`GA.init()`函式會將來自[!DNL Google Analytics]舊版/已棄用版本的資料傳送至Audience Manager。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 僅適用於Google的舊版analytics追蹤代碼， `ga.js` 或 `dc.js`。如果您使用`analytics.js`（Google [!DNL Universal Analytics]的最新代碼庫），則無法調用此[!UICONTROL DIL]函式。 [!DNL Audience Manager] 使用和 [!UICONTROL DIL] 的 [!DNL Universal Analytics] 客戶應 [看到GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)。

**函式簽名：** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `_gaq` | 陣列 | 包含GA命令的陣列。 |
| `dilInstance` | 物件 | 包含DIL例項的物件。 |
| `trackVars` | 物件 | *（選用）* 包含屬性的物 `names` 件。此屬性是要跟蹤的GA命令名稱的陣列。 |

**支援的GA函式呼叫**

預設情況下， `GA.init`從以下函式中捕獲資料：

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL建立GA資料的鍵**

Audience Manager可接受索引鍵值配對形式的資料，而GA可搭配陣列中的項目運作。 若要使用GA資料，[!UICONTROL DIL]會自動建立機碼值組，並形成如下的機碼：`c_ <key name>`。 此外，GA陣列中的項目會以特定順序顯示。 因此，您必須依該順序提供所有參數，即使這些參數不含任何資料亦然。 [!UICONTROL DIL] 映射以下GA方法的鍵：

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**程式碼範例**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

要跟蹤所有受監控的GA度量而不使用上面所示的附加函式，請自行調用`GA.init`，如下所示：

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**事件呼叫範例**

對Audience Manager的URL事件呼叫看起來可能類似這樣：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics追蹤代碼](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完整Web升級：ga.js/dc.js至analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [將analytics.js新增至您的網站](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Ga對象方法參考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

