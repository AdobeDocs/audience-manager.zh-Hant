---
description: 說明「重疊」報表更新程序所需的區段大小和建立時間需求。
seo-description: 說明「重疊」報表更新程序所需的區段大小和建立時間需求。
seo-title: 重疊報表更新排程和最小區段大小
solution: Audience Manager
title: 重疊報表更新排程和最小區段大小
uuid: 35c1cb39-e28 d-4d20-88c9-5ff4 Fe154 e9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

說明「重疊」報表更新程序所需的區段大小和建立時間需求。

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] 報表會每周更新。報告前處理將於星期六開始。這會影響新區段或現有區段在星期一重疊報表中的顯示方式。要包含在重疊報表中：

* 在過去14天內，區段最少必須包含70,000名即時使用者。Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* 區段必須在星期四上午12到週四UTC(每周重疊報表更新程序開始前的天)建立。
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>區段大小過小</b> </p> </td> 
   <td colname="col2"> <p>假設您在週四12月12日之前建立了區段，但它包含的即時使用者人數少於70,000位。This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. 請注意，此外，區段必須符合週四結束期間或之前的使用者計數。If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段已建立太遲</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立細分，其中包含超過70,000名即時使用者。This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [特徵至特徵重疊報表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [區段至特徵重疊報表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [區段至區段重疊報表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

