---
description: 描述DIL.modules命名空間中的方法。 這些模組允許您以寫程式方式收集資料並處理Audience Manager對象。
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL 模組
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 4%

---

# DIL 模組{#dil-modules}

介紹中的方法 `DIL.modules` 命名空間。 這些模組允許您以寫程式方式收集資料並處理Audience Manager對象。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

使用 [!UICONTROL DIL] 發送 [!DNL Analytics] 標籤元素（變數、道理、eVars等） Audience Manager。 以逗號分隔的清單返回資料。 在2.6版中提供。

**函式簽名：** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>必須將此代碼放在頁面上 *先* 這樣 `s.t();` 的子菜單。

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
   <td colname="col3"> <p>包含未枚舉的字串的陣列 <span class="keyword"> 分析 </span> 變數 <code> pageName </code>。 <code> channel </code>。 <code> campaign </code>。 <code> product </code>的子菜單。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>包含枚舉的對象的陣列 <span class="keyword"> 分析 </span> 變數如道具和潛水器(如 <code> prop1 </code>。 <code> prop2 </code>。 <code> evar3 </code>。 <code> evar4 </code>)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整數 </td> 
   <td colname="col3"> <p>指示要返回的迭代名稱數。 例如，要返回兩個道具或避風器，請設定 <code> maxIndex:2 </code>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>表示 <span class="keyword"> 分析 </span> 的雙曲餘切值。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>表示 <span class="wintitle"> DIL </span>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>其他選項： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>如果不指定其他內容，則句點將替換為預設下划線(_)。 </p> <p>例如 <code> s.contextData = {abc.def = '123'} </code>會導致 <code> c_contextData_abc_def=123 </code> 在事件調用查詢字串中。 </p> <p>此選項僅在 <span class="wintitle"> DIL </span> 5.0版或更高版本。 </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>比如說， <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> 將導致從上下文資料的資料收集中過濾字串陣列。 此選項不包括個人身份資訊(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init捕獲的資料**

此函式返回以下方面的詳細資訊 [!DNL Analytics] 屬性：

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

此代碼建立逗號分隔的清單 [!DNL Analytics] 事件（道具、eVars等） 的值。

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

跟蹤所有受監視的 [!DNL Analytics] 資料點沒有上面所示的附加函式，調用 `siteCatalyst.init` 本身就是這樣的：

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

的 `GA.submitUniversalAnalytics();` 函式從Google發送資料 [!DNL Universal Analytics] Audience Manager。 此 [!UICONTROL DIL] 功能設計為 `analytics.js`，是Google的最新代碼庫 [!DNL Universal Analytics]。

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 對Google沒有任何瞭解和控制 `analytics.js` 代碼庫。 您應驗證 [!UICONTROL DIL] 如果Google發佈新版本，或當其發佈時，資料收集仍然有效 `analytics.js`。
>
>* 不能使用 `GA.submitUniversalAnalytics();` 如果您仍在使用Google的舊式分析跟蹤代碼(例如， `ga.js` 或 `dc.js`)。 請參閱 [GA.init](../dil/dil-modules.md#ga-init) 的雙曲餘切值。
>


**函式簽名：** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**屬性**

的 `GA.submitUniversalAnalytics();` 函式接受以下屬性。

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
   <td colname="col2"> <p>實例的全局變數 <span class="keyword"> Google Analytics </span>。 通常 <code> ga </code> 預設情況下，除非您 <span class="keyword"> Google Analytics </span> 代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>表示實例的變數 <span class="wintitle"> DIL </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（可選）</i> 在 <code> analytics.js </code> 庫，內部屬性是微型變數 <code> 'b' </code>。 此變數保持 <span class="keyword"> Google Analytics </span> 資料。 </p> <p>此屬性是可選的，因為除非Google更改其內部變數的名稱，否則不需要設定它。 例如，如果此微型變數更改為 <code> 'a' </code>你打給 <code> GA.submitUniversalAnalytics(); </code> 這樣： </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

記住定義 [!DNL Google Analytics] `ga` 在調用前先對象 [!UICONTROL DIL] 和 `GA.submitUniversalAnalytics();`。 您的代碼可能與以下內容類似：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

的 `GA.init()` 函式從舊版/不建議使用的版本發送資料 [!DNL Google Analytics] Audience Manager。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 只與Google的舊式分析跟蹤代碼配合使用， `ga.js` 或 `dc.js`。 無法調用此 [!UICONTROL DIL] 函式 `analytics.js`，是Google的最新代碼庫 [!DNL Universal Analytics]。 [!DNL Audience Manager] 使用 [!UICONTROL DIL] 和 [!DNL Universal Analytics] 應該看 [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)。

**函式簽名：** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `_gaq` | 陣列 | 包含GA命令的陣列。 |
| `dilInstance` | 物件 | 包含DIL實例的對象。 |
| `trackVars` | 物件 | *（可選）* 由 `names` 屬性。 此屬性是要跟蹤的GA命令名的陣列。 |

**支援的GA函式調用**

預設情況下， `GA.init` 從以下功能捕獲資料：

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL為GA資料建立鍵**

Audience Manager以鍵值對的形式接受資料，而GA則處理陣列中的項。 要處理GA資料， [!UICONTROL DIL] 自動建立鍵值對，並形成如下鍵： `c_ <key name>`。 此外，GA陣列中的項按特定順序顯示。 因此，必須按該順序提供所有參數，即使這些參數不包含任何資料。 [!UICONTROL DIL] 映射以下GA方法的鍵：

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

要跟蹤所有被監視的GA度量，而不使用上面顯示的附加函式，請調用 `GA.init` 本身就是這樣的：

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**示例事件調用**

對Audience Manager的URL事件調用可能與以下內容類似：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics跟蹤代碼](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完成Web升級：ga.js/dc.js到analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [將analytics.js添加到您的站點](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Ga對象方法參考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

