---
description: 收集從FLA檔傳送到Analytics的資料，並在Audience Manager中處理該資訊。
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: FlashDIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# FlashDIL{#flash-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe在此點之後不會開發[!DNL DIL]。 建議客戶針對[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

收集從FLA檔傳送到Analytics的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL]是[!DNL ActionScript]程式碼庫，可讓您在Audience Manager中處理視訊播放資料。 [!DNL Flash DIL]的運作方式是擷取Adobe[!UICONTROL AppMeasurement]資料庫傳入Analytics的SWF內容。 [!DNL Flash DIL]會將該資料傳送至個別的[!UICONTROL DIL] JavaScript資料收集模組，以便傳遞該資訊給Audience Manager。 Analytics資料（ [!UICONTROL Props]、[!UICONTROL eVars]、事件等） 從[!DNL FLA]檔案擷取的訊號，可在Audience Manager中作為特徵或未使用的訊號使用。

## FlashDIL資料收集的需求 {#requirements}

一般實作和程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash]資料收集需要：

* [!UICONTROL DIL]類別庫( `dil.swc`)。 從您的合作夥伴解決方案連絡人取得[!UICONTROL DIL]類別庫。

* 頁面上的JavaScript [!UICONTROL DIL]資料收集代碼。
* [DILActionScript庫](../dil/dil-flash.md#flash-dil-actionscript)載入到您要收集資料的Flash物件中。
* Adobe[!DNL AppMeasurement] [!DNL AS]資料庫（版本3.5.2或更新版本）已載入您想要從中收集資料的[!DNL Flash]物件。

**將AllowScriptAccess設定為`Always`或`sameDomain`**

載入SWF檔案的HTML程式碼中的`AllowScriptAccess`控制從SWF檔案執行輸出URL存取的能力。 當您設定[!UICONTROL Flash DIL]資料整合時，請確定Flash`AllowScriptAccess`引數設定為`always`或`sameDomain`。 如果`AllowScriptAccess`設為`never`，[!UICONTROL Flash DIL]資料彙集將無法運作。 請參閱[控制指令碼或主機網頁的存取](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS [!UICONTROL DIL]程式碼位置**

嘗試將JS [!UICONTROL DIL]資料收集模組放在頁面上，使其在[!DNL FLA]檔案之前載入。 當[!DNL FLA]檔案先載入，[!UICONTROL DIL]資料收集準備就緒之前，您可能會遺漏[!UICONTROL Flash DIL]傳送給該模組的初始資料訊號。 不過，一旦具現化，[!UICONTROL DIL]資料收集模組將會擷取[!UICONTROL Flash DIL]傳入的所有後續SWF檔案資料。

## FlashDIL所收集的資料 {#data-collected}

[!UICONTROL Flash DIL]從Adobe[!UICONTROL AppMeasurement]媒體櫃擷取頁面檢視、連結追蹤、媒體追蹤和其他媒體檢視事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面檢視事件**

除非`s.trackVars`另有指定，[!UICONTROL Flash DIL]否則會從Adobe AppMeasurement收集下列資料：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結追蹤事件**

除非`s.linkTrackVars`另有指定，[!UICONTROL Flash DIL]會從Adobe[!UICONTROL AppMeasurement]收集下列資料：

* `pe` （呼叫的追蹤連結型別）
* `pev1` （連結URL）
* `pev2`（連結文字）

**媒體追蹤事件**

除非`s.Media.trackVars`另有指定，[!UICONTROL Flash DIL]會收集頁面檢視事件區段中列舉的所有資料。

**其他資料點**

預設會收集來自這些引數的資料：

* `mediaName` （媒體/視訊元素名稱）
* `mediaAdName` （廣告名稱）
* `mediaAdParentName` （廣告巢狀內嵌於其下的主要媒體內容名稱）
* `mediaAdParentPod` （廣告播放所在主要內容中的Pod或廣告插播）
* `mediaAdParentPodPos` (Pod內播放廣告的數值位置。 一個Pod可以播放多個廣告。

## 以Audience ManagerFlashDIL資料 {#flash-dil-data}

[!UICONTROL Flash DIL]模組會將Adobe AppMeasurement資料轉換為Audience Manager特徵與未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件的運作方式與Audience Manager中的特徵類似。 特徵是機碼值組，用於建立區段。 例如，在類似`c30=foo`的Analytics Prop中，`c30`是索引鍵（常數），`foo`是值（變數）。

**將Audience Manager特徵與Analytics變數比對**

若要使用[!UICONTROL Flash DIL]傳遞的Analytics資料，您應該建立鍵值以`c_`為前置詞的Audience Manager特徵。

請參閱表格以取得範例：

| Analytics資料元素 | Analytics範例 | 作為Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/分析資料為未使用的訊號**

即使沒有對應的特徵，Audience Manager也會接受Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件。 在此情況下，資料無法用於特徵建立，而是顯示在[未使用的訊號報表](../reporting/dynamic-reports/unused-signals.md)中。 若要充分利用此資訊，請建立符合[!UICONTROL Flash DIL]資料庫所傳入Analytics資料的Audience Manager特徵。

## FlashDILActionScript庫 {#flash-dil-actionscript}

將Analytics資料傳送至Audience Manager的[!DNL Flash]物件代碼。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 對於每個[!DNL Flash]物件，程式碼僅支援一個夥伴執行個體( `d.partner`)。
>
>* 需要Adobe[!UICONTROL AppMeasurement] [!DNL AS]程式庫3.5.2版或更新版本。

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
