---
description: 概觀Audience Manager如何與其他資料提供者和系統交換資訊。
seo-description: 概觀Audience Manager如何與其他資料提供者和系統交換資訊。
seo-title: 資料整合方法
solution: Audience Manager
title: 資料整合方法
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# 資料整合方法 {#data-integration-methods}

概觀Audience Manager如何與其他資料提供者和系統交換資訊。

## 支援的資料整合方法：即時和[!DNL Server-to-Server] {#supported-methods}

選擇正確的整合方法取決於業務需求與資料合作夥伴的技術能力的組合。 Audience Manager透過下列任一方法與其他資料提供者交換訪客資訊：

* **即時：當使用** 者瀏覽您的網站時，立即傳輸資料。此方法也稱為&#x200B;*`synchronous`*&#x200B;整合。
* **批次([!DNL Server-to-Server])：訪** 客離開頁面後，在設定的排程中在伺服器間傳輸資料。此方法也稱為&#x200B;*`out-of-band`*&#x200B;或&#x200B;*`asynchronous`*&#x200B;整合。

## 必要條件：建立特徵分類法{#prereqs}

在整合程式開始之前，請記得在[!DNL Audience Manager] UI中[建立traits](../features/traits/create-onboarded-rule-based-traits.md)和[資料夾結構](../features/traits/trait-storage.md#create-trait-storage-folder)。 該分類將包含在邏輯層次中組織的所有[!UICONTROL traits]。

## 整合使用案例{#integration-use-cases}

Audience Manager資料整合方法的使用案例摘要，以及各方法的優缺點。

### 即時[!DNL Server-to-Server]整合

<!-- c_int_types_use_cases.xml -->

即時[!DNL server-to-server]資料整合可快速同步Audience Manager伺服器與其他定位系統之間的使用者資料。 在大多數情況下，資料交換會在數秒或數分鐘內進行，視定位系統的重新整理率而定。 但請注意，目標系統會決定此重新整理間隔，而非Audience Manager。 此外，刷新率在不同系統之間可能不同。 即時[!UICONTROL server-to-server]整合是資料交換的偏好整合類型。 Audience Manager只要定位合作夥伴可以支援，就會使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">讓您在頁面、視訊播放器等中不再看見使用者，就能符合使用者群體的資格。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 減少頁面的HTTP呼叫數。 較少的呼叫有助於保留使用者體驗。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">協助您進行時間敏感型定位，以便快速對符合資格的使用者採取行動。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">移至Offsite定位時DSP很實用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 當您需要針對相同頁面或下一頁的使用者進行定位時，根據該群體的使用者資格，Onsite定位的用途會變得較少。</td>
 </tr>
</table>

### [!DNL Server-to-Server] 批次整合

[!DNL server-to-server]批次整合會捆綁資料，並以設定的間隔傳送資料至其他系統，而非近乎即時地傳送。 資料傳輸間隔從24小時開始。 有些資料提供者僅支援此整合類型。 不過，我們已看到從批次整合向即時整合方式轉變的趨勢。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">讓您在頁面、視訊播放器等中不再看見使用者，就能符合使用者群體的資格。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">對於非時間敏感的定位非常有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 同步間隔可以延遲針對最新資料的定位。</td>
 </tr>
</table>

### 即時呼叫

即時呼叫會立即與Audience Manager交換資料，當使用者造訪您的網站或在頁面上採取動作時。 透過此方法，定位系統會取得最新的細分資格資料，並在內容或廣告傳遞決策期間可考慮這些資訊。 此外，此程式適用於發佈者廣告伺服器，我們會將限定區段更新為第一方Cookie，並讀取到廣告呼叫中做為索引鍵值配對。 目前，Audience Manager使用即時呼叫與[!DNL Adobe Target]和其他內容管理系統整合。

<table> 
 <tr>
  <td> <p>優勢: </p></td>
  <td> <p> 可讓您根據最近的區段資格來定位下一頁、內容區域或廣告曝光。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺點： </p></td>
  <td> <p>從頁面新增對Audience Manager的呼叫。</p></td>
 </tr> 
</table>


### 像素與定位系統同步

像素同步會將區段對應至頁面上的像素。 當用戶符合特定段的條件時，該像素會觸發和發送資料。 像素同步是一種基本且不可靠的資料傳輸機制。 頂級資料供應商和系統很少使用它。

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> <p> 即時資料傳輸。 </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>缺點： </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">可從頁面新增許多用戶端呼叫。 </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">資料傳輸不可靠。 5%到20%的損失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## 如何選擇資料傳送方法{#data-delivery-choices}

說明透過同步（即時）或非同步（伺服器對伺服器）方法傳送資料的技術和商業理由。

<!-- c_int_delivery_choices.xml -->

### 選擇資料傳送類型

* **技術考量：** 資料傳送取決於資料合作夥伴的技術能力。Audience Manager可從瀏覽器或透過離線伺服器對伺服器通訊程式批次更新，即時傳送／接收資料。
* **業務考慮** 事項：選擇一種或另一種傳送方法的業務原因取決於目標合作夥伴的技術能力以及您希望如何使用此資料。通常，同步資料傳輸在您需要立即對使用者資料採取動作時非常有用。 非同步資料傳輸在不需要立即動作，以及您有時間建立更深入的使用者設定檔以供日後使用時，可能很有用。

## 即時資料傳輸進程{#real-time-data-transfer-process}

概述Audience Manager如何與第三方供應商進行同步資料交換。

### 即時資料傳輸

<!-- c_int_overview_sync.xml -->

即時資料傳輸會以使用者造訪或在您的網站上採取動作的方式傳送和接收區段ID。 通常，同步資料傳輸在您需要立即取得使用者資格或劃分使用者瀏覽庫存時非常有用。

### 即時資料整合步驟

即時資料整合程式的運作方式如下：

1. 使用者瀏覽包含Audience Manager代碼的客戶網站。
1. Audience Manager載入Iframe並對[!UICONTROL Data Collection Server]([!DNL DCS])進行調用。
1. [!DNL DCS]會呼叫協力廠商伺服器（即時），以檢查廠商是否有使用者的區段資訊。
1. 第三方會傳回該使用者的區段資訊給Audience Manager。
1. Audience Manager收錄區段資訊，並讓它可供定位。

![](assets/rt_reduce70.png)

## 批次資料傳輸流程 {#batch-data-transfer-process}

概述Audience Manager如何與協力廠商同步（即時）交換資料。

### 批次資料整合

<!-- c_int_overview_async.xml -->

批次([!DNL server-to-server])資料整合程式遵循即時資料傳輸程式中概述的大部分步驟。 不過，使用者資訊不會立即傳回區段ID，而是會儲存到我們的伺服器，並定期與協力廠商資料提供者同步。 在下列情況下，非同步資料傳輸程式非常有用：

* 不需要立即傳送資料。
* 收集資料，以建立龐大的細分使用者群。
* 您想要減少來自瀏覽器的資料不一致和`HTTP`呼叫。

### 批次資料整合步驟

1. 使用者瀏覽客戶網站。
1. Audience Manager和協力廠商資料提供者會為訪客指派唯一ID（通常使用Cookie）。
1. Audience Manager呼叫協力廠商資料提供者，以符合訪客ID。
1. 排程的請求（通常在每日間隔內）會在Audience Manager和您的第三方資料提供者之間交換訪客區段資料。

![](assets/s2s_70.png)

有關描述Audience Manager處理入站和出站[!DNL Server-to-Server]([!UICONTROL S2S])檔案傳輸時的時間幀的資訊，請參閱[報告和檔案傳輸時間幀准則](../reference/reporting-file-transfer-timeframe.md)。
