---
description: 描述「重疊」報告更新流程所需的段大小和建立時間要求。
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 重疊報表更新計畫和最小段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# 重疊報表：更新排程和最小區段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

描述Overlap報告更新流程所需的特性和段大小以及建立時間要求。

## 更新計畫和要求 {#update-schedule}

[!UICONTROL Overlap] 報告每週在星期日更新。 報表預處理從星期六開始。 這會影響星期一重疊報告中新段或現有段的顯示方式。 要包括在重疊報告中：

* 在過去14天內，一個網段必須包含至少70,000個即時用戶。
* 一個特徵必須包含28000 [獨特的特性實現](/help/using/features/traits/trait-and-segment-qualification-reference.md) 在過去的14天裡。
* 必須在UTC星期四上午12點（每週重疊報告更新過程開始前2個完整天）之前建立段。
* 您的公司必須是完整 [!DNL Audience Manager] 客戶。 請聯繫您 [!DNL Audience Manager] 咨詢顧問或客戶服務部門瞭解更多資訊。

## 段大小和/或建立時間影響報告 {#segment-size}

如果在其中一個 [!UICONTROL Overlap] 可能是由於分部不符合該等最低要求。

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>段大小太小</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期四UTC的上午12點之前建立一個段，但它包含的即時用戶總數少於70,000。 此段不會出現在 <span class="wintitle"> 重疊報表</span> 直到滿足用戶閾值要求。 另請注意，該段必須滿足星期四截止期間或之前所需的用戶計數。 如果它不滿足每週截止時間，則段將出現在 <span class="wintitle"> 重疊報表</span> 在下週日資料運行後的一週。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>建立的段太遲</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立了一個網段，該網段包含70,000多個即時用戶。 此段不會出現在 <span class="wintitle"> 重疊報表</span> 在報告更新期間之前不到2天建立。 但是，該段將出現在 <span class="wintitle"> 重疊報表</span> 下一週更新後。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特徵至特徵重疊報表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [區段至特徵重疊報表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [區段至區段重疊報表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

