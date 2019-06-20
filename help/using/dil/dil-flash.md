---
description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中使用該資訊。
seo-description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中使用該資訊。
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833metrics-768e-4b16-95c5-debd8411 df38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中使用該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是 [!DNL ActionScript] 程式碼庫，可讓您在Audience Manager中處理視訊播放資料。[!DNL Flash DIL] 方法是擷取Adobe [!UICONTROL AppMeasurement] 程式庫傳入Analytics中的SWF內容。[!DNL Flash DIL] 將該資料傳送至個別 [!UICONTROL DIL] JavaScript資料收集模組，將該資訊傳遞至Audience Manager。Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

一般實施與程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* [!UICONTROL DIL] 類別程式庫( `dil.swc`)。Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [DIL ActionScript程式庫](../dil/dil-flash.md#flash-dil-actionscript) 載入您要收集資料的Flash物件。
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**將allowScriptAccess設為`Always`或`sameDomain`**

`AllowScriptAccess` 載入SWF檔案的HTML程式碼控制在SWF檔案內執行傳出URL存取的能力。When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] 如果設定為，資料收集將無法 `AllowScriptAccess` 運作 `never`。See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS[!UICONTROL DIL]程式碼位置**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. [!DNL FLA] 當檔案第一次載入時， [!UICONTROL DIL] 在資料收集就緒之前，您可以錯失 [!UICONTROL Flash DIL] 傳送到該模組的初始資料訊號。However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] 從Adobe [!UICONTROL AppMeasurement] 資料庫擷取頁面檢視、連結追蹤、媒體追蹤及其他媒體檢視事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面檢視事件**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結追蹤事件**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (呼叫的追蹤連結類型)
* `pev1` (連結 URL)
* `pev2`(連結文字)

**媒體追蹤事件**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**其他資料點**

預設會收集這些參數的資料：

* `mediaName` (媒體/視訊元素名稱)
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` (已巢狀內嵌的主要媒體內容的名稱)
* `mediaAdParentPod` (廣告播放之主要內容內的pod或廣告插播)
* `mediaAdParentPodPos` (pod在廣告播放位置中的數值位置)。多個廣告可在pod內播放。

>[!MORE_贊_ this]
>
>* [AppMeasurement Flash、Flex和OSMF實施指南](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] 模組會將Adobe AppMeasurement資料轉換為Audience Manager特徵和未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. 特徵是關鍵值配對，用於建立區段。For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**匹配Audience Manager特徵至Analytics變數**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

如需範例，請參閱表格：

| Analytics資料元素 | Analytics範例 | Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics資料作為未使用的訊號**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_贊_ this]
>
>* [特徵](../features/traits/trait-details-page.md)
>* [訊號、特徵和區段](../reference/signal-trait-segment.md)
>* [索引鍵值對說明](../reference/key-value-pairs-explained.md)
>* [關鍵變數的首碼需求](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

[!DNL Flash] 您物件的程式碼，以傳送Analytics資料至Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

