---
description: 在段test組中建立相互排斥的Test段，以比較和衡量不同目標的有效性。 您可以留出一個控制組，將您的段分成整體的百分比，以便test效果。
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

建立互斥test段 [!UICONTROL Segment Test Groups] 比較和衡量不同目的地的效能。 您可以留出一個控制組，將您的段分成整體的百分比，以便test效果。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab] 使用 [配置檔案連結](../../features/profile-merge-rules/merge-rules-overview.md) 為跨設備測試供電。 這有助於確保用戶有資格獲得相同的test段，並在設備間獲得相同的處理。 test組中的test段將繼承 [配置檔案合併規則](../../features/profile-merge-rules/merge-rules-dashboard.md) 基本段已分配給它。

的 [!UICONTROL Audience Lab] 預設視圖顯示每個test組的卡。 按一下卡以訪問 **[!UICONTROL Test Group]** 的子菜單。 此視圖包括以下資訊：

* **[測試群組資訊](../../features/audience-lab/audience-lab-information-view.md)**
* **[測試群組報表](../../features/audience-lab/audience-lab-reporting-view.md)**

您可以建立 **最多10個test組**，每個 **最多15個test段**。

![](assets/test-groups-view.PNG)

## 搜索和篩選Test組 {#search-and-filter}

一旦開始建立具有多個test段的多個test組，使用搜索框查找特定test組可能會更容易。 您可以通過以下方式搜索test組：

* test組名稱；
* 您的test組中任何test段的名稱；
* test組的說明。

![](assets/search_and_filter_audience_lab.png)

您還可以按狀態篩選test組。 所有可用狀態均在 [狀態](../../features/audience-lab/audience-lab.md#status) 的下界。

## [!UICONTROL Status] {#status}

test組的狀態可以是活動、計畫、暫停、草稿或已完成。 下表中每項的詳細資訊：

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
   <td colname="col2"> <p>安 <i>活動</i> test組表示當前正在將資料發送到目標。 按 <b><span class="uicontrol"> 暫停Test </span></b> 的 <b><span class="uicontrol"> Test組 </span></b> 掛起向目標發送資料的卡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已排程 </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>計畫</i> test組尚未處於活動狀態，但無法再編輯。 它將在您在中選擇的開始日期處處於活動狀態 <b>建立Test組</b> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已暫停 </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>暫停</i> test組當前未將資料發送到目標。 按 <b><span class="uicontrol"> 激活 </span></b> 的 <b><span class="uicontrol"> Test組 </span></b> 繼續發送特徵卡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 草稿 </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>草案</i> test組尚未處於活動狀態，仍可編輯。 它尚未將資料發送到映射的目標。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 完成 </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>已完成</i> test組已到達您在 <b><span class="uicontrol"> 建立Test組 </span></b> 已停止發送報告資料。 </p> </td>
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
   <td colname="col2"> <p>可用 <b>僅</b> 的子菜單。 允許您恢復 <b><span class="uicontrol"> 新建Test組 </span></b> 的子菜單。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 暫停 </span></b> </p> </td>
   <td colname="col2"> <p>可用於活動test組。 允許您暫停將test段發送到目標。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 激活 </span></b> </p> </td>
   <td colname="col2"> <p>可用於暫停的test組。 允許您繼續將test段發送到目標。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檢視 </span></b> </p> </td>
   <td colname="col2"> <p>可用於已完成的test組。 允許您查看test生成的報告資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 複製 </span></b> </p> </td>
   <td colname="col2"> <p>允許您建立與正在複製的配置相同的新test組。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 刪除 </span></b> </p> </td>
   <td colname="col2"> <p>允許您刪除test組。 test段將從目標中取消映射，與test組關聯的基線段和轉換特徵是完全可編輯的。 當您刪除test組以保存報告時，如果您願意，會出現警報，提示您下載CSV檔案。 </p> </td>
  </tr>
 </tbody>
</table>
