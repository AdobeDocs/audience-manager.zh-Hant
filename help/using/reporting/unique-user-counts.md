---
description: 說明相同特徵和時段報表之間獨特使用者總計的變化。
seo-description: 說明Adobe Audience Manager相同特徵和時段報表之間獨特使用者總計的差異
seo-title: 在重疊和一般報表中計算獨特使用者AAM
solution: Audience Manager
title: 計算重疊和一般報表中的不重複使用者數
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: 報告參考
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# 計算重疊和一般報表中的不重複使用者數{#counting-unique-users-in-overlap-and-general-reports}

此頁面說明相同特徵和時段報表之間獨特使用者總數的變化。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：唯一使用者計數

重疊報表會將使用者計為符合特徵時的獨特使用者：

* 在報告的選定時間間隔內。
* 該值的[即時](../features/traits/segment-ttl-explained.md)值比報告的選定時間間隔長。
* 如果它們在我們的系統中被視為活動（即，符合任何其他特徵的資格，則具有ID同步等） 60天內完成。

## 一般報告：唯一使用者計數

如果網站訪客在選取的時段內符合特徵，「一般」報表會將其計算為獨特。

>[!MORELIKETHIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報表](../reporting/general-reports.md#general-reports-overview)

