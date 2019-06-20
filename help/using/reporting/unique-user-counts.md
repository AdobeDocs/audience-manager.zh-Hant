---
description: 說明報告在相同特徵和時段內不同使用者總數的變化。
seo-description: 說明在Adobe Audience Manager中，同一特性和時段內報告之間獨特使用者總數的變化
seo-title: 在AAM中的重疊和一般報表中計算獨特使用者
solution: Audience Manager
title: 計算重疊和一般報表中的獨特使用者
uuid: 450f6a8c-f363-43de-b2 d8-0a156 f14 eae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

此頁面說明報告在相同特徵和時段內的獨特使用者總數變化。

<!-- 

c_unique_user_counts.xml

 -->

## 重疊報表：獨特使用者計數

重疊報告在使用者符合特徵資格時會將其計數為獨特：

* 在選取的報表時間間隔內。
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* 如果他們在我們的系統中被視為活動中(即符合其他特徵的資格、具有ID同步等)。

## 一般報表：獨特使用者計數

一般報告會將網站訪客在選定時段內符合特徵的資格計算為獨特訪客。

>[!MORE_贊_ this]
>
>* [互動式報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [一般報表](../reporting/general-reports.md#general-reports-overview)

