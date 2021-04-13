---
description: 說明「重疊」報表更新程式所需的區段大小和建立時間需求。
seo-description: 說明「重疊」報表更新程式所需的區段大小和建立時間需求。
seo-title: 重疊報表更新排程和最小區段大小
solution: Audience Manager
title: 重疊報表更新排程和最小區段大小
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: 重疊報表
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# 重疊報表：更新排程和最小區段大小{#overlap-reports-update-schedule-and-minimum-segment-size}

說明「重疊」報表更新程式所需的特徵和區段大小以及建立時間需求。

## 更新計畫和要求{#update-schedule}

[!UICONTROL Overlap] 報告每週在週日更新。報表預處理從星期六開始。 這會影響週一重疊報表中新區段或現有區段的顯示方式。 要包含在重疊報表中：

* 區段在過去14天內至少必須包含70,000名即時使用者。
* 在過去14天內，特徵必須包含28,000個[獨特特徵實現](/help/using/features/traits/trait-and-segment-qualification-reference.md)。
* 區段必須在UTC的週四上午12點之前建立（每週重疊報告更新程式開始前2個完整天）。
* 您的公司必須是[!DNL Audience Manager]完整客戶。 請連絡您的[!DNL Audience Manager]顧問或客戶服務以瞭解更多資訊。

## 區段大小和／或建立時間影響報告{#segment-size}

如果您在其中一個[!UICONTROL Overlap]報表中未看到區段，可能是因為區段不符合這些最低要求。

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
   <td colname="col2"> <p>假設您在UTC的週四上午12點之前建立區段，但其中的即時使用者總數少於70,000名。 除非符合使用者臨界值要求，否則此區段不會出現在<span class="wintitle">重疊報表</span>中。 此外，此區段必須符合星期四截止期間的使用者計數要求或之前。 如果不符合每週期限，則區段會顯示在下個星期日資料執行後一週的「重疊報表」中。<span class="wintitle"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>建立的區段太遲</b> </p> </td> 
   <td colname="col2"> <p>假設您在星期五建立區段，其中包含超過70,000名即時使用者。 此區段不會在下週的「重疊報表」中顯示，因為此區段是在報表更新時段前2天內建立的。 <span class="wintitle"></span>但是，在下次每週更新後，區段會出現在<span class="wintitle">重疊報表</span>中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [特徵至特徵重疊報表](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [區段至特徵重疊報表](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [區段至區段重疊報表](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

