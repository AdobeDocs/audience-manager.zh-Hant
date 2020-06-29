---
description: 說明區段、其組成部分，以及使用區段產生器建立規則。
seo-description: 說明區段、其組成部分，以及使用區段產生器建立規則。
seo-title: 區段用途、組成和規則
solution: Audience Manager
title: 區段用途、組成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# 區段：用途、構成和規則 {#segments-purpose-composition-and-rules}

說明 [!UICONTROL segments]其組成部分，以及使用建立規則 [!UICONTROL Segment Builder]。

## 目的 [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. 在Audience Manager中，您使用 [!UICONTROL segments] 伺服器端規則建立。 這些規則可讓您根據網站訪客屬性(例如：

* 行為;
* 人口（年齡、性別、收入等）;
* 您可以在使用者介面中定義的其他特性。

## [!UICONTROL Segment] 構圖

Audience Manager是 [!UICONTROL segment] 伺服器端規則，由個別或特徵群組組成。 特徵由稱為鍵值對的資料元素組成。 除了您在層級設定的規 [!UICONTROL segment] 則，這些關鍵值配對還包含符合訪客特徵和成員資格的 [!UICONTROL segment] 准則。

## 對映的考 [!UICONTROL Adobe Analytics][!UICONTROL Segment] 慮

當將Adobe Analytics或報 [!UICONTROL segments] 表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀 [!UICONTROL segments] 和特徵。 您無法從Audience Manager編輯或變更這些 [!UICONTROL segments] 儲存位置。 不過，您在對應的Adobe Analytics或報表套裝上執行的任何變 [!UICONTROL segments] 更都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager與 [!UICONTROL segments] Audience Manager不同 [!DNL Adobe Analytics] 於 [!UICONTROL segments]。 Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/zh-Hant/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## 使用 [!UICONTROL Segments] [!UICONTROL Segment Builder]

與傳統的像素不同，它們會因簡單的是／否條件而觸發， [!UICONTROL Segment Builder] 讓您建立複雜的 [!UICONTROL segment] 需求。 例如， [!UICONTROL traits]使用運 [!UICONTROL segments] 算式( [!DNL Boolean] 、[!DNL AND]、 [!DNL OR][!DNL NOT])、比較運算子（大於、小於、等於等於等）和時近／頻率准則來評估資料。 這些功能可協助建立與您的 [!UICONTROL segments] 業務需求相關的受眾。

## 福利

[!UICONTROL Segments] 改善標準的像素受眾建立／細分流程，因為它們可讓您：

* 運用第一方和第 [!UICONTROL segments] 三方特性建立相關且實用的功能。
* 使用布林運算子、比較運算式和時近／頻率准則建立複雜而複雜的分段規則。
* 傳送 [!UICONTROL segment] 資料給目標合作夥伴。
* 使用Audience Manager報表監控效能。

>[!MORELIKETHIS]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)

