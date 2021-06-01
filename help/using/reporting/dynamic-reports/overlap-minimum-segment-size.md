---
description: 說明「重疊」報表更新程式所需的區段大小和建立時間需求。
seo-description: 說明「重疊」報表更新程式所需的區段大小和建立時間需求。
seo-title: 重疊報表更新排程和最小區段大小
solution: Audience Manager
title: 重疊報表更新排程和最小區段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: 重疊報表
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# 重疊報表：更新排程和最小區段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

說明「重疊」報表更新程式所需的特徵和區段大小及建立時間需求。

## 更新計畫和要求{#update-schedule}

[!UICONTROL Overlap] 報告每週在星期日更新。報表預先處理從星期六開始。 這會影響星期一重疊報表中新區段或現有區段的顯示方式。 要納入重疊報表：

* 區段在過去14天內，至少必須包含70,000個即時使用者。
* 特徵在過去14天內必須包含28,000個[不重複特徵實現](/help/using/features/traits/trait-and-segment-qualification-reference.md)。
* 區段必須在UTC的星期四上午12點前建立（每週重疊報表更新程式開始前2天）。
* 您的公司必須是完整[!DNL Audience Manager]客戶。 請連絡您的[!DNL Audience Manager]顧問或客戶服務以了解更多資訊。

## 區段大小和/或建立時間會影響報表{#segment-size}

若您在其中一個[!UICONTROL Overlap]報表中未看見區段，可能是因為區段不符合這些最低需求。

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
   <td colname="col2"> <p>假設您在星期四UTC的上午12點前建立區段，但其包含的即時使用者總數少於70,000名。 在符合使用者臨界值要求之前，此區段不會出現在<span class="wintitle">重疊報表</span>中。 另請注意，區段必須符合星期四截止期間之前或之前的必要使用者計數。 如果不符合每週期限，則在即將到來的星期日資料執行後的一週，區段會顯示在<span class="wintitle">重疊報表</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段建立太遲</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立區段，其中包含70,000個以上的即時使用者。 下週的<span class="wintitle">重疊報表</span>中不會顯示此區段，因為它是在報表更新期間前不到2天建立的。 不過，下次每週更新後，區段會顯示在<span class="wintitle">重疊報表</span>中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特徵至特徵重疊報表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
* [區段至特徵重疊報表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
* [區段至區段重疊報表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

