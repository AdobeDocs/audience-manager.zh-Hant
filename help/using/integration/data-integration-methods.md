---
description: Audience Manager如何與其他資料提供者和系統交換資訊的整體概觀。
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: 資料整合方法
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# 資料整合方法 {#data-integration-methods}

Audience Manager如何與其他資料提供者和系統交換資訊的整體概觀。

## 支援的資料整合方法：即時和[!DNL Server-to-Server] {#supported-methods}

選擇正確的整合方法取決於業務需求與資料合作夥伴的技術能力的組合。 Audience Manager透過下列其中一種方法與其他資料提供者交換訪客資訊：

* **即時：**&#x200B;在使用者造訪您的網站時立即傳輸資料。 此方法也稱為&#x200B;*`synchronous`*&#x200B;整合。
* **批次([!DNL Server-to-Server])：**&#x200B;在訪客離開頁面後，依設定的排程在伺服器之間傳輸資料。 此方法也稱為&#x200B;*`out-of-band`*&#x200B;或&#x200B;*`asynchronous`*&#x200B;整合。

## 先決條件：建立特徵分類法 {#prereqs}

在整合程式開始之前，請記得在[ UI中](../features/traits/create-onboarded-rule-based-traits.md)建立特徵[和](../features/traits/trait-storage.md#create-trait-storage-folder)資料夾結構[!DNL Audience Manager]。 分類法會包含以邏輯階層組織的所有[!UICONTROL traits]。

## 整合的使用案例 {#integration-use-cases}

Audience Manager資料整合方法的使用案例摘要，以及每種方法的優缺點。

### 即時[!DNL Server-to-Server]整合

<!-- c_int_types_use_cases.xml -->

即時[!DNL server-to-server]資料整合可快速同步Audience Manager伺服器與其他目標定位系統之間的使用者資料。 在大多數情況下，視目標系統的重新整理頻率而定，資料交換會在數秒或數分鐘內進行。 但請注意，目標系統決定此重新整理間隔，而不是Audience Manager。 此外，不同系統的重新整理速率可能有所不同。 即時[!UICONTROL server-to-server]整合是資料交換的偏好整合型別。 只要目標合作夥伴可支援，Audience Manager就會使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>優點： </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">可讓您讓使用者符合區段的資格，而不需在頁面、視訊播放器等中再次看到這些區段。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 減少頁面的HTTP呼叫數。 減少呼叫次數有助於保留使用者體驗。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">協助進行有時效性的目標定位，以便您能夠對合格使用者快速採取行動。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">移至異地鎖定目標的DSP時相當實用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 當您需要根據使用者是否符合該區段的資格來在同一個頁面或下一頁鎖定使用者時，對現場鎖定目標沒有多大幫助。</td>
 </tr>
</table>

### [!DNL Server-to-Server]批次整合

[!DNL server-to-server]批次整合會組合資料，並以設定的間隔將其傳送至其他系統，而非近乎即時。 資料傳輸間隔從24小時開始。 有些資料提供者僅支援此整合型別。 不過，我們已看到從批次整合轉向即時整合方法的一般趨勢。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>優點： </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">可讓您讓使用者符合區段的資格，而不需在頁面、視訊播放器等中再次看到這些區段。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">適合用於不具時效性的目標定位。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 同步間隔可能會延遲針對最新資料進行目標定位。</td>
 </tr>
</table>

### 即時呼叫

當使用者造訪您的網站或在頁面上採取行動時，即時呼叫會立即與Audience Manager交換資料。 使用此方法，目標定位系統可獲得最新的區段資格資料，並可在內容或廣告傳送決策期間將該資訊列入考量。 此外，此程式也適用於發佈商廣告伺服器，我們會將合格的區段更新為第一方Cookie，並以索引鍵值配對的形式讀取廣告呼叫。 目前，Audience Manager使用即時呼叫來與[!DNL Adobe Target]和其他內容管理系統整合。

<table> 
 <tr>
  <td> <p>優點： </p></td>
  <td> <p> 可讓您根據最近的區段資格來鎖定下一個頁面、內容區域或廣告印象。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺點： </p></td>
  <td> <p>從頁面新增呼叫Audience Manager。</p></td>
 </tr> 
</table>


### 目標系統的畫素同步

畫素同步會將區段對應至頁面上的畫素。 當使用者符合特定區段的資格時，畫素會觸發並傳輸資料。 畫素同步是一種基本且不可靠的資料傳輸機制。 頂層資料提供者和系統很少使用它。

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>優點： </p></td>
  <td class="stentry"> <p> 即時資料傳輸。 </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>缺點： </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">可以從頁面新增許多使用者端呼叫。 </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">資料傳輸不可靠。 5%到20%的損失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## 如何選擇資料傳送方法 {#data-delivery-choices}

說明透過同步（即時）或非同步（伺服器對伺服器）方法傳送資料的技術和業務原因。

<!-- c_int_delivery_choices.xml -->

### 選取資料傳送型別

* **技術考量：**&#x200B;資料傳遞取決於資料合作夥伴的技術能力。 Audience Manager可從瀏覽器即時傳送/接收資料，或透過離線伺服器對伺服器通訊程式進行批次更新。
* **業務考量：**&#x200B;選擇一種或另一種傳遞方法的業務理由取決於目的地合作夥伴的技術能力，以及您想要如何使用此資料。 通常，當您需要立即對使用者資料採取行動時，同步資料傳輸會很有用。 當不需要立即採取行動且您有時間建置更深入的使用者設定檔以供日後使用時，非同步資料傳輸可能會很有用。

## 即時資料傳輸程式 {#real-time-data-transfer-process}

概述Audience Manager如何與協力廠商執行同步資料交換。

### 即時資料傳輸

<!-- c_int_overview_sync.xml -->

即時資料傳輸會在使用者造訪您的網站或在您的網站上採取動作時，傳送及接收區段ID。 通常，當您需要立即讓使用者在瀏覽您的詳細目錄時符合資格或劃分使用者時，同步資料傳輸會很有用。

### 即時資料整合步驟

即時資料整合程式的運作方式如下：

1. 使用者造訪包含Audience Manager程式碼的客戶網站。
1. Audience Manager載入Iframe並呼叫[!UICONTROL Data Collection Server] ([!DNL DCS])。
1. [!DNL DCS]會呼叫協力廠商伺服器（即時）以檢查廠商是否有任何關於使用者的區段資訊。
1. 協力廠商會將該使用者的相關區段資訊傳回給Audience Manager。
1. Audience Manager會擷取區段資訊，並將其用於鎖定目標。

![](assets/rt_reduce70.png)

## 批次資料傳輸流程 {#batch-data-transfer-process}

概述Audience Manager如何與第三方廠商同步（即時）交換資料。

### 批次資料整合

<!-- c_int_overview_async.xml -->

批次([!DNL server-to-server])資料整合程式遵循即時資料傳輸程式中所概述的大多數步驟。 不過，使用者資訊不會立即傳回區段ID，而是會儲存至我們的伺服器，並定期與第三方資料提供者同步。 非同步資料傳輸程式在下列情況下相當實用：

* 不需要立即傳輸資料。
* 收集資料以建立大型分段使用者集區。
* 您想要減少資料差異和瀏覽器的`HTTP`呼叫。

### 批次資料整合步驟

1. 使用者造訪客戶網站。
1. Audience Manager和第三方資料提供者會為訪客指派唯一ID （通常使用Cookie）。
1. Audience Manager會呼叫第三方資料提供者來比對訪客ID。
1. 排程請求（通常為每日間隔）會在Audience Manager和您的第三方資料提供者之間交換訪客區段資料。

![](assets/s2s_70.png)

如需描述Audience Manager處理傳入和傳出[!DNL Server-to-Server] ([!UICONTROL S2S])檔案傳輸時段的資訊，請參閱[報告和檔案傳輸時間範圍准則](../reference/reporting-file-transfer-timeframe.md)。
