---
description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# Flash DIL{#flash-dil}

收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是可讓 [!DNL ActionScript] 您在Audience Manager中處理視訊播放資料的程式碼庫。[!DNL Flash DIL] 擷取Adobe資料庫傳入Analytics [!UICONTROL AppMeasurement] 的SWF內容。[!DNL Flash DIL] 傳送該資料至個別的 [!UICONTROL DIL] JavaScript資料收集模組，然後將該資訊傳送至Audience Manager。分析資料（[!UICONTROL Props]、[!UICONTROL eVars]、事件等） 從[!DNL FLA]檔案擷取的影像，在Audience Manager中可做為特徵或未使用的訊號。

## Flash DIL資料收集需求{#requirements}

一般實作與程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* [!UICONTROL DIL]類庫(`dil.swc`)。 從您的「合作夥伴解決方案」聯絡人取得[!UICONTROL DIL]類別程式庫。

* 頁面上的JavaScript [!UICONTROL DIL]資料收集代碼。
* [DIL ActionScript程式](../dil/dil-flash.md#flash-dil-actionscript) 庫，載入至您要收集資料的Flash物件。
* Adobe [!DNL AppMeasurement] [!DNL AS]程式庫（3.5.2版或更新版本）已載入您要從中收集資料的[!DNL Flash]物件。

**將AllowScriptAccess設為 `Always` 或`sameDomain`**

載入SWF檔案的HTML程式碼中的`AllowScriptAccess`可控制從SWF檔案執行傳出URL存取的功能。 當您設定[!UICONTROL Flash DIL]資料整合時，請確定Flash `AllowScriptAccess`參數已設為`always`或`sameDomain`。 [!UICONTROL Flash DIL] 如果設為，資料收 `AllowScriptAccess` 集將無法運作 `never`。請參閱[控制指令碼訪問或主機網頁](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS程 [!UICONTROL DIL] 式碼位置**

嘗試將JS [!UICONTROL DIL]資料收集模組置於頁面上，讓它載入至[!DNL FLA]檔案之前。 當[!DNL FLA]檔案先載入時，在[!UICONTROL DIL]資料收集準備就緒之前，您可能會遺漏[!UICONTROL Flash DIL]傳送至該模組的初始資料訊號。 但是，當實例化後，[!UICONTROL DIL]資料收集模組將捕獲[!UICONTROL Flash DIL]傳入的所有後續SWF檔案資料。

## Flash DIL收集的資料{#data-collected}

[!UICONTROL Flash DIL] 從Adobe資料庫擷取頁面檢視、連結追蹤、媒體追蹤和其他媒體檢視 [!UICONTROL AppMeasurement] 事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面檢視事件**

除非`s.trackVars`另有指定，[!UICONTROL Flash DIL]會從Adobe AppMeasurement收集下列資料：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結追蹤事件**

除非`s.linkTrackVars`另有指定，[!UICONTROL Flash DIL]會從Adobe [!UICONTROL AppMeasurement]收集下列資料：

* `pe` （呼叫的追蹤連結類型）
* `pev1` (連結 URL)
* `pev2`（連結文字）

**媒體追蹤事件**

除非`s.Media.trackVars`另有指定，[!UICONTROL Flash DIL]會收集「頁面檢視事件」區段中列舉的所有資料。

**其他資料點**

預設會收集這些參數的資料：

* `mediaName` （媒體／視訊元素名稱）
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` （廣告巢狀內嵌的主要媒體內容名稱）
* `mediaAdParentPod` （廣告播放之主要內容中的pod或廣告插播）
* `mediaAdParentPodPos` (廣告播放的Pod內的數值位置。在Pod中可播放多個廣告。

## Audience Manager中的Flash DIL資料{#flash-dil-data}

[!UICONTROL Flash DIL]模組可將Adobe AppMeasurement資料轉換為Audience Manager特性和未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件的運作方式與Audience Manager中的特徵類似。 特徵是關鍵值配對，用於建立區段。 例如，在`c30=foo`等Analytics prop中，`c30`是索引鍵（常數）,`foo`是值（變數）。

**將Audience Manager特徵與Analytics變數相符**

若要使用[!UICONTROL Flash DIL]傳遞的Analytics資料，您應建立Audience Manager特徵，其關鍵值前置有`c_`。

如需範例，請參閱表格：

| Analytics資料元素 | Analytics範例 | 身為Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics資料做為未使用的訊號**

Audience Manager接受Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件，即使沒有對應的特徵亦然。 在此情況下，資料無法用於特徵建立，而會出現在[未使用的信號報表](../reporting/dynamic-reports/unused-signals.md)中。 若要充份運用這些資訊，請建立符合[!UICONTROL Flash DIL]程式庫所傳入之Analytics資料的Audience Manager特徵。

## Flash DIL ActionScript程式庫{#flash-dil-actionscript}

[!DNL Flash]物件的程式碼，以傳送Analytics資料至Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 對於每個[!DNL Flash]對象，代碼僅支援一個合作夥伴實例(`d.partner`)。
   >
   >
* 需要Adobe [!UICONTROL AppMeasurement] [!DNL AS]程式庫3.5.2版或更新版本。


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [特徵](../features/traits/trait-details-page.md)
>* [訊號、特徵和區段](../reference/signal-trait-segment.md)
>* [索引鍵值配對說明](../reference/key-value-pairs-explained.md)
>* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)

