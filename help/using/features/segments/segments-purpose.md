---
description: 說明區段、其組成部分以及使用區段產生器建立規則。
seo-description: 說明區段、其組成部分以及使用區段產生器建立規則。
seo-title: 區段用途、構圖和規則
solution: Audience Manager
title: 區段用途、構圖和規則
uuid: 886d4abe-b1 b6-4983-b4 fb-b552 d54 d51 ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## 區段的用途

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. 在Audience Manager中，您可以使用伺服器端規則建立區段。這些規則可讓您根據網站訪客屬性建立對象群組，例如：

* 行為;
* 人口統計(年齡、性別、收入等);
* 您可以在使用者介面中定義的其他特性。

## 區段構成

Audience Manager區段是伺服器端規則，包含個別或特徵群組。特徵由稱為索引鍵值配對的資料元素組成。除了您在區段層級設定的規則，這些索引鍵值配對也包含符合特徵和區段成員資格的標準訪客。

## Adobe Analytics區段對應的考量事項

將Adobe Analytics區段或報表套裝對應至Experience Cloud組織時，Audience Manager會自動建立新的對應區段和特性。您無法從Audience Manager編輯或變更這些區段的儲存位置。不過，您在對應的Adobe Analytics區段或報表套裝上執行的任何變更，都會反映在Audience Manager中。

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## 使用區段產生器建立規則型區段

不同於在回應簡單/無條件的情況下引發的傳統像素，區段產生器可讓您建立複雜的區段需求。Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. 這些功能有助於建立與您業務需求相關的目標受眾細分。

## 福利

區段在標準像素的對象建立/分段程序上改進，因為它們可讓您：

* 建立具有第一方及第三方特徵的相關有用區段。
* 使用布林運算元、比較運算式和最近/頻率標準，建立複雜複雜的區段規則。
* 傳送區段資料給目的地合作夥伴。
* 使用Audience Manager報告監控效能。

>[!MORE_贊_ this]
>
>* [訊號、特徵和區段](../../reference/signal-trait-segment.md)

