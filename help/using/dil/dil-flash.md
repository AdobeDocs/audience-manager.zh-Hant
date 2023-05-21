---
description: 收集從FLA檔案發送到分析的資料，並在Audience Manager中處理該資訊。
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 4%

---

# Flash DIL{#flash-dil}

收集從FLA檔案發送到分析的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是 [!DNL ActionScript] 代碼庫，允許您在Audience Manager中處理視頻播放資料。 [!DNL Flash DIL] 通過捕獲SWF內容Adobe [!UICONTROL AppMeasurement] 庫會轉入分析。 [!DNL Flash DIL] 將資料發送到 [!UICONTROL DIL] JavaScript資料收集模組，將該資訊傳遞給Audience Manager。 分析資料( [!UICONTROL Props]。 [!UICONTROL eVars]、事件等) 從 [!DNL FLA] 檔案在Audience Manager中可用作特徵或未使用的信號。

## FlashDIL資料收集要求 {#requirements}

一般實施和與代碼相關的要求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* 的 [!UICONTROL DIL] 類庫( `dil.swc`)。 獲取 [!UICONTROL DIL] 合作夥伴解決方案聯繫人提供的類庫。

* JavaScript [!UICONTROL DIL] 頁面上的資料收集代碼。
* [DILActionScript庫](../dil/dil-flash.md#flash-dil-actionscript) 載入到要從中收集資料的Flash對象中。
* Adobe [!DNL AppMeasurement] [!DNL AS] 庫(3.5.2版或更高版本)已載入 [!DNL Flash] 要從中收集資料的對象。

**將AllowScriptAccess設定為 `Always` 或`sameDomain`**

的 `AllowScriptAccess` 在載入HTML檔案的SWF代碼中，控制從SWF檔案內執行出站URL訪問的能力。 配置 [!UICONTROL Flash DIL] 資料整合，確保Flash `AllowScriptAccess` 參數設定為 `always` 或 `sameDomain`。 [!UICONTROL Flash DIL] 資料收集在 `AllowScriptAccess` 設定為 `never`。 請參閱 [控制對指令碼或主機網頁的訪問](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS [!UICONTROL DIL] 代碼放置**

嘗試放置JS [!UICONTROL DIL] 頁面上的資料收集模組，以便在 [!DNL FLA] 的子菜單。 當 [!DNL FLA] 檔案先載入，之前 [!UICONTROL DIL] 資料收集已就緒，您可能會錯過初始資料信號 [!UICONTROL Flash DIL] 發送到該模組。 但是，一旦實例化， [!UICONTROL DIL] 資料收集模組將捕獲傳入的所有後續SWF檔案資料 [!UICONTROL Flash DIL]。

## 按Flash收集的資料DIL {#data-collected}

[!UICONTROL Flash DIL] 從Adobe捕獲頁面視圖、連結跟蹤、介質跟蹤和其他介質視圖事件 [!UICONTROL AppMeasurement] 的下界。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面視圖事件**

除非另有指定 `s.trackVars`。 [!UICONTROL Flash DIL] 從Adobe AppMeasurement收集以下資料：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結跟蹤事件**

除非另有指定 `s.linkTrackVars`。 [!UICONTROL Flash DIL] 從Adobe收集以下資料 [!UICONTROL AppMeasurement]:

* `pe` （調用的跟蹤連結類型）
* `pev1` (連結 URL)
* `pev2`（連結文本）

**媒體跟蹤事件**

除非另有指定 `s.Media.trackVars`。 [!UICONTROL Flash DIL] 收集「頁面視圖事件」部分中枚舉的所有資料。

**其他資料點**

預設情況下，會從這些參數收集資料：

* `mediaName` （媒體/視頻元素名稱）
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` （廣告嵌套在其中的主媒體內容的名稱）
* `mediaAdParentPod` （廣告播放的主要內容中的pod或ad中斷）
* `mediaAdParentPodPos` (廣告播放的盒中的數字位置。 一個廣告可以在一個盒子裡播放。

## FlashDIL資料在Audience Manager {#flash-dil-data}

的 [!UICONTROL Flash DIL] 模組將Adobe AppMeasurement資料轉化為Audience Manager特徵和未使用信號。

<!-- 

c_flash_dil_in_aam.xml

 -->

分析 [!UICONTROL Props]。 [!UICONTROL eVars]而且事件在Audience Manager中就像特質一樣。 特徵是關鍵值對，用於構建段。 例如，在類似於 `c30=foo`。 `c30` 是鍵（a常數） `foo` 是值（變數）。

**將Audience Manager特性與分析變數匹配**

使用傳遞的分析資料 [!UICONTROL Flash DIL]，應建立鍵值前置詞為的Audience Manager特徵 `c_`。

有關示例，請參見表：

| 分析資料元素 | 分析示例 | 作為Audience Manager特性 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **埃瓦** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/分析資料作為未使用的信號**

Audience Manager接受分析 [!UICONTROL Props]。 [!UICONTROL eVars]、事件，即使沒有相應的特徵。 在這種情況下，資料不可用於特徵建立，並顯示在 [「 Unused Signals 」報告](../reporting/dynamic-reports/unused-signals.md) 的雙曲餘切值。 要充分利用此資訊，請建立與傳入的Analytics資料匹配的Audience Manager特徵 [!UICONTROL Flash DIL] 的下界。

## FlashDILActionScript庫 {#flash-dil-actionscript}

代碼 [!DNL Flash] 將分析資料發送到Audience Manager的對象。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 每個 [!DNL Flash] 對象，代碼支援一個夥伴實例( `d.partner`)。
>
>* 需要Adobe [!UICONTROL AppMeasurement] [!DNL AS] 庫版本3.5.2或更高版本。


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

