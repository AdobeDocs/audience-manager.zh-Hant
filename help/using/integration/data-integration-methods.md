---
description: 高級概述Audience Manager如何與其他資料提供商和系統交換資訊。
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: 資料整合方法
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 1%

---

# 資料整合方法 {#data-integration-methods}

高級概述Audience Manager如何與其他資料提供商和系統交換資訊。

## 支援的資料整合方法：即時和 [!DNL Server-to-Server] {#supported-methods}

選擇正確的整合方法取決於業務需求和資料合作夥伴的技術能力的組合。 Audience Manager通過以下任一方法與其他資料提供方交換訪問者資訊：

* **即時：** 當用戶訪問您的站點時立即傳輸資料。 此方法也稱為 *`synchronous`* 整合。
* **批([!DNL Server-to-Server]):** 訪問者離開頁面後，按預定計畫在伺服器之間傳輸資料。 此方法也稱為 *`out-of-band`* 或 *`asynchronous`* 整合。

## 先決條件：建立特質分類 {#prereqs}

在整合過程開始之前，切記 [創造性狀](../features/traits/create-onboarded-rule-based-traits.md) 和 [資料夾結構](../features/traits/trait-storage.md#create-trait-storage-folder) 的 [!DNL Audience Manager] UI。 分類將包含所有 [!UICONTROL traits] 按邏輯層次組織。

## 整合使用案例 {#integration-use-cases}

Audience Manager資料整合方法的用例概要，以及每種方法的優缺點。

### 即時 [!DNL Server-to-Server] 整合

<!-- c_int_types_use_cases.xml -->

即時 [!DNL server-to-server] 資料整合可快速同步Audience Manager伺服器和另一個目標系統之間的用戶資料。 在大多數情況下，根據目標系統的刷新率，資料交換在幾秒或幾分鐘內進行。 但請注意，目標系統決定了此刷新間隔，而不是Audience Manager。 此外，刷新率可在不同系統之間變化。 即時， [!UICONTROL server-to-server] 整合是資料交換的首選整合類型。 Audience Manager只要目標合作夥伴能夠支援，就使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">允許用戶在頁面上、視頻播放器等中不再看到段，從而對段進行限定。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 減少頁面中的HTTP調用數。 減少呼叫有助於保留用戶體驗。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">幫助進行時間敏感型目標確定，以便您可以快速對合格用戶執行操作。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">在移到異地目標時DSP非常有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 如果您需要針對同一頁或下一頁上的用戶，則根據該段的用戶資格確定，對現場定位效果不太有用。</td>
 </tr>
</table>

### [!DNL Server-to-Server] 批整合

A [!DNL server-to-server] 批處理整合將資料捆綁並以設定的時間間隔發送到其他系統，而不是以接近即時的時間發送。 資料傳輸間隔從24小時開始。 某些資料提供程式僅支援此整合類型。 但是，我們看到了從批量整合向即時整合方法的總體趨勢。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">允許用戶在頁面上、視頻播放器等中不再看到段，從而對段進行限定。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">對於非時間敏感的目標很有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 同步間隔可以針對最新資料延遲目標。</td>
 </tr>
</table>

### 即時呼叫

當用戶訪問您的站點或在頁面上執行操作時，即時調用帶有Audience Manager的交換資料。 通過這種方法，目標系統獲得最新的段資格資料，並可以在內容或廣告交付決策期間考慮該資訊。 此外，此過程與發佈伺服器廣告伺服器配合使用，在發佈伺服器中，我們將限定的段更新為第一方cookie，該cookie作為鍵值對被讀入廣告調用中。 目前，Audience Manager使用即時呼叫與 [!DNL Adobe Target] 以及其他內容管理系統。

<table> 
 <tr>
  <td> <p>優勢: </p></td>
  <td> <p> 允許您根據最近的段資格確定下一頁、內容區域或廣告印象。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺點： </p></td>
  <td> <p>從頁面向Audience Manager添加調用。</p></td>
 </tr> 
</table>


### 像素與目標系統同步

像素同步將段映射到頁面上的像素。 當用戶符合特定段時，該像素將觸發和發送資料。 像素同步是一種基本且不可靠的資料傳輸機制。 頂級資料提供商和系統很少使用它。

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> <p> 即時資料傳輸。 </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>缺點： </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">可以從頁面添加大量客戶端調用。 </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">資料傳輸不可靠。 5%到20%的損失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## 如何選擇資料傳遞方法 {#data-delivery-choices}

介紹通過同步（即時）或非同步（伺服器到伺服器）方法體系發送資料的技術和業務原因。

<!-- c_int_delivery_choices.xml -->

### 選擇資料傳遞類型

* **技術注意事項：** 資料交付取決於資料合作夥伴的技術能力。 Audience Manager可以通過離線、伺服器到伺服器的通信進程通過批更新即時發送/接收資料。
* **業務注意事項：** 選擇一種或另一種交付方法的業務原因取決於目標合作夥伴的技術能力以及您希望如何使用這些資料。 通常，當您需要立即對用戶資料採取操作時，同步資料傳輸非常有用。 當不需要立即執行操作並且您有時間構建更深入的用戶配置檔案以供以後使用時，非同步資料傳輸可能非常有用。

## 即時資料傳輸過程 {#real-time-data-transfer-process}

關於Audience Manager如何與第三方供應商執行同步資料交換的概述。

### 即時資料傳輸

<!-- c_int_overview_sync.xml -->

作為用戶訪問或在您的站點上執行操作，即時資料傳輸發送和接收段ID。 通常，在您需要立即確定用戶資格或對用戶進行細分時，同步資料傳輸非常有用，因為用戶在清單中導航。

### 即時資料整合步驟

即時資料整合過程的工作如下：

1. 用戶訪問包含Audience Manager代碼的客戶站點。
1. Audience Manager載入Iframe並調用 [!UICONTROL Data Collection Server] ([!DNL DCS])。
1. 的 [!DNL DCS] 調用第三方伺服器（即時）以檢查供應商是否具有有關用戶的任何段資訊。
1. 第三方將有關該用戶的段資訊返回給Audience Manager。
1. Audience Manager接收段資訊，並使其可用於目標。

![](assets/rt_reduce70.png)

## 批次資料傳輸流程 {#batch-data-transfer-process}

概述Audience Manager如何與第三方供應商同步（即時）交換資料。

### 批資料整合

<!-- c_int_overview_async.xml -->

批([!DNL server-to-server])資料整合過程遵循即時資料傳輸過程中概述的大部分步驟。 但是，用戶資訊不會立即返回段ID，而是會定期保存到我們的伺服器並與第三方資料提供程式同步。 非同步資料傳輸過程在以下情況下非常有用：

* 不需要立即資料傳輸。
* 收集資料以構建一個大的分段用戶池。
* 您希望減少資料差異， `HTTP` 從瀏覽器發出的呼叫。

### 批資料整合步驟

1. 用戶訪問客戶站點。
1. Audience Manager和第三方資料提供程式為訪問者分配一個唯一ID（通常使用cookie）。
1. Audience Manager調用第三方資料提供程式以匹配訪問者ID。
1. 計畫請求（通常在每日間隔內）在Audience Manager與第三方資料提供商之間交換訪問者段資料。

![](assets/s2s_70.png)

有關描述Audience Manager處理入站和出站時的時間幀的資訊 [!DNL Server-to-Server] ([!UICONTROL S2S])檔案傳輸，請參見 [報告和檔案傳輸時間框架准則](../reference/reporting-file-transfer-timeframe.md)。
