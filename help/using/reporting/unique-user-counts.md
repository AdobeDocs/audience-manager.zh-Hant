---
description: 說明相同特徵和時段之報表之間的不重複使用者總數差異。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 計算重疊和一般報表中的不重複使用者數
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# 計算重疊和一般報表中的不重複使用者數{#counting-unique-users-in-overlap-and-general-reports}

此頁面說明相同特徵和時段報表之間不重複使用者總計的差異。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：不重複使用者計數

重疊報表會將符合特徵資格的使用者計為不重複：

* 在報表的選取時間間隔內。
* 其存留時間[值為](../features/traits/segment-ttl-explained.md)，超過報告選取的時間間隔。
* 如果系統將這些識別碼視為作用中（亦即，這些識別碼符合任何其他特徵的資格，且已進行ID同步等）， 在過去60天內。

## 一般報表：不重複使用者計數

如果網站訪客在選取的時段符合特徵資格，「一般」報表會將其計為不重複訪客。

>[!MORELIKETHIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報表](../reporting/general-reports.md#general-reports-overview)
