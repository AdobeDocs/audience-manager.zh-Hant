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

說明[!UICONTROL segments]、其組成部分，以及使用[!UICONTROL Segment Builder]建立規則。

## [!UICONTROL Segments]的用途

*`segment`*（或&#x200B;*`audience`*）是一組共用公共屬性的用戶。 在Audience Manager中，您使用伺服器端規則建立[!UICONTROL segments]。 這些規則可讓您根據網站訪客屬性(例如：

* 行為;
* 人口（年齡、性別、收入等）;
* 您可以在使用者介面中定義的其他特性。

## [!UICONTROL Segment] 構圖

Audience Manager [!UICONTROL segment]是伺服器端規則，由個別或特徵群組組成。 特徵由稱為鍵值對的資料元素組成。 除了您在[!UICONTROL segment]層級設定的規則外，這些索引鍵值配對還包含符合訪客特徵和[!UICONTROL segment]成員資格的條件。

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment]映射的注意事項

將Adobe Analytics [!UICONTROL segments]或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀[!UICONTROL segments]和特徵。 您無法從Audience Manager編輯或變更這些[!UICONTROL segments]的儲存位置。 不過，您在對應的Adobe Analytics [!UICONTROL segments]或報表套裝上執行的任何變更都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager [!UICONTROL segments]與[!DNL Adobe Analytics] [!UICONTROL segments]不同。 請閱讀[瞭解Analytics和Audience Manager中的區段](https://docs.adobe.com/content/help/zh-Hant/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)，以深入瞭解差異。

## 使用[!UICONTROL Segment Builder]建立以規則為基礎的[!UICONTROL Segments]

與響應簡單是／否條件而觸發的傳統像素不同，[!UICONTROL Segment Builder]可讓您建立複雜的[!UICONTROL segment]要求。 與[!UICONTROL traits]一樣，[!UICONTROL segments]使用[!DNL Boolean]運算式([!DNL AND]、[!DNL OR]、[!DNL NOT])、比較運算子（大於、小於、等於等於等）以及時近／頻率准則來評估資料。 這些功能可協助您建立與業務需求相關的受眾[!UICONTROL segments]。

## 福利

[!UICONTROL Segments] 改善標準的像素受眾建立／細分流程，因為它們可讓您：

* 建立具有第一方和第三方特徵的相關實用[!UICONTROL segments]。
* 使用布林運算子、比較運算式和時近／頻率准則建立複雜而複雜的分段規則。
* 傳送[!UICONTROL segment]資料給目標合作夥伴。
* 使用Audience Manager報表監控效能。

>[!MORELIKETHIS]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)

