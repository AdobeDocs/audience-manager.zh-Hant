---
description: 使用段生成器描述段、其組成部分和規則建立。
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: 段目的、組成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 3%

---

# 區段：用途、構成和規則 {#segments-purpose-composition-and-rules}

描述 [!UICONTROL segments]、其組成部分和規則建立 [!UICONTROL Segment Builder]。

## 目的 [!UICONTROL Segments]

A *`segment`* (或 *`audience`*)是一組共用公共屬性的用戶。 在Audience Manager中，建立 [!UICONTROL segments] 伺服器端規則。 這些規則允許您根據站點訪問者屬性(如：

* 行為;
* 人口（年齡、性別、收入等）;
* 可在用戶介面中定義的其他特性。

## [!UICONTROL Segment] 組合

Audience Manager [!UICONTROL segment] 是由單個或一組特徵組成的伺服器端規則。 特徵由稱為鍵值對的資料元素組成。 以及您在 [!UICONTROL segment] 級別，這些關鍵值對包含符合訪問者特徵和 [!UICONTROL segment] 成員身份。

## 關於 [!UICONTROL Adobe Analytics] [!UICONTROL Segment] 映射

當測繪Adobe Analytics [!UICONTROL segments] 或Experience Cloud組織的報表套件，Audience Manager自動建立新的、相應的只讀 [!UICONTROL segments] 和特徵。 不能編輯或更改這些儲存的儲存位置 [!UICONTROL segments] Audience Manager。 但是，您對映射的Adobe Analytics執行的任何更改 [!UICONTROL segments] 或報告套件反映在Audience Manager中。

>[!TIP]
>
>Audience Manager [!UICONTROL segments] 不同於 [!DNL Adobe Analytics] [!UICONTROL segments]。 閱讀 [瞭解分析和Audience Manager中的段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) 以深入描述差異。

## 建立基於規則的 [!UICONTROL Segments] 與 [!UICONTROL Segment Builder]

與傳統的像素不同， [!UICONTROL Segment Builder] 使您能夠建立複雜 [!UICONTROL segment] 要求。 像 [!UICONTROL traits]。 [!UICONTROL segments] 評估資料 [!DNL Boolean] 表達式([!DNL AND]。 [!DNL OR]。 [!DNL NOT])、比較運算子（大於、小於、等於等）和頻率/頻率標準。 這些功能可幫助建立重點關注的受眾 [!UICONTROL segments] 與您的業務需要相關。

## 福利

[!UICONTROL Segments] 改進標準基於像素的受眾建立/分段流程，因為它們使您能夠：

* 構建相關、有用 [!UICONTROL segments] 具有第一和第三方特徵。
* 使用布爾運算子、比較表達式和頻率/頻率標準建立複雜的分段規則。
* 發送 [!UICONTROL segment] 資料。
* 使用Audience Manager報告監視效能。

>[!MORELIKETHIS]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)

