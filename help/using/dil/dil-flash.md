---
description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-description: 收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Flash DIL{#flash-dil}

收集從FLA檔案傳送至Analytics的資料，並在Audience Manager中處理該資訊。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是程式 [!DNL ActionScript] 碼庫，可讓您在Audience Manager中處理視訊播放資料。 [!DNL Flash DIL] 擷取Adobe資料庫傳入Analytics [!UICONTROL AppMeasurement] 的SWF內容。 [!DNL Flash DIL] 傳送該資料至個別的 [!UICONTROL DIL] JavaScript資料收集模組，然後將該資訊傳送至Audience Manager。 分析資 [!UICONTROL Props]料( [!UICONTROL eVars]、事件等) 從檔案擷 [!DNL FLA] 取的內容，在Audience Manager中可做為特徵或未使用的訊號。

## Flash DIL資料收集需求 {#requirements}

一般實作與程式碼相關需求。

<!-- 

c_flash_dil_intro.xml

 -->

**實作需求**

[!UICONTROL Flash] 資料收集需要：

* 類別 [!UICONTROL DIL] 程式庫( `dil.swc`)。 從您的合 [!UICONTROL DIL] 作夥伴解決方案聯絡人取得類別程式庫。

* 頁面上 [!UICONTROL DIL] 的JavaScript資料收集代碼。
* [您要從Flash物件中載入](../dil/dil-flash.md#flash-dil-actionscript) DIL ActionScript程式庫，以收集資料。
* Adobe [!DNL AppMeasurement][!DNL AS] Library（3.5.2版或更新版本）已載入您要從中收 [!DNL Flash] 集資料的物件。

**將AllowScriptAccess設為`Always`或`sameDomain`**

載 `AllowScriptAccess` 入SWF檔案的HTML程式碼可控制從SWF檔案執行傳出URL存取的能力。 設定資料整 [!UICONTROL Flash DIL] 合時，請確定Flash `AllowScriptAccess` 參數設為 `always` 或 `sameDomain`。 [!UICONTROL Flash DIL] 如果設為，資料收 `AllowScriptAccess` 集將無法運作 `never`。 請參 [閱控制指令碼存取或主機網頁](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS代[!UICONTROL DIL]碼位置**

嘗試將JS資料收 [!UICONTROL DIL] 集模組置於頁面上，以便在檔案之前載 [!DNL FLA] 入。 當檔案 [!DNL FLA] 先載入時，在資料收 [!UICONTROL DIL] 集準備就緒之前，您可能會遺漏傳送至該模 [!UICONTROL Flash DIL] 組的初始資料訊號。 不過，當執行個體化後，資 [!UICONTROL DIL] 料收集模組會擷取傳入的所有後續SWF檔案資料 [!UICONTROL Flash DIL]。

## Flash DIL收集的資料 {#data-collected}

[!UICONTROL Flash DIL] 從Adobe資料庫擷取頁面檢視、連結追蹤、媒體追蹤和其他媒體檢視事 [!UICONTROL AppMeasurement] 件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**頁面檢視事件**

除非另行指 `s.trackVars`定， [!UICONTROL Flash DIL] 否則從Adobe AppMeasurement收集下列資料：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**連結追蹤事件**

除非另行指 `s.linkTrackVars`定， [!UICONTROL Flash DIL] 否則從Adobe收集下列資料 [!UICONTROL AppMeasurement]:

* `pe` （呼叫的追蹤連結類型）
* `pev1` (連結 URL)
* `pev2`（連結文字）

**媒體追蹤事件**

除非另行指 `s.Media.trackVars`定， [!UICONTROL Flash DIL] 否則會收集「頁面檢視事件」區段中列舉的所有資料。

**其他資料點**

預設會收集這些參數的資料：

* `mediaName` （媒體／視訊元素名稱）
* `mediaAdName` (廣告名稱)
* `mediaAdParentName` （廣告巢狀內嵌的主要媒體內容名稱）
* `mediaAdParentPod` （廣告播放之主要內容中的pod或廣告插播）
* `mediaAdParentPodPos` (廣告播放的Pod內的數值位置。 在Pod中可播放多個廣告。

## Audience Manager中的Flash DIL資料 {#flash-dil-data}

此模 [!UICONTROL Flash DIL] 組將Adobe AppMeasurement資料轉換為Audience Manager特徵和未使用的訊號。

<!-- 

c_flash_dil_in_aam.xml

 -->

分析 [!UICONTROL Props]、 [!UICONTROL eVars]和事件的運作方式與Audience Manager中的特徵類似。 特徵是關鍵值配對，用於建立區段。 例如，在類似Analytics `c30=foo`prop中， `c30` 是索引鍵（常數） `foo` 和值（變數）。

**將Audience Manager特徵與Analytics變數相符**

若要使用透過的Analytics資 [!UICONTROL Flash DIL]料，您應建立具有前置關鍵值的Audience Manager特徵 `c_`。

如需範例，請參閱表格：

| Analytics資料元素 | Analytics範例 | 身為Audience Manager特徵 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics資料做為未使用的訊號**

Audience Manager接受Analytics [!UICONTROL Props]、 [!UICONTROL eVars]和事件，即使沒有對應的特徵。 在此情況下，資料無法用於特徵建立，而會出現在「未使用的 [訊號」報表](../reporting/dynamic-reports/unused-signals.md) 。 若要充份運用這些資訊，請建立符合資料庫所傳入之Analytics資料的Audience Manager特 [!UICONTROL Flash DIL] 性。

## Flash DIL ActionScript程式庫 {#flash-dil-actionscript}

您物件的程 [!DNL Flash] 式碼，以傳送Analytics資料至Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 對於每 [!DNL Flash] 個物件，程式碼僅支援一個合作夥伴例項( `d.partner`)。
   >
   >
* 需要Adobe [!UICONTROL AppMeasurement] Library 3.5.2版或更 [!DNL AS] 新版本。


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
>* [信號、特徵和區段](../reference/signal-trait-segment.md)
>* [說明的鍵值對](../reference/key-value-pairs-explained.md)
>* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)


<!-- Victor/Vlad: Do we still need this link? It doesn't look like this content has been migrated.
>* [AppMeasurement Flash, Flex, and OSMF Implementation Guide](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)
-->
