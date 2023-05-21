---
description: 描述相同特性和時間段的報表之間唯一用戶合計的變化。
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: 計算重疊和一般報表中的不重複使用者數
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 12%

---

# 計算重疊和一般報表中的不重複使用者數{#counting-unique-users-in-overlap-and-general-reports}

此頁描述相同特性和時間段的報表之間唯一用戶合計的變化。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：唯一用戶計數

重疊報告將用戶在符合以下特徵時視為唯一：

* 在報告的選定時間間隔內。
* 有 [生存時間](../features/traits/segment-ttl-explained.md) 值長於報告的選定時間間隔。
* 如果它們在我們的系統中被視為活動（即，符合任何其他特性，具有ID同步等） 60天內。

## 一般報告：唯一用戶計數

如果站點訪問者在選定時間段內符合特性，則「一般」報告會將其計算為唯一。

>[!MORELIKETHIS]
>
>* [互動式報告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報表](../reporting/general-reports.md#general-reports-overview)

