---
description: 說明相同特徵和時段內，報表之間不重複使用者總計的變化。
seo-description: 說明Adobe Audience Manager中相同特徵和時段報表之間不重複使用者總計的變化
seo-title: 計算AAM中重疊和一般報表中的不重複使用者數
solution: Audience Manager
title: 計算重疊和一般報表中的不重複使用者數
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: 報表參考
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# 計算重疊和一般報表中的不重複使用者數{#counting-unique-users-in-overlap-and-general-reports}

本頁面說明相同特徵和時段內，不重複使用者總計在報表之間的變化。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：不重複使用者計數

當使用者符合特徵資格時，重疊報表會將使用者計為獨特：

* 在報表的所選時間間隔內。
* 其[存留時間](../features/traits/segment-ttl-explained.md)值比報表的所選時間間隔長。
* 如果系統中他們被視為作用中（亦即，符合任何其他特徵的資格、有ID同步等） 過去60天。

## 一般報告：不重複使用者計數

如果網站訪客在選取的時段內符合特徵資格，則「一般」報表會將其計為獨特。

>[!MORELIKETHIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
* [一般報表](../reporting/general-reports.md#general-reports-overview)

