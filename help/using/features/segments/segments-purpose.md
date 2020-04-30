---
description: 說明區段、其組成部分，以及使用區段產生器建立規則。
seo-description: 說明區段、其組成部分，以及使用區段產生器建立規則。
seo-title: 區段用途、組成和規則
solution: Audience Manager
title: 區段用途、組成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 區段： 目的、構成和規則 {#segments-purpose-composition-and-rules}

說明區段、其組成部分，以及使用建立規則 [!UICONTROL Segment Builder]。

## 區段用途

A *`segment`* (或 *`audience`*)是一組共用共同屬性的使用者。 在Audience Manager中，您可以使用伺服器端規則建立區段。 這些規則可讓您根據網站訪客屬性(例如：

* 行為;
* 人口（年齡、性別、收入等）;
* 您可以在使用者介面中定義的其他特性。

## 區段構成

Audience Manager區段是伺服器端規則，由個別或特徵群組組成。 特徵由稱為鍵值對的資料元素組成。 除了您在區段層級設定的規則，這些關鍵值配對還包含符合訪客特徵和區段成員資格的條件。

## Adobe Analytics區段對應的考量

將Adobe Analytics區段或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀區段和特徵。 您無法從Audience Manager編輯或變更這些區段的儲存位置。 不過，您對對應的Adobe Analytics區段或報表套裝執行的任何變更都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager區段與區段不 [!DNL Adobe Analytics] 同。 閱 [讀瞭解Analytics和Audience Manager中的區段](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) ，以深入瞭解差異。

## 使用區段產生器建立以規則為基礎的區段

與因簡單是／否條件而引發的傳統像素不同，「區段產生器」可讓您建立複雜的區段需求。 和特徵一樣，區段會使 [!DNL Boolean] 用運算式([!DNL AND]、 [!DNL OR]、 [!DNL NOT])、比較運算子（大於、小於、等於等於等）和時近／頻率准則來評估資料。 這些功能可協助您建立與業務需求相關的受眾細分。

## 福利

區段可改善標準的像素受眾建立／區隔程式，因為它們可讓您：

* 建立具有第一方和第三方特徵的相關、有用區段。
* 使用布林運算子、比較運算式和時近／頻率准則建立複雜而複雜的分段規則。
* 傳送區段資料給目標合作夥伴。
* 使用Audience Manager報表監控效能。

>[!MORELIKETHIS]
>
>* [信號、特徵和區段](../../reference/signal-trait-segment.md)

