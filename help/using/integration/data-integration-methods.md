---
description: 概述Audience Manager如何與其他資料供應商和系統交換資訊。
seo-description: 概述Audience Manager如何與其他資料供應商和系統交換資訊。
seo-title: 資料整合方法
solution: Audience Manager
title: 資料整合方法
uuid: 17a4179a-e99 b-49eb-8f45-f2946 afbd27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 資料整合方法 {#data-integration-methods}

概述Audience Manager如何與其他資料供應商和系統交換資訊。

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

選擇正確的整合方法取決於資料合作夥伴的商業需求和技術能力的組合。Audience Manager透過下列其中一種方式，將訪客資訊交換給其他資料供應商：

* **即時：** 當使用者瀏覽您的網站時立即傳輸資料。This method is also known as a *`synchronous`* integration.
* **批次(伺服器至伺服器)：** 在訪客離開頁面後，以固定排程在伺服器之間傳輸資料。This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. 分類法將包含邏輯階層中組織的所有特性。

## Integration Use Cases {#integration-use-cases}

Audience Manager資料整合方法的使用案例摘要，以及每個方法的優缺點。

### 即時伺服器對伺服器整合

<!-- c_int_types_use_cases.xml -->

即時伺服器對伺服器資料整合可快速同步Audience Manager伺服器與其他定位系統之間的使用者資料。通常，資料交換會在數秒或數分鐘內完成，取決於定位系統的重新整理速率。不過，請注意，目標系統會決定此重新整理間隔，而非Audience Manager。此外，重新整理率在不同系統之間可能不同。即時伺服器對伺服器整合是資料交換的偏好整合類型。當定位合作夥伴可支援時，Audience Manager會使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">可讓您符合區段的使用者資格，而不會再次在頁面上檢視它們、在視訊播放器中等。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 減少頁面的HTTP呼叫次數。呼叫較少有助於保留使用者體驗。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">有助於時間敏感定位，讓您快速對合格使用者採取行動。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">當移至DSP進行Offsite定位時很有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 當您需要在相同頁面上定位使用者，或根據符合該群體的使用者資格時，對站上定位較不有用。</td>
 </tr>
</table>

### 伺服器對伺服器批次整合

伺服器對伺服器批次整合整合資料組合，並以固定間隔傳送至其他系統，而非幾乎即時傳送。資料傳輸間隔從24小時開始。有些資料供應商僅支援此整合類型。不過，我們已看到從批次整合到即時整合方法的普遍趨勢。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>優勢: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">可讓您符合區段的使用者資格，而不會再次在頁面上檢視它們、在視訊播放器中等。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">適用於不區分時間的定位。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺點：</td>
  <td class="stentry"> 同步間隔可延遲對最新資料的鎖定。</td>
 </tr>
</table>

### 即時呼叫

當使用者瀏覽您的網站或在頁面上採取動作時，即時呼叫會立即與Audience Manager交換資料。透過此方法，定位系統可取得最新的區段資格資料，並可在內容或廣告傳送決策期間將該資訊納入考量。此外，此程序可與發佈商廣告伺服器搭配使用，其中我們將合格區段更新為第一方Cookie，並將其讀取為關鍵字值配對。Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>優勢: </p></td>
  <td> <p> 可讓您定位根據最新區段資格的下一頁、內容區域或廣告曝光。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺點： </p></td>
  <td> <p>從頁面新增對Audience Manager的呼叫。</p></td>
 </tr> 
</table>


### 像素同步至定位系統

像素同步化會將區段對應至頁面上的像素。當使用者符合特定區段的資格時，像素就會觸發並傳送資料。像素同步化是不可靠且不可靠的資料傳輸機制。頂級資料供應商和系統很少使用它。

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">資料傳輸不可靠。5%到20%的損失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

說明透過同步(即時)或非同步(伺服器對伺服器)方法傳送資料的技術和商業原因。

<!-- c_int_delivery_choices.xml -->

### 選取資料傳送類型

* **技術考量：** 資料傳遞取決於資料合作夥伴的技術能力。Audience Manager可從瀏覽器或透過離線、伺服器到伺服器的通訊程序，即時傳送/接收資料。
* **商業考量：** 選擇一種傳送方式或另一種傳送方式的商業理由取決於目的地合作夥伴的技術能力以及您要如何使用此資料。通常，同步資料傳輸會在您需要立即對使用者資料採取動作時有用。非同步資料傳輸在不需要立即採取動作時，以及您有時間建立更深層的使用者設定檔以供日後使用時，可能會很有用。

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

概述Audience Manager如何與第三方廠商執行同步資料交換。

### 即時資料傳輸

<!-- c_int_overview_sync.xml -->

即時資料傳輸會傳送並接收區段ID作為使用者瀏覽或在您的網站上採取動作。通常，同步資料傳輸會在使用者瀏覽您的庫存時立即符合資格，或立即分段。

### 即時資料整合步驟

即時資料整合程序運作如下：

1. 使用者瀏覽包含Audience Manager代碼的客戶網站。
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 第三方會將該使用者的區段資訊傳回至Audience Manager。
1. Audience Manager會擷取區段資訊，讓其可供定位。

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

概述Audience Manager如何與第三方廠商即時同步資料(即時)。

### 批次資料整合

<!-- c_int_overview_async.xml -->

批次(伺服器對伺服器)資料整合程序遵循即時資料傳輸程序中概述的大部分步驟。不過，使用者資訊會儲存到我們的伺服器，並以定期間隔與第三方資料供應商同步，而非立即傳回區段ID。在下列情況下，非同步資料傳輸程序很有用：

* 不需要立即傳輸資料。
* 收集資料以建立一大群區段使用者。
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### 批次資料整合步驟

1. 使用者瀏覽客戶網站。
1. Audience Manager和第三方資料提供者會指派訪客唯一ID(通常使用Cookie)。
1. Audience Manager會呼叫第三方資料提供者以符合訪客ID。
1. 排程的請求通常會在每日間隔內，交換Audience Manager與第三方資料供應商之間的訪客區段資料。

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
