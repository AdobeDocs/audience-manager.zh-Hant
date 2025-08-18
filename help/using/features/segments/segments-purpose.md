---
description: 說明區段、其組成部分，以及使用「區段產生器」建立規則。
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: 區段用途、構成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# 區段：用途、構成和規則 {#segments-purpose-composition-and-rules}

說明[!UICONTROL segments]、其組成部份以及使用[!UICONTROL Segment Builder]建立規則。

## [!UICONTROL Segments]的目的

*`segment`* （或&#x200B;*`audience`*）是共用相同屬性的一組使用者。 在Audience Manager中，您會使用伺服器端規則建立[!UICONTROL segments]。 這些規則可讓您根據網站訪客屬性來建立對象群組，例如：

* 行為；
* 人口統計（年齡、性別、收入等）；
* 您可在使用者介面中定義的其他特性。

## [!UICONTROL Segment]組合

Audience Manager [!UICONTROL segment]是伺服器端規則，包含個別特徵或特徵群組。 特徵是由稱為機碼值組的資料元素所組成。 這些機碼值組以及您在[!UICONTROL segment]層級設定的規則，都包含可讓訪客符合特徵和[!UICONTROL segment]成員資格的條件。

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment]對應的考量事項

將Adobe Analytics [!UICONTROL segments]或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立對應的新唯讀[!UICONTROL segments]和特徵。 您無法從Audience Manager編輯或變更這些[!UICONTROL segments]的儲存位置。 不過，您在對應的Adobe Analytics [!UICONTROL segments]或報表套裝上執行的任何變更都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager [!UICONTROL segments]與[!DNL Adobe Analytics] [!UICONTROL segments]不同。 閱讀[瞭解Analytics和Audience Manager中的區段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)以深入瞭解差異。

## 使用[!UICONTROL Segments]建立規則型[!UICONTROL Segment Builder]

[!UICONTROL Segment Builder]不像傳統畫素會因應簡單的yes/no條件而引發，它可讓您建立複雜的[!UICONTROL segment]需求。 類似[!UICONTROL traits]，[!UICONTROL segments]使用[!DNL Boolean]運算式([!DNL AND]、[!DNL OR]、[!DNL NOT])、比較運運算元（大於、小於、等於等）和時近/頻率條件來評估資料。 這些功能有助於建立與您的業務需求相關的重點對象[!UICONTROL segments]。

## 福利

[!UICONTROL Segments]可改善標準畫素式對象建立/細分程式，因為這些程式可讓您：

* 建置具有第一方和第三方特徵的相關且有用的[!UICONTROL segments]。
* 使用布林運運算元、比較運算式和時近/頻率條件，建立複雜複雜的分段規則。
* 傳送[!UICONTROL segment]資料給目的地合作夥伴。
* 使用Audience Manager報表監控效能。

>[!MORELIKETHIS]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)
