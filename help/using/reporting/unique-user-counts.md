---
description: 說明相同特徵和時段之報表之間的不重複使用者總數差異。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 計算重疊和一般報表中的不重複使用者數
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
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
* 在過去60天內，如果系統將這些識別碼視為作用中（亦即符合任何其他特徵的資格、具有ID同步等）。

## 一般報表：不重複使用者計數

如果網站訪客在選取的時段符合特徵資格，「一般」報表會將其計為不重複訪客。

>[!MORELIKETHIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報表](../reporting/general-reports.md#general-reports-overview)
