---
description: 說明相同特徵和時段報表之間獨特使用者總計的變化。
seo-description: 說明Adobe Audience manager中相同特徵和時段報表之間獨特使用者總數的變化
seo-title: 計算AAM中重疊和一般報表中的獨特使用者
solution: Audience Manager
title: 計算重疊和一般報告中的獨特用戶
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 計算重疊和一般報告中的獨特用戶{#counting-unique-users-in-overlap-and-general-reports}

此頁面說明相同特徵和時段報表之間獨特使用者總數的變化。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：唯一使用者計數

重疊報表會將使用者計為符合特徵時的獨特使用者：

* 在報告的選定時間間隔內。
* 該值的 [存留時間值比報表的](../features/traits/segment-ttl-explained.md) 選定時間間隔長。
* 如果它們在我們的系統中被視為活動（即，符合任何其他特徵的資格，則具有ID同步等）60天內完成。

## 一般報告：唯一使用者計數

如果網站訪客在選取的時段內符合特徵，「一般」報表會將其計算為獨特。

>[!MORE_LIKE_THIS]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報告](../reporting/general-reports.md#general-reports-overview)

