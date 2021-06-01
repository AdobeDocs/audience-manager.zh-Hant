---
description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-title: Flash DIL
solution: Audience Manager
title: FlashDIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL實作
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# Flash DIL{#flash-dil}

收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是程 [!DNL ActionScript] 式碼程式庫，可讓您以Audience Manager處理視訊播放資料。[!DNL Flash DIL] 其運作方式是擷取Adobe程式庫 [!UICONTROL AppMeasurement] 傳入Analytics的SWF內容。[!DNL Flash DIL] 會將該資料傳送至個別 [!UICONTROL DIL] 的JavaScript資料收集模組，由此將該資訊傳遞至Audience Manager。分析資料（[!UICONTROL Props]、[!UICONTROL eVars]、事件等） 從[!DNL FLA]檔案擷取的資料，在Audience Manager中可作為特徵或未使用的訊號。

## FlashDIL資料收集需求 {#requirements}

一般實作與程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* [!UICONTROL DIL]類庫(`dil.swc`)。 從您的合作夥伴解決方案聯繫人獲取[!UICONTROL DIL]類庫。

* 頁面上的JavaScript [!UICONTROL DIL]資料收集程式碼。
* [DIL](../dil/dil-flash.md#flash-dil-actionscript) ActionScript程式庫，載入至您要收集資料的Flash物件中。
* Adobe[!DNL AppMeasurement] [!DNL AS]程式庫（3.5.2版或更新版本）載入了您要從中收集資料的[!DNL Flash]物件。

**將AllowScriptAccess設定為 `Always` 或`sameDomain`**

載入SWF檔案的HTML代碼中的`AllowScriptAccess`控制從SWF檔案中執行出站URL訪問的能力。 設定[!UICONTROL Flash DIL]資料整合時，請確定Flash`AllowScriptAccess`參數設為`always`或`sameDomain`。 [!UICONTROL Flash DIL] 如果設為，資料收 `AllowScriptAccess` 集將無法運 `never`作。請參閱[控制對指令碼的訪問或主機網頁](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS程 [!UICONTROL DIL] 式碼放置**

嘗試將JS [!UICONTROL DIL]資料收集模組放置在頁面上，使其在[!DNL FLA]檔案之前載入。 當[!DNL FLA]檔案先載入時，在[!UICONTROL DIL]資料收集準備就緒之前，您可能會遺漏[!UICONTROL Flash DIL]傳送至該模組的初始資料訊號。 但是，在實例化後，[!UICONTROL DIL]資料收集模組將捕獲由[!UICONTROL Flash DIL]傳入的所有後續SWF檔案資料。

## 由FlashDIL{#data-collected}收集的資料

[!UICONTROL Flash DIL] 從Adobe程式庫中擷取頁面檢視、連結追蹤、媒體追蹤和其他媒體檢視 [!UICONTROL AppMeasurement] 事件。

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

除非`s.linkTrackVars`另有指定，[!UICONTROL Flash DIL]會從Adobe[!UICONTROL AppMeasurement]收集下列資料：

* `pe` （呼叫的追蹤連結類型）
* `pev1` (連結 URL)
* `pev2`（連結文字）

**媒體追蹤事件**

除非`s.Media.trackVars`另有指定，否則[!UICONTROL Flash DIL]會收集「頁面檢視事件」區段中列舉的所有資料。

**其他資料點**

預設會收集來自這些參數的資料：

* `mediaName` （媒體/影片元素名稱）
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` （廣告巢狀內嵌的主要媒體內容名稱）
* `mediaAdParentPod` （廣告播放所在主要內容中的Pod或廣告插播）
* `mediaAdParentPodPos` (Pod內播放廣告的數值位置。一個Pod內可播放多個廣告。

## FlashDILAudience Manager{#flash-dil-data}中的資料

[!UICONTROL Flash DIL]模組可將Adobe AppMeasurement資料轉換為Audience Manager特徵和未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件的運作方式與Audience Manager中的特徵相似。 特徵是機碼值組，可用來建立區段。 例如，在`c30=foo`之類的Analytics Prop中，`c30`是索引鍵（常數）,`foo`是值（變數）。

**比對Audience Manager特徵與Analytics變數**

若要使用[!UICONTROL Flash DIL]傳遞的Analytics資料，您應建立Audience Manager特徵，其鍵值應加上`c_`前置詞。

如需範例，請參閱表格：

| Analytics資料元素 | Analytics範例 | 作為Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/分析資料作為未使用的訊號**

Audience Manager接受Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件，即使沒有對應的特徵亦然。 在此情況下，資料無法用於特徵建立，而會出現在[未使用的訊號報表](../reporting/dynamic-reports/unused-signals.md)中。 若要充分運用這些資訊，請建立符合[!UICONTROL Flash DIL]資料庫所傳入之Analytics資料的Audience Manager特徵。

## FlashDILActionScript庫{#flash-dil-actionscript}

[!DNL Flash]物件的程式碼，以傳送Analytics資料至Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 對於每個[!DNL Flash]物件，程式碼僅支援一個合作夥伴例項(`d.partner`)。
   >
   >
* 需要Adobe[!UICONTROL AppMeasurement] [!DNL AS]程式庫3.5.2版或更新版本。


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
* [訊號、特徵和區段](../reference/signal-trait-segment.md)
* [索引鍵值配對說明](../reference/key-value-pairs-explained.md)
* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)

