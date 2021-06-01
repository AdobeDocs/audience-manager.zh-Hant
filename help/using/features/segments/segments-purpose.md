---
description: 使用區段產生器說明區段、其組成部分以及規則建立。
seo-description: 使用區段產生器說明區段、其組成部分以及規則建立。
seo-title: 區段用途、組成和規則
solution: Audience Manager
title: 區段用途、組成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 區段
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 6%

---

# 區段：用途、構成和規則 {#segments-purpose-composition-and-rules}

使用[!UICONTROL Segment Builder]說明[!UICONTROL segments]、其組成部分和規則建立。

## [!UICONTROL Segments]的用途

*`segment`*（或&#x200B;*`audience`*）是一組共用共同屬性的使用者。 在Audience Manager中，使用伺服器端規則建立[!UICONTROL segments]。 這些規則可讓您根據網站訪客屬性來建立受眾群組，例如：

* 行為;
* 人口（年齡、性別、收入等）;
* 您可在使用者介面中定義的其他特性。

## [!UICONTROL Segment] 組合物

Audience Manager[!UICONTROL segment]是伺服器端規則，包含個別或特徵群組。 特徵是由稱為索引鍵值配對的資料元素所組成。 除了您在[!UICONTROL segment]層級設定的規則，這些索引鍵值配對包含可讓訪客符合特徵和[!UICONTROL segment]成員資格的條件。

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment]映射的注意事項

將Adobe Analytics [!UICONTROL segments]或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀[!UICONTROL segments]和特徵。 不能從Audience Manager編輯或更改這些[!UICONTROL segments]的儲存位置。 不過，您在對應的Adobe Analytics [!UICONTROL segments]或報表套裝上執行的任何變更都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager[!UICONTROL segments]與[!DNL Adobe Analytics] [!UICONTROL segments]不同。 如需差異的深入說明，請參閱[了解Analytics和Audience Manager中的區段](https://docs.adobe.com/content/help/zh-Hant/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)。

## 使用[!UICONTROL Segment Builder]建立規則型[!UICONTROL Segments]

與因簡單是/否條件而引發的傳統像素不同， [!UICONTROL Segment Builder]可讓您建立複雜的[!UICONTROL segment]要求。 與[!UICONTROL traits]一樣，[!UICONTROL segments]使用[!DNL Boolean]運算式([!DNL AND]、[!DNL OR]、[!DNL NOT])、比較運算子（大於、小於、等於等等）和時近/頻度標準來評估資料。 這些功能可協助您建立與業務需求相關的受眾[!UICONTROL segments]。

## 福利

[!UICONTROL Segments] 改善標準的像素受眾建立/細分程式，因為它們可讓您：

* 使用第一方和第三方特徵建立相關且實用的[!UICONTROL segments]。
* 使用布林運算子、比較運算式和造訪間隔/頻率條件，建立複雜的分段規則。
* 將[!UICONTROL segment]資料發送到目標合作夥伴。
* 使用Audience Manager報告監控效能。

>[!MORELIKETHIS]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)

