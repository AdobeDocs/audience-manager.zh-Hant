---
description: 說明重疊報表更新程式所需的區段大小和建立時間需求。
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 重疊報表更新排程和最小區段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# 重疊報表：更新排程和最小區段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

說明重疊報表更新程式所需的特徵和區段大小以及建立時間需求。

## 更新排程和需求 {#update-schedule}

[!UICONTROL Overlap]報告在星期日每週更新。 報表預先處理作業將於星期六開始。 這會影響新區段或現有區段在星期一重疊報表中的顯示方式。 要包含在重疊報表中：

* 區段在過去14天內必須至少包含70,000位即時使用者。
* 特徵在過去14天內必須包含28,000個[不重複特徵實現](/help/using/features/traits/trait-and-segment-qualification-reference.md)。
* 區段必須建立於星期四UTC午夜12點（每週重疊報告更新程式開始前2個整天）之前。
* 您的公司必須是完整[!DNL Audience Manager]客戶。 請聯絡您的[!DNL Audience Manager]顧問或客戶服務以取得更多資訊。

## 區段大小和/或建立時間會影響報告 {#segment-size}

如果您在其中一個報表中看不到區段[!UICONTROL Overlap]，可能是因為該區段不符合這些最低需求。

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>區段大小太小</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期四UTC凌晨12點前建立區段，但其中即時使用者總數少於70,000人。 此區段在符合使用者臨界值要求之前，不會出現在<span class="wintitle">重疊報表</span>中。 另外請注意，區段必須符合星期四截止期間或之前的必要使用者計數。 如果不符合每週期限，此區段將會在即將執行的星期日資料執行後的一週內出現在<span class="wintitle">重疊報表</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段建立太晚</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立區段，其中總共包含超過70,000名即時使用者。 此區段不會出現在下星期的<span class="wintitle">重疊報表</span>中，因為它是在報表更新期間之前的2天內建立的。 不過，在下次每週更新後，該區段會顯示在<span class="wintitle">重疊報表</span>中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特徵至特徵重疊報表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [區段至特徵重疊報表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [區段至區段重疊報表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
