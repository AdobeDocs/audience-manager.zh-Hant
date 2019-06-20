---
description: 在區段測試群組中建立互斥測試區段，以比較並測量不同目的地的效能。您可以設定控制群組，將區段分為整體百分比，以測試功效。
seo-description: 在區段測試群組中建立互斥測試區段，以比較並測量不同目的地的效能。您可以設定控制群組，將區段分為整體百分比，以測試功效。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8 f-2629085d78 e9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. 您可以設定控制群組，將區段分為整體百分比，以測試功效。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用 [描述檔連結](../../features/profile-merge-rules/merge-rules-overview.md) 來支援跨裝置測試。如此可確保使用者符合相同測試區段的資格，並在不同裝置上接收相同的處理方式。The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

[!UICONTROL Audience Lab] 預設檢視會顯示每個測試群組的資訊卡。Click a card to access the **[!UICONTROL Test Group]** view. 此檢視包含下列資訊：

* **[測試群組資訊](../../features/audience-lab/audience-lab-information-view.md)**
* **[測試群組報表](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

在您開始使用多個測試區段建立多個測試群組後，使用搜尋方塊來尋找特定測試群組可能比較容易。您可以依下列方式搜尋測試群組：

* 測試群組的名稱；
* 測試群組中任何測試區段的名稱；
* 測試群組的說明。

![](assets/search_and_filter_audience_lab.png)

您也可以依狀態篩選測試群組。All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## 狀態 {#status}

測試群組的狀態可以是活動中、已排程、暫停、草稿或完成。下列表格中的詳細資訊：

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 狀態 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 活動中 </span></b> </p> </td> 
   <td colname="col2"> <p><i>作用</i> 中的測試群組表示資料目前會傳送至目的地。Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已排程 </span></b> </p> </td> 
   <td colname="col2"> <p><i>排程</i> 的測試群組尚未啓用，但無法再編輯。It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已暫停 </span></b> </p> </td> 
   <td colname="col2"> <p><i>暫停</i> 的測試群組目前不會傳送資料至目的地。Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p><i>草稿</i> 測試群組尚未作用中，仍可編輯。尚未傳送資料至映射的目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Completed </span></b> </p> </td> 
   <td colname="col2"> <p><i>完成</i> 的測試群組已達您在 <b><span class="uicontrol"> 「建立測試群組 </span></b> 」精靈中選取的結束日期，已停止傳送報告資料。 </p> </td>
  </tr>
 </tbody>
</table>

## 動作 {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 動作 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 編輯 </span></b> </p> </td>
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暫停 </span></b> </p> </td>
   <td colname="col2"> <p>適用於作用中測試群組。允許您暫停將測試區段傳送至目的地。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 啓用活動 </span></b> </p> </td>
   <td colname="col2"> <p>適用於暫停的測試群組。可讓您繼續將測試區段傳送至目的地。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檢視 </span></b> </p> </td>
   <td colname="col2"> <p>適用於完成測試群組。可讓您檢視測試產生的報表資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 複製 </span></b> </p> </td>
   <td colname="col2"> <p>可讓您建立新的測試群組，與您複製的設定相同。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 刪除 </span></b> </p> </td>
   <td colname="col2"> <p>可讓您刪除測試群組。測試區段將會從目的地未對應，且與測試群組關聯的基準區段和轉換特徵可完全編輯。當您刪除測試群組時，警報會提示您下載CSV檔案，以儲存報告。 </p> </td>
  </tr>
 </tbody>
</table>