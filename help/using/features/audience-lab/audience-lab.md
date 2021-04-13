---
description: 在區段測試群組中建立互斥的測試區段，以比較和評估不同目的地的效能。 您可以放棄控制群組，將區段分成整體的百分比，以測試效能。
seo-description: 在區段測試群組中建立互斥的測試區段，以比較和評估不同目的地的效能。 您可以放棄控制群組，將區段分成整體的百分比，以測試效能。
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

在[!UICONTROL Segment Test Groups]中建立互斥的測試區段，以比較和評估不同目標的效能。 您可以放棄控制群組，將區段分成整體的百分比，以測試效能。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用 [設定](../../features/profile-merge-rules/merge-rules-overview.md) 檔Link來推動跨裝置測試。這有助於確保使用者符合相同測試區段的資格，並在不同裝置上接受相同的處理。 測試群組中的測試區段將繼承已指派給其的基本區段的[描述檔合併規則](../../features/profile-merge-rules/merge-rules-dashboard.md)。

[!UICONTROL Audience Lab]預設檢視會針對每個測試群組顯示資訊卡。 按一下資訊卡以存取&#x200B;**[!UICONTROL Test Group]**&#x200B;檢視。 此檢視包含下列資訊：

* **[測試群組資訊](../../features/audience-lab/audience-lab-information-view.md)**
* **[測試群組報表](../../features/audience-lab/audience-lab-reporting-view.md)**

您可以建立&#x200B;**最多10個測試群組**，每個測試群組&#x200B;**最多15個測試區段**。

![](assets/test-groups-view.PNG)

## 搜尋和篩選測試群組{#search-and-filter}

當您開始建立包含多個測試區段的多個測試群組後，使用搜尋方塊尋找特定測試群組可能會比較容易。 您可以透過下列方式搜尋測試群組：

* 測試群組的名稱；
* 測試群組中任何測試區段的名稱；
* 測試群組的說明。

![](assets/search_and_filter_audience_lab.png)

您也可以依狀態篩選測試群組。 所有可用狀態都在下面的[Status](../../features/audience-lab/audience-lab.md#status)部分中說明。

## [!UICONTROL Status] {#status}

測試群組的狀態可以是作用中、已排程、暫停、草稿或完成。 下表中每項資訊的詳細資訊：

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 狀態 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 啟用 </span></b> </p> </td> 
   <td colname="col2"> <p><i>active</i>測試組表示資料當前正被發送到目標。 在<b><span class="uicontrol">測試群組</span></b>卡中按<b><span class="uicontrol">暫停測試</span></b>以暫停傳送資料至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已排程 </span></b> </p> </td> 
   <td colname="col2"> <p><i>scheduled</i>測試群組尚未啟用，但無法再編輯。 它將在您在<b>建立測試群組</b>精靈中選取的開始日期生效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已暫停 </span></b> </p> </td> 
   <td colname="col2"> <p><i>已暫停的</i>測試群組目前不會傳送資料至目的地。 在<b><span class="uicontrol">測試群組</span></b>卡中按<b><span class="uicontrol">啟用</span></b>以繼續傳送特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p><i>draft</i>測試群組尚未啟用，仍可加以編輯。 它尚未傳送資料至映射的目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 完成 </span></b> </p> </td> 
   <td colname="col2"> <p><i>已完成</i>測試群組已到達您在<b><span class="uicontrol">建立測試群組</span></b>精靈中選取的結束日期，並已停止傳送報告資料。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

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
   <td colname="col2"> <p>僅<b>適用於草稿測試群組。 </b>允許您繼續<b><span class="uicontrol">建立新測試組</span></b>嚮導。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暫停 </span></b> </p> </td>
   <td colname="col2"> <p>適用於作用中的測試群組。 可讓您暫停傳送測試區段至目標。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 啟用  </span></b> </p> </td>
   <td colname="col2"> <p>可用於暫停的測試群組。 可讓您繼續傳送測試區段至目標。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檢視 </span></b> </p> </td>
   <td colname="col2"> <p>可用於完成的測試組。 可讓您檢視測試產生的報表資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 複製 </span></b> </p> </td>
   <td colname="col2"> <p>允許您使用與正在複製的測試組相同的配置建立新的測試組。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 刪除 </span></b> </p> </td>
   <td colname="col2"> <p>可讓您刪除測試群組。 測試區段將從目標取消對應，與測試群組相關聯的基準區段和轉換特徵可完全編輯。 當您刪除測試群組以儲存報表時，會出現警報提示您下載CSV檔案。 </p> </td>
  </tr>
 </tbody>
</table>
