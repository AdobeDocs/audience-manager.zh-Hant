---
description: 收集從FLA檔傳送到Analytics的資料，並在Audience Manager中處理該資訊。
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超出此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

收集從FLA檔傳送到Analytics的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是 [!DNL ActionScript] 程式碼庫可讓您在Audience Manager中處理視訊播放資料。 [!DNL Flash DIL] 透過在Adobe中擷取SWF內容來運作 [!UICONTROL AppMeasurement] 程式庫會傳入Analytics。 [!DNL Flash DIL] 將該資料傳送至獨立的 [!UICONTROL DIL] JavaScript資料收集模組，可將該資訊傳遞至Audience Manager。 Analytics資料( [!UICONTROL Props]， [!UICONTROL eVars]、事件等) 擷取自 [!DNL FLA] 在Audience Manager中，檔案是以特徵或未使用訊號的形式提供。

## FlashDIL資料收集的需求 {#requirements}

一般實作和程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* 此 [!UICONTROL DIL] 類別庫( `dil.swc`)。 取得 [!UICONTROL DIL] 合作夥伴解決方案連絡人的類別庫。

* JavaScript [!UICONTROL DIL] 頁面上的資料收集程式碼。
* [DILActionScript庫](../dil/dil-flash.md#flash-dil-actionscript) 已載入您要從中收集資料的Flash物件中。
* Adobe [!DNL AppMeasurement] [!DNL AS] 程式庫（3.5.2版或更新版本）已載入 [!DNL Flash] 您想要從中收集資料的物件。

**將AllowScriptAccess設定為 `Always` 或`sameDomain`**

此 `AllowScriptAccess` 在載入HTML檔案的SWF程式碼中，會控制從SWF檔案內執行傳出URL存取的能力。 當您設定 [!UICONTROL Flash DIL] 資料整合，確認Flash `AllowScriptAccess` 引數已設為 `always` 或 `sameDomain`. [!UICONTROL Flash DIL] 如果符合下列條件，資料收集將無法運作 `AllowScriptAccess` 設為 `never`. 另請參閱 [控制指令碼或主機網頁的存取](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] 程式碼放置**

嘗試放置JS [!UICONTROL DIL] 頁面上的資料收集模組，使其在 [!DNL FLA] 檔案。 當 [!DNL FLA] 檔案會先載入，在 [!UICONTROL DIL] 資料收集準備就緒，可能會遺漏初始資料訊號 [!UICONTROL Flash DIL] 傳送至該模組。 不過，一旦例項化， [!UICONTROL DIL] 資料收集模組將擷取所有由傳遞的後續SWF檔案資料 [!UICONTROL Flash DIL].

## FlashDIL所收集的資料 {#data-collected}

[!UICONTROL Flash DIL] 從Adobe擷取頁面檢視、連結追蹤、媒體追蹤和其他媒體檢視事件 [!UICONTROL AppMeasurement] 資料庫。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面檢視事件**

除非另有指定 `s.trackVars`， [!UICONTROL Flash DIL] 從Adobe AppMeasurement收集下列資料：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結追蹤事件**

除非另有指定 `s.linkTrackVars`， [!UICONTROL Flash DIL] 從Adobe收集下列資料 [!UICONTROL AppMeasurement]：

* `pe` （呼叫的追蹤連結型別）
* `pev1` (連結 URL)
* `pev2`（連結文字）

**媒體追蹤事件**

除非另有指定 `s.Media.trackVars`， [!UICONTROL Flash DIL] 收集「頁面檢視事件」區段中列舉的所有資料。

**其他資料點**

預設會收集來自這些引數的資料：

* `mediaName` （媒體/視訊元素名稱）
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` （廣告巢狀內嵌於其下的主要媒體內容名稱）
* `mediaAdParentPod` （廣告播放所在主要內容中的Pod或廣告插播）
* `mediaAdParentPodPos` (Pod內播放廣告的數值位置。 一個Pod可以播放多個廣告。

## 以Audience ManagerFlashDIL資料 {#flash-dil-data}

此 [!UICONTROL Flash DIL] 模組會將Adobe AppMeasurement資料變成Audience Manager特徵和未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]， [!UICONTROL eVars]，而事件的運作方式與Audience Manager中的特徵類似。 特徵是機碼值組，用於建立區段。 例如，在Analytics的Prop中，例如 `c30=foo`， `c30` 是索引鍵（常數）和 `foo` 是值（變數）。

**比對Audience Manager特徵與Analytics變數**

若要使用傳遞的Analytics資料 [!UICONTROL Flash DIL]，您應該建立鍵值前置詞為的Audience Manager特徵 `c_`.

請參閱表格以取得範例：

| Analytics資料元素 | Analytics範例 | 作為Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**將資料DIL/分析為未使用的訊號**

Audience Manager接受Analytics [!UICONTROL Props]， [!UICONTROL eVars]、和事件，即使沒有對應的特徵也是如此。 在這種情況下，無法建立特徵，資料會顯示在 [未使用的訊號報表](../reporting/dynamic-reports/unused-signals.md) 而非。 若要充分運用這項資訊，請建立符合Analytics資料（由傳入）的Audience Manager特徵 [!UICONTROL Flash DIL] 資料庫。

## FlashDILActionScript庫 {#flash-dil-actionscript}

您的程式碼 [!DNL Flash] 物件，可將Analytics資料傳送至Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 針對每個 [!DNL Flash] 物件，程式碼支援一個合作夥伴例項( `d.partner`)。
>
>* 需要Adobe [!UICONTROL AppMeasurement] [!DNL AS] 程式庫3.5.2版或更新版本。

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
