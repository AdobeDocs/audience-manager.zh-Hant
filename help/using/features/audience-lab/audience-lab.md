---
description: 在區段測試群組中建立互斥的測試區段，以比較和測量不同目的地的效能。 您可以放置控制組並將區段劃分為整體的百分比，以測試功效。
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

在[!UICONTROL Segment Test Groups]中建立互斥的測試區段，以比較和測量不同目的地的效能。 您可以放置控制組並將區段劃分為整體的百分比，以測試功效。

## 概述 {#audience-lab-overview}

[!UICONTROL Audience Lab]使用[設定檔連結](../../features/profile-merge-rules/merge-rules-overview.md)來支援跨裝置測試。 這有助於確保使用者符合相同的測試區段資格，並在各裝置間獲得相同的待遇。 測試群組中的測試區段將繼承基底區段已指派給它的[設定檔合併規則](../../features/profile-merge-rules/merge-rules-dashboard.md)。

[!UICONTROL Audience Lab]預設檢視會顯示每個測試群組的卡片。 按一下卡片以存取&#x200B;**[!UICONTROL Test Group]**&#x200B;檢視。 此檢視包含下列資訊：

* **[測試群組資訊](../../features/audience-lab/audience-lab-information-view.md)**
* **[測試群組報表](../../features/audience-lab/audience-lab-reporting-view.md)**

您最多可建立&#x200B;**10個測試群組**，每個群組都有&#x200B;**最多15個測試區段**。

![](assets/test-groups-view.PNG)

## 搜尋和篩選測試群組 {#search-and-filter}

開始建立具有多個測試區段的多個測試群組後，使用搜尋方塊來尋找特定測試群組可能會更容易。 搜尋測試群組的方法有：

* 測試群組的名稱；
* 測試群組中任何測試區段的名稱；
* 測試群組的說明。

![](assets/search_and_filter_audience_lab.png)

您也可以依狀態篩選測試群組。 所有可用狀態在下方的[狀態](../../features/audience-lab/audience-lab.md#status)一節中說明。

## [!UICONTROL Status] {#status}

測試群組的狀態可以是「作用中」、「已排程」、「已暫停」、「草稿」或「已完成」。 有關各個專案的詳細資訊，請參閱下表：

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 狀態 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">使用中</span></b> </p> </td> 
   <td colname="col2"> <p><i>使用中</i>測試群組表示資料目前正在傳送至目的地。 在<b><span class="uicontrol">測試群組</span></b>卡片中按<b><span class="uicontrol">暫停測試</span></b>以暫停傳送資料至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">已排程</span></b> </p> </td> 
   <td colname="col2"> <p><i>已排程</i>測試群組尚未啟用，但無法再編輯。 它會從您在<b>建立測試群組</b>精靈中選取的開始日期開始啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">已暫停</span></b> </p> </td> 
   <td colname="col2"> <p><i>已暫停</i>測試群組目前未傳送資料至目的地。 按<b><span class="uicontrol">使</span></b>測試群組<b><span class="uicontrol">卡片中的</span></b>生效，以繼續傳送特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">草稿</span></b> </p> </td> 
   <td colname="col2"> <p><i>草稿</i>測試群組尚未啟用，仍可編輯。 尚未將資料傳送至對應的目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">已完成</span></b> </p> </td> 
   <td colname="col2"> <p><i>已完成</i>的測試群組已達到您在<b><span class="uicontrol">建立測試群組</span></b>精靈中選取的結束日期，並已停止傳送報告資料。 </p> </td>
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
   <td colname="col1"> <p> <b><span class="uicontrol">編輯</span></b> </p> </td>
   <td colname="col2"> <p><b>僅</b>可供草稿測試群組使用。 可讓您繼續<b><span class="uicontrol">建立新測試群組</span></b>精靈。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">暫停</span></b> </p> </td>
   <td colname="col2"> <p>適用於使用中測試群組。 可讓您暫停傳送測試區段至目的地。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">設定為使用中</span></b> </p> </td>
   <td colname="col2"> <p>可用於暫停的測試群組。 可讓您繼續傳送測試區段至目的地。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">檢視</span></b> </p> </td>
   <td colname="col2"> <p>可用於已完成的測試群組。 可讓您檢視測試產生的報告資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">重複</span></b> </p> </td>
   <td colname="col2"> <p>可讓您使用與正在複製的相同組態，建立新的測試群組。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">刪除</span></b> </p> </td>
   <td colname="col2"> <p>可讓您刪除測試群組。 測試區段將會從目的地取消對應，而和測試群組相關聯的基準區段和轉換特徵將可完全編輯。 當您刪除測試群組以儲存報告時，系統會提示您下載CSV檔案（如果您想要的話）。 </p> </td>
  </tr>
 </tbody>
</table>
