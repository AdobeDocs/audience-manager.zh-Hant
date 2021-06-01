---
description: 可定址對象功能和使用案例的概觀。
keywords: DIL
seo-description: 可定址對象功能和使用案例的概觀。
seo-title: 可定址受眾
solution: Audience Manager
title: 可定址受眾
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: 符合率
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience]功能及使用案例的概述。

## 什麼是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences]功能顯示您在[!DNL Audience Manager]收集資料的所有屬性與您所選目的地之間所看見的對象重疊。 為協助您了解此概念，請參閱下圖。 每個圓圈之間的重疊代表不同類型的可定址對象。

![](assets/addressableAudienceVenn.png)


| 量度 | 說明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] a  [!UICONTROL Destination] | 在報表回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動，且可能符合您所選[!UICONTROL destination]的所有裝置計數。 <br><br>此量度很實用，因為它會顯示： <ul><li>[!DNL Audience Manager]可針對特定目標[!UICONTROL destination]達到的總數[!UICONTROL addressable audience]的大小。</li><li>[!DNL Audience Manager]設定檔池對於目標平台的大小及其對象的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧期間，已在您的屬性上或從離線檔案中實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Addressable Audience Match Rate] | 在回顧期間實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置的重疊計數，以及我們有與所選[!UICONTROL destination]同步之ID的裝置（不論同步的時間為何）。<br><br>此量度代表具備下列條件的裝置：<ul><li>在回顧期間`AND`實現[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>具有與所選[!UICONTROL destination]同步的ID（不論同步的時間為何）。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 在報表回顧期間，屬於[!UICONTROL segment]成員的所有裝置計數。 |
| [!UICONTROL Segment Addressable Audience] | 在報表回顧期間屬於[!UICONTROL segment]且在您的網站上具有同步作用中ID的使用者人數。 [!UICONTROL Segments] 可以透過在Audience Marketplace中取得，包含您自己的第一方資料、第 [!UICONTROL traits] 二方和第 [三方資料](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。<br><br>提示：與1天回顧期間搭配使用時，此量度可協助您了解的目前狀 [!UICONTROL segments]態。這是因為[!UICONTROL Segment Addressable Audience]量度代表在[!UICONTROL segment]中停留了一整天的使用者。 將此量度與[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實結合，即可結合此量度與回顧期間，提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 介面 {#addressable-audience-interface}

[!UICONTROL Addressable Audience]功能將此抽象概念轉換為可量化的資料。 在[!DNL Audience Manager]中，此功能會顯示對象與資料視覺效果的重疊，這些視覺效果可提供一目瞭然的資訊，並以表格形式呈現數值資料。

[!UICONTROL Addressable Audiences] 位於中 **[!UICONTROL Audience Data > Destinations]**。選取&#x200B;**[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;以查看可定址的受眾量度。

![](assets/addressable-audiences-landing.png)

您可以在[!UICONTROL Addressable Audiences]登陸頁面上看到的三個量度代表：

| 量度 | 說明 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度代表過去30天的[!UICONTROL Customer Addressable Audience]（如上表所述）*。* |
| **[!UICONTROL Match Rate]** | 此量度代表過去30天&#x200B;*的[!UICONTROL Addressable Audience Match Rate]（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在報表回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與此[!UICONTROL destination]相符的所有裝置計數。 如需詳細資訊，請參閱[平台層級量度](/help/using/features/addressable-audiences.md#platform-level-metrics)。 |

按一下[!UICONTROL server-to-server destination]的名稱，即可檢視可定址的受眾資料。 注意，此功能僅返回[!UICONTROL server-to-server destinations]的資料，並且訪問需要管理員權限。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測和規劃：** [!UICONTROL Segment Addressable Audience] 資料可讓您進一步細分您打算傳送至目的地的區段，以便鎖定受眾並加以啟用。

* **效能審核：** 此功 [!UICONTROL Addressable Audiences] 能也是疑難排解工具。它可讓您檢閱促銷活動績效、了解促銷活動觸及率，以及如果您看不到預期的結果，則可讓您與目標鎖定/啟用合作夥伴交叉檢查。

### 使用第三方資料進行勘察及對匹配率的影響

購買第三方資料以進行受眾贏取前，客戶可驗證與其他資料提供者的重疊。 這可協助您在購買新資料前做出明智的決策。 購買的第三方資料的ID同步不僅取決於您資料的重疊，也取決於第三方提供者與所有其他[!DNL Audience Manager]客戶的足跡。 您的[!DNL Adobe]顧問可協助您識別其他相關資料來源，以最佳化探礦促銷活動。

### 行動使用者和符合率

嘗試連線[!DNL Safari]或行動應用程式使用者時，若無第三方[!DNL cookies]存在，便會出現差距。 這會讓使用者難以與某些合作夥伴同步，因為媒體傳送記錄中僅提供同步第三方[!DNL cookies]的[!DNL Adobe] ID。 這就是為什麼您可能會看到[!UICONTROL destinations]低匹配率](../features/addressable-audiences.md#low-match-rates)的原因。[

## [!UICONTROL Addressable Audiences]和[!UICONTROL Destinations] {#date-ranges}中的日期範圍

請閱讀以下各節，了解[!UICONTROL Addressable Audience]或[!UICONTROL Destination]報表中可用的日期範圍，以及資料在每個間隔之外的老化程度。

## 可用日期範圍和時區{#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences]和[目的地](../features/destinations/destinations.md)的報表使用相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔從前24小時時段的午夜到午夜。這不是即時或目前時間量度。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍都設定在[!DNL UTC]時區中。 請參閱Audience Manager](../reference/aam-time-zones.md)中的[時區。

## 日期範圍間隔{#date-range-intervals}中的資料

[!UICONTROL Addressable Audience]和[!UICONTROL Destination]量度會傳回所選時間間隔內的不重複使用者計數。 例如，即使某位訪客多次造訪您的網站，也只會計算一次。 第一次瀏覽是唯一瀏覽並記錄。 後續的造訪會回訪，不會計入，因為它們並非唯一。

日期範圍包含所選時間間隔或較舊時間的資料。 而且，資料會隨著時間流逝而在每個報告間隔中老化。 例如，假設您在選擇[!UICONTROL Last 30 Days]選項後看到2個訪客。 在報表中，這些訪客：

* *會* 以較長的時間間隔（60天、90天和期限）傳回的結果中包含。
* *不會以* 選項之前的較短間隔( [!UICONTROL Last 30 Day] 目前、7天和14天)納入。

而在第31天，這些訪客只會顯示在60天、90天和[!UICONTROL Lifetime]結果中。 他們在30天間隔內過了年齡。 訪客不會超出[!UICONTROL Lifetime]間隔。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本節說明[!UICONTROL Addressable Audiences]提供的量度類型。

### 客戶層級量度{#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客來到您的網站，或您將傳入資料檔案傳送至[!DNL Audience Manager]時，所實現特徵的資料。 這些量度可提供您帳戶的受眾規模完整檢視。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顧期間實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置重疊計數，以及我們與所選目的地有ID同步的裝置（不論同步的時間為何）。<br><br>此量度代表具備下列條件的裝置：<ul><li>在回顧期間`AND`實現[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>具有與所選[!UICONTROL destination]同步的ID（不論同步的時間為何）。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧期間，已在您的屬性上或從離線檔案中實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 區段層級符合量度{#segment-level-metrics}

這些量度會傳回[!UICONTROL segment]成員資格的資料。 它們可協助您更精細、更精確地檢視每個[!UICONTROL segments]的受眾大小。

>[!NOTE]
>
>在[!UICONTROL segment]級別應用回顧窗口的方式與在客戶級別應用回顧窗口的方式不同。 訪客可以在10天前來到網站並實現[!UICONTROL trait]，且自那時起可以符合[!UICONTROL segment]資格，並在2天前退出[!UICONTROL segment]。 套用7天回顧時，這些訪客會在[!UICONTROL segment]層級計算，但不會在客戶層級計算。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 在報表回顧期間屬於[!UICONTROL segment]且在您的網站上具有同步作用中ID的使用者人數。 區段可以透過[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)中取得的[!UICONTROL traits]，包含您自己的第一方資料、第二方資料和第三方資料。<br><br>提示：與1天回顧期間搭配使用時，此量度可協助您了解的目前狀 [!UICONTROL segments]態。這是因為[!UICONTROL Segment Addressable Audience]量度代表在[!UICONTROL segment]中停留了一整天的使用者。 將此量度與[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實結合，即可結合此量度與回顧期間，提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Total Segment Population] | 在報表回顧期間，屬於[!UICONTROL segment]成員的所有裝置計數。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台層級量度{#platform-level-metrics}

此量度會傳回所有[!DNL Audience Manager]客戶所收集之活動的資料。 與匯總的[!DNL Audience Manager]客戶相比，它們可提供更廣泛的客戶受眾檢視。

| 量度 | 說明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在報表回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動，且可能符合您所選[!UICONTROL destination]的所有裝置計數。 <br><br>此量度很實用，因為它會顯示：<ul><li>[!DNL Audience Manager]可到達特定目標目標的[!UICONTROL total addressable audience]大小。</li><li>[!DNL Audience Manager]設定檔池對於目標平台的大小及其對象的大小。</li></ul> |

## 比較[!UICONTROL Customer]和[!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不應比較[!UICONTROL Customer Addressable Audience]和[!UICONTROL Segment Addressable Audience]量度來判斷其中一個量度是否比另一個量度更重要。 這些是不同、不同和獨立的量度。 如上述定義所述，每個定義都衍生自不同的資料集。 有鑑於此，您應避免在某個量度大於另一個量度時得出任何結論。 比較時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 是根據 [!UICONTROL trait] 您 *自己第一方資料的實現*。此量度可提供您與資料合作夥伴整合的全面檢視。

* [!UICONTROL Segment Addressable Audiences] 是根據您自己第 *一方資料的區段資格，以及第二方和第三方資料*。此量度可提供目標平台中[!UICONTROL addressable audiences]的精細、更精確的檢視。

## [!UICONTROL Addressable Audiences] {#low-match-rates}匹配率低的原因

造成[!UICONTROL Addressable Audience]低匹配率或所報告數字差異的常見元素。

| 原因 | 說明 |
|---|---|
| 行動流量 | 大部分的[!UICONTROL server-to-server]整合都仰賴由協力廠商[!DNL cookies]提供的同步程式。 不過，行動環境不使用第三方[!DNL cookies]。 因此，與[!UICONTROL segment]大小相比，您的[!UICONTROL Addressable Audiences]數字可能看起來很低。 <br><br>自2018年1月起，您可以在為對象設定的相同和 [!DNL Google] 目的地 [!DNL Adobe Advertising Cloud] 中啟用行動 [!UICONTROL cookie-based] 對象。雖然這表示您可以將[!UICONTROL segments]與行動ID成員資格結合傳送至[!DNL Google]和[!DNL Advertising Cloud]目的地，但請記住，[!UICONTROL Addressable Audiences]只會顯示[!DNL cookie] ID與目的地之間的重疊。 [!DNL cookie][!DNL Audience Manager] 會將100%的行動受眾傳送 [!UICONTROL destinations]至，但行動受眾不是由量度 [!UICONTROL Addressable Audience] 測量。<br><br>**注意**:例如，以 [!UICONTROL segment] 人口為1,000,000的。如果將此[!UICONTROL segment]對應至[!DNL Google]或[!DNL Adobe Advertising Cloud]目的地，您可能會看到包含700,000個裝置的[!UICONTROL Addressable Audience]和70%的[!UICONTROL Match Rate]。 700,000的成員資格包含[!DNL cookie] ID，這些ID與[!UICONTROL destination]同步。 事實上，您的[!UICONTROL Addressable Audience]可能會高得多，因為可定址的行動ID不會出現在此量度中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 封鎖第三方 [!DNL cookies]。這可防止[!DNL Audience Manager]與[!UICONTROL destination]同步ID。 導入[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)後，您可以預期您的[!UICONTROL addressable audiences]不會包含[!DNL Safari]使用者。 |
| 追蹤媒體曝光數 | 由於廣告伺服器最佳實務，不會在廣告標籤內進行ID同步。 執行大量離站廣告的客戶不會將使用者同步至這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可能會減少[!UICONTROL addressable audience]數量。 |

## 使用[!UICONTROL Addressable Audiences]進行故障排除 {#troubleshooting}

除了曲面匹配率外，還可以使用[!UICONTROL Addressable Audiences]作為故障排除工具。

例如，假設您傳送區段至[!UICONTROL destination]，而[!UICONTROL destination]顯示低報表數。 檢查[!UICONTROL Addressable Audience]結果會顯示這是技術問題，還是匹配率低的情況。 低匹配率顯示您的[!UICONTROL destination]對於您選取的區段來說並不都是那麼好。 但是，[!DNL Audience Manager]和[!UICONTROL destination]之間的[!UICONTROL total addressable audience]數字差異表示整合、同步或其他技術問題。 在這些情況下，請連絡您的客戶經理。
