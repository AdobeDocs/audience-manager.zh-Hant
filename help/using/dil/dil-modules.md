---
description: 說明DIL.modules命名空間中的方法。 這些模組可讓您以程式設計方式收集資料並使用Audience manager物件。
seo-description: 說明DIL.modules命名空間中的方法。 這些模組可讓您以程式設計方式收集資料並使用Audience manager物件。
seo-title: DIL模組
solution: Audience Manager
title: DIL模組
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# DIL模組{#dil-modules}

說明命名空間中的 `DIL.modules` 方法。 這些模組可讓您以程式設計方式收集資料並使用Audience manager物件。

<!-- 

c_dil_mods.xml

 -->

##  siteCatalyst.init {#sitecat-init}

可搭配 [!UICONTROL DIL] 傳送標 [!DNL Analytics] 記元素（變數、prop、eVar等）至Audience Manager。 以逗號分隔的清單傳回資料。 2.6版提供。

**** 函式簽名： `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>您必須將此程式碼放在函式 *之前*`s.t();` 的頁面。

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
   <td colname="col3"> <p>一系列非執行Analytics變數，例如「Analytics名稱」、「列舉 <span class="keyword"> 頁面名稱」、「促銷活動字串」、「 </span> 促銷活動字串」、「產品」等，其中包 <code> 含「列舉的」、「 </code>促銷活動字串」、「 <code></code><code></code><code></code>產品」等。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>包含 <span class="keyword"> Analytics變數的陣列，如prop和evar(例如 </span> prop1、prop2、evar3 <code> 、evar4枚舉的 </code><code></code><code></code><code></code>prop1、prop2、evar4)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整數 </td> 
   <td colname="col3"> <p>指出您要傳回的重複名稱數。 例如，若要傳回兩個prop或evar，請設定 <code> maxIndex:2 </code>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>代表 <span class="keyword"> Analytics物件的物 </span> 件。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>代表 <span class="wintitle"> DIL的物件 </span>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 選項 </code> </td> 
   <td colname="col2"> 物件 </td> 
   <td colname="col3"> <p>其他選項： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>如果不指定其他內容，則句點將替換為預設下划線(_)。 </p> <p>例如， <code> s.contextData = {abc.def = '123'} </code>會在事件呼叫查詢字串中產生 <code></code> c_contextData_abc_def=123。 </p> <p>此選項僅適用於 <span class="wintitle"> DIL </span> 5.0版或更新版本。 </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>例如，filterFromContextVariables <code> :['email'、'zip'、'accountNumber'] </code> 會導致從上下文資料的資料收集中篩選字串陣列。 此選項不包括個人識別資訊(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init擷取的資料**

此函式會傳回下列屬性的詳細 [!DNL Analytics] 資訊：

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

此程式碼會建立以逗號分隔的 [!DNL Analytics] 事件清單（prop、eVar等）如果值存在。

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

若要追蹤所有受監 [!DNL Analytics] 控的資料點，而不需上述其他功能，請 `siteCatalyst.init` 自行呼叫，如下所示：

```
DIL.modules.siteCatalyst.init(s, scDil);
```

##  GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

此函 `GA.submitUniversalAnalytics();` 數會從Google的資料傳送 [!DNL Universal Analytics] 至Audience Manager。 此函 [!UICONTROL DIL] 數的設計目的是搭配 `analytics.js`Google最新的程式碼庫使用 [!DNL Universal Analytics]。

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 對Google程式碼庫沒有任何洞察或 `analytics.js` 控制。 當Google發行新版 [!UICONTROL DIL] 本時，您應確認資料收集仍然有效 `analytics.js`。
   >
   >
* 如果您 `GA.submitUniversalAnalytics();` 仍在使用Google的舊版分析追蹤代碼（例如，或），則 `ga.js` 無法 `dc.js`使用。 請 [參閱GA.init](../dil/dil-modules.md#ga-init) 。
>



**** 函式簽名： `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**屬性**

函式 `GA.submitUniversalAnalytics();` 接受下列屬性。

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
   <td colname="col2"> <p>Google Analytics例項的全域 <span class="keyword"> 變數 </span>。 這通常 <code> 是預 </code> 設的，除非您已自訂 <span class="keyword"> Google Analytics程 </span> 式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>代表您DIL例項的變 <span class="wintitle"> 數 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（可選）</i> ，在 <code> analytics.js程式庫中 </code> ，內部屬性是精簡變 <code> 數「b」 </code>。 此變數包含 <span class="keyword"> Google Analytics </span> 資料。 </p> <p>此屬性是選用的，因為除非Google變更其內部變數的名稱，否則您不需要設定它。 例如，如果此精簡變數變更 <code> 為'a' </code>，您會呼叫 <code> GA.submitUniversalAnalytics(); </code> 如下： </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

請記得先定義 [!DNL Google Analytics] 物件， `ga` 然後再呼叫 [!UICONTROL DIL] 和 `GA.submitUniversalAnalytics();`。 您的程式碼看起來可能類似下列：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_LIKE_THIS]
>
>* [ga對象方法參考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


##  GA.init {#ga-init}

此函 `GA.init()` 數會將舊版／已過時版本的資料 [!DNL Google Analytics] 傳送至Audience Manager。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 僅能與Google的舊有分析追蹤代碼搭配使 `ga.js` 用， `dc.js`或 如果您使用 [!UICONTROL DIL] Google的最新程式碼 `analytics.js`庫，則無法叫用此函式 [!DNL Universal Analytics]。 [!DNL Audience Manager] 使用並應 [!UICONTROL DIL] 該看 [!DNL Universal Analytics] 到 [GA.submitUniversalAnalytics的客戶](../dil/dil-modules.md#ga-submit-universal-analytics)。

**** 函式簽名： `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `_gaq` | 陣列 | 包含GA命令的陣列。 |
| `dilInstance` | 物件 | 包含DIL例項的物件。 |
| `trackVars` | 物件 | *（可選）* ，包含屬性的對 `names` 像。 此屬性是要跟蹤的GA命令名稱陣列。 |

**支援的GA函式調用**

依預設，會 `GA.init` 從下列函式擷取資料：

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL建立GA資料的金鑰**

Audience manager可接受以鍵值配對的形式呈現的資料，而GA則可處理陣列中的項目。 要使用GA資料， [!UICONTROL DIL] 請自動建立密鑰值對並形成如下密鑰： `c_ <key name>`。 此外，GA陣列中的項目以特定順序顯示。 因此，您必須依該順序提供所有參數，即使這些參數不含任何資料亦然。 [!UICONTROL DIL] 映射以下GA方法的鍵：

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

若要追蹤所有受監控的GA量度，而不需上述其他函式，請 `GA.init` 自行呼叫，如下所示：

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**範例事件呼叫**

對Audience manager的URL事件呼叫看起來可能類似下列：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_LIKE_THIS]
>
>* [Google Analytics追蹤代碼](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完整的網頁升級：ga.js/dc.js至analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [將analytics.js新增至您的網站](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

