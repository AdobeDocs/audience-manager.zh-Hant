---
description: 說明DIL.模組名稱空間中的方法。這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。
seo-description: 說明DIL.模組名稱空間中的方法。這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。
seo-title: DIL模組
solution: Audience Manager
title: DIL模組
uuid: d4c0d8dd-79f8-448e-b17 c-c935415 dd449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# DIL Modules{#dil-modules}

Describes methods in the `DIL.modules` namespace. 這些模組可讓您以程式設計方式收集資料並使用Audience Manager物件。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Works with [!UICONTROL DIL] to send [!DNL Analytics] tag elements (variables, props, eVars, etc.) 至Audience Manager。以逗號分隔清單傳回資料。適用於2.6版。

**函數簽名：**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>You must place this code on the page *before* the `s.t();` function.

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
   <td colname="col1"> <code> 名稱 </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>An array of strings that contains un-enumerated <span class="keyword"> Analytics </span> variables like <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 反覆名稱 </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated <span class="keyword"> Analytics </span> variables like props and evars (e.g. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整數 </td> 
   <td colname="col3"> <p>指出您要傳回多少反覆名稱。For example, to return two props or evars, set <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> SiteCatalystReportSuite </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>An object that represents the <span class="keyword"> Analytics </span> object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> DiLintition </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>An object that represents <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 選項 </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>其他選項： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> ReplaceContextDataAlphoAndSSH </code> </p> <p>如果您未指定其他項目，則會以預設底線(_)取代句號。 </p> <p>For example <code> s.contextData = {abc.def = '123'} </code>would result in <code> c_contextData_abc_def=123 </code> in the event call query string. </p> <p>This option is available only in <span class="wintitle"> DIL </span> version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> FilterFromContextVariables </code> </p> <p>For example, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> would result in the array of strings being filtered from the data collection of context data. 此選項排除個人識別資訊(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**由SiteCatalyst. init擷取的資料**

This function returns details on the following [!DNL Analytics] properties:

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

This code creates a comma separated list of [!DNL Analytics] events (props, eVars, etc.) If value for them exists.

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

To track all the monitored [!DNL Analytics] data points without the additional function shown above, invoke `siteCatalyst.init` by itself like this:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();` 函數會將Google的 [!DNL Universal Analytics] 資料傳送至Audience Manager。This [!UICONTROL DIL] function is designed to work with `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 對Google `analytics.js` 程式碼程式庫沒有任何深入分析或控制。You should verify that [!UICONTROL DIL] data collection is still working if or when Google releases new versions of `analytics.js`.
   >
   >
* `GA.submitUniversalAnalytics();` 如果您仍在使用Google的舊版分析追蹤代碼(例如 `ga.js` ，或 `dc.js`)，則無法使用。See [GA.init](../dil/dil-modules.md#ga-init) instead.
>



**函數簽名：**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**屬性**

`GA.submitUniversalAnalytics();` 函數可接受下列屬性。

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 屬性 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> GaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Google Analytics例項的全域變數 </span>。This is usually <code> ga </code> by default, unless you've customized your <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DiLintition </code> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> InternalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(選擇性)</i> 在 <code> analytics. js </code> 程式庫中，內部屬性是縮小變數 <code> 'b' </code>。This variable holds <span class="keyword"> Google Analytics </span> data. </p> <p>此屬性是選擇性的，因為除非Google變更其內部變數的名稱，否則您不需要加以設定。For example, if this minified variable changed to <code> 'a' </code>, you would call <code> GA.submitUniversalAnalytics(); </code> like this: </p> <p> <code> DIL. modules. GasUbMitsalAnalytics(Ga，Dilintiation，'a')； </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

Remember to define the [!DNL Google Analytics] `ga` object first, before calling [!UICONTROL DIL] and `GA.submitUniversalAnalytics();`. 您的程式碼看起來類似於：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_贊_ this]
>
>* [Ga物件方法參考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


## GA.init {#ga-init}

`GA.init()` 函數會從舊版/已過時版本的Audience [!DNL Google Analytics] Manager傳送資料。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 僅適用於Google的舊版分析追蹤代碼或 `ga.js``dc.js`。You cannot invoke this [!UICONTROL DIL] function if you use `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics]. [!DNL Audience Manager] 使用 [!UICONTROL DIL] 且 [!DNL Universal Analytics] 應查看 [GA. submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)的客戶。

**函數簽名：**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `_gaq` | 陣列 | 包含GA命令的陣列。 |
| `dilInstance` | 物件 | 包含DIL實例的物件。 |
| `trackVars` | 物件 | *(可選)* 包含 `names` 屬性的物件。此屬性是您要追蹤的GA命令名稱陣列。 |

**支援的GA函數呼叫**

By default, `GA.init` captures data from the following functions:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL建立GA資料的索引鍵**

Audience Manager可接受關鍵值配對形式的資料，而GA則適用於陣列中的項目。To work with GA data, [!UICONTROL DIL] creates a key-value pair automatically and forms a key like this: `c_ <key name>`. 此外，GA陣列中的項目會以特定順序顯示。因此，您必須以該順序提供所有參數，即使這些參數沒有任何資料。[!UICONTROL DIL] 對應下列GA方法的索引鍵：

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

To track all the monitored GA metrics without the additional function shown above, invoke `GA.init` by itself like this:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**範例事件呼叫**

Audience Manager的URL事件呼叫看起來類似於：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_贊_ this]
>
>* [Google Analytics追蹤代碼](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完整的Web升級：ga.js/dc.js至analytics. js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [新增分析. js至您的網站](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

