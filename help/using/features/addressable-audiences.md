---
description: 「可定址對象」功能和使用案例的概述。
keywords: DIL
seo-description: 「可定址對象」功能和使用案例的概述。
seo-title: 可定址受眾
solution: Audience Manager
title: 可定址受眾
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: 符合率
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience]功能的概述及使用案例。

## 什麼是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

[!UICONTROL Addressable Audiences]功能顯示您在[!DNL Audience Manager]收集資料的所有屬性與您選取目的地之間所看到的觀眾重疊。 為協助您瞭解此概念，請檢視下圖。 每個社交圈之間的重疊代表不同類型的可定址觀眾。

![](assets/addressableAudienceVenn.png)


| 量度 | 說明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] for a  [!UICONTROL Destination] | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與您選擇的[!UICONTROL destination]相符的所有裝置計數。 <br><br>此量度很有用，因為它顯示： <ul><li>[!DNL Audience Manager]在特定目標[!UICONTROL destination]上可觸及的總[!UICONTROL addressable audience]的大小。</li><li>[!DNL Audience Manager]設定檔存放區對於定位平台及其受眾的大小有多大。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧視窗中，已在您的屬性上實現[!UICONTROL rule-based trait]或離線檔案中實現[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Addressable Audience Match Rate] | 在回顧視窗期間實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置與我們已與所選[!UICONTROL destination]進行ID同步的裝置的重疊計數，不論同步時間。<br><br>此量度代表下列裝置：<ul><li>已在回顧視窗`AND`期間實現[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>不論同步的時間為何，都能與所選的[!UICONTROL destination]同步ID。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] 在 [!UICONTROL Customer Total Audience] ÷以百分比表示。 |
| [!UICONTROL Total Segment Population] | 報告回顧期間，屬於[!UICONTROL segment]成員的所有設備的計數。 |
| [!UICONTROL Segment Addressable Audience] | 在報告回顧期間屬於[!UICONTROL segment]並在您的網站上同步作用中ID的使用者人數。 [!UICONTROL Segments] 可透過Audience Marketplace取得，包含您自己的第一方資料以及第 [!UICONTROL traits] 二方和第 [三方資料](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。<br><br>提示：當與1天回顧期間搭配使用時，此度量可協助您瞭解您的目前狀態 [!UICONTROL segments]。這是因為[!UICONTROL Segment Addressable Audience]量度代表在前一天中一直留在[!UICONTROL segment]中的使用者。 結合此點與[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實，結合此量度和回顧期間可提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] 在 [!UICONTROL Total Segment Population] ÷以百分比表示。 |

## [!UICONTROL Addressable Audiences] 介面 {#addressable-audience-interface}

[!UICONTROL Addressable Audience]功能將此抽象概念轉化為可量化的資料。 在[!DNL Audience Manager]中，此功能會顯示觀眾與資料視覺化的重疊部分，這些視覺化可提供一目瞭然的資訊以及表格格式的數值資料。

[!UICONTROL Addressable Audiences] 的子菜單 **[!UICONTROL Audience Data > Destinations]**。選擇&#x200B;**[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;可查看可定址的觀眾量度。

![](assets/addressable-audiences-landing.png)

您在[!UICONTROL Addressable Audiences]登陸頁面上可看到的三個度量代表：

| 量度 | 說明 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此度量代表過去30天的[!UICONTROL Customer Addressable Audience]（如上表所述）*。* |
| **[!UICONTROL Match Rate]** | 此度量代表過去30天&#x200B;*的[!UICONTROL Addressable Audience Match Rate]（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與此[!UICONTROL destination]相符的所有裝置計數。 如需詳細資訊，請參閱[平台層級量度](/help/using/features/addressable-audiences.md#platform-level-metrics)。 |

按一下[!UICONTROL server-to-server destination]的名稱，以檢視可定址的觀眾資料。 注意，此功能僅傳回[!UICONTROL server-to-server destinations]的資料，且存取需要管理員權限。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測與規劃：資** [!UICONTROL Segment Addressable Audience] 料可讓您更精細地瞭解您打算傳送至目的地的細分，以便鎖定受眾並啟用。

* **效能評論：** 此功 [!UICONTROL Addressable Audiences] 能也是疑難排解工具。它可讓您檢視促銷活動成效、瞭解促銷活動觸及面，並讓您在看不到預期結果時，與目標／啟動合作夥伴進行交叉檢查。

### 使用第三方資料進行預測及對匹配率的影響

在購買協力廠商資料以贏取觀眾之前，客戶可以驗證與其他資料供應商的重疊。 這可協助您在購買新資料之前，做出明智的決策。 購買之協力廠商資料的ID同步不僅取決於您資料的重疊，還取決於協力廠商與所有其他[!DNL Audience Manager]客戶的足跡。 您的[!DNL Adobe]顧問可協助您識別其他相關資料來源，以最佳化客源搜尋活動。

### 行動使用者與比對率

嘗試連線[!DNL Safari]或行動應用程式使用者時，沒有第三方[!DNL cookies]存在時，會有空隙。 因此，很難將使用者與某些合作夥伴同步，因為媒體傳送記錄中只提供同步的第三方[!DNL cookies]的[!DNL Adobe] ID。 這是您為何可能看到[!UICONTROL destinations]的[低匹配率](../features/addressable-audiences.md#low-match-rates)的原因。

## [!UICONTROL Addressable Audiences]和[!UICONTROL Destinations] {#date-ranges}中的日期範圍

請閱讀以下各節，瞭解[!UICONTROL Addressable Audience]或[!UICONTROL Destination]報表中可用日期範圍以及資料在每個間隔之外的老化情形。

## 可用日期範圍和時區{#available-date-ranges}

<!-- addressable-audience-dates.xml -->

[!UICONTROL Addressable Audiences]和[目標](../features/destinations/destinations.md)的報表使用相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔從前24小時時段的「午夜」到「午夜」。它不是即時或目前的度量。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍都設定在[!DNL UTC]時區中。 請參閱Audience Manager中的[時區](../reference/aam-time-zones.md)。

## 日期範圍間隔{#date-range-intervals}中的資料

[!UICONTROL Addressable Audience]和[!UICONTROL Destination]量度會傳回所選時間間隔內的獨特使用者計數。 例如，即使訪客多次造訪您的網站，訪客也只會被計算一次。 第一次瀏覽是獨特的瀏覽，並會被錄制。 後續的瀏覽是回訪，因為並非唯一，所以不會計入。

日期範圍包含所選時間間隔或較舊日期的資料。 而且，資料會隨著時間流逝而在每個報告間隔中老化。 例如，假設您在選擇[!UICONTROL Last 30 Days]選項後會看到2位訪客。 在報表中，這些訪客：

* *將* 包含在較長時間間隔（60天、90天和期限）傳回的結果中。
* *不會包* 含在選項前的較短間隔 [!UICONTROL Last 30 Day] 中（目前、7天和14天）。

而在第31天，這些訪客只會在60天、90天和[!UICONTROL Lifetime]結果中顯示。 他們已經過了30天的間隔。 訪客不會在[!UICONTROL Lifetime]間隔內變老。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本節說明[!UICONTROL Addressable Audiences]提供的量度類型。

### 客戶層級量度{#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客來到您的網站時，或您傳送傳入資料檔案至[!DNL Audience Manager]時所發現之特徵的資料。 這些量度可提供您帳戶的受眾規模完整檢視。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顧視窗期間實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置與我們擁有與所選目的地同步ID的裝置的重疊計數，不論同步時間。<br><br>此量度代表下列裝置：<ul><li>已在回顧視窗`AND`期間實現[!UICONTROL rule-based]或[!UICONTROL onboarded trait]</li><li>不論同步的時間為何，都能與所選的[!UICONTROL destination]同步ID。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧視窗中，已在您的屬性上實現[!UICONTROL rule-based trait]或離線檔案中實現[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] 在 [!UICONTROL Customer Total Audience] ÷以百分比表示。 |

### 區段層級符合量度{#segment-level-metrics}

這些量度會傳回[!UICONTROL segment]會籍的資料。 這些功能可協助您更精細精確地檢視每個[!UICONTROL segments]的受眾大小。

>[!NOTE]
>
>在[!UICONTROL segment]層級套用回顧視窗的方式與在客戶層級不同。 訪客可於10天前來到網站並實現[!UICONTROL trait]，而且可自此符合[!UICONTROL segment]的資格，並於2天前退出[!UICONTROL segment]。 套用7天回顧時，這些訪客會計入[!UICONTROL segment]層級，但不會計入客戶層級。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 在報告回顧期間屬於[!UICONTROL segment]並在您的網站上同步作用中ID的使用者人數。 區段可以透過[Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)中取得的[!UICONTROL traits]，包含您自己的第一方資料、第二方資料和第三方資料。<br><br>提示：當與1天回顧期間搭配使用時，此度量可協助您瞭解您的目前狀態 [!UICONTROL segments]。這是因為[!UICONTROL Segment Addressable Audience]量度代表在前一天中一直留在[!UICONTROL segment]中的使用者。 結合此點與[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實，結合此量度和回顧期間可提供[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Total Segment Population] | 報告回顧期間，屬於[!UICONTROL segment]成員的所有設備的計數。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] 在 [!UICONTROL Total Segment Population] ÷以百分比表示。 |

### 平台層級量度{#platform-level-metrics}

此度量會傳回所有[!DNL Audience Manager]客戶所收集之活動的資料。 與匯總的[!DNL Audience Manager]客戶相比，他們可以提供更廣泛的客戶受眾視圖。

| 量度 | 說明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與您選擇的[!UICONTROL destination]相符的所有裝置計數。 <br><br>此量度很有用，因為它顯示：<ul><li>[!DNL Audience Manager]可在特定目標上到達的[!UICONTROL total addressable audience]大小。</li><li>[!DNL Audience Manager]設定檔存放區對於定位平台及其受眾的大小有多大。</li></ul> |

## 比較[!UICONTROL Customer]和[!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不應比較[!UICONTROL Customer Addressable Audience]和[!UICONTROL Segment Addressable Audience]量度，以判斷其中一個量度是否比另一個量度更重要。 這些是個別、不同和獨立的度量。 如上述定義所述，每個定義都源自不同的資料集。 因此，如果一個量度大於另一個量度，您應避免得出任何結論。 在比較這些時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 是以您自己 [!UICONTROL trait] 的第 *一方資料的實現為基礎*。此量度可提供您與資料合作夥伴整合的廣泛、完整檢視。

* [!UICONTROL Segment Addressable Audiences] 是以您自己第一 *方資料的區段資格，加上第二方及第三方資料為基礎*。此量度提供定位平台中[!UICONTROL addressable audiences]的精細、更精確的檢視。

## [!UICONTROL Addressable Audiences] {#low-match-rates}匹配率低的原因

導致[!UICONTROL Addressable Audience]低匹配率或報告數字不一致的常見元素。

| 原因 | 說明 |
|---|---|
| 行動流量 | 大多數[!UICONTROL server-to-server]整合都依賴協力廠商[!DNL cookies]所促成的同步程式。 不過，行動環境不使用協力廠商[!DNL cookies]。 因此，與[!UICONTROL segment]大小相比，您的[!UICONTROL Addressable Audiences]數字可能看起來很低。 <br><br>自2018年1月起，您可以在為觀眾設定的相同和目的地 [!DNL Google] 啟 [!DNL Adobe Advertising Cloud] 動行動觀眾 [!UICONTROL cookie-based] 群。雖然這表示您可以將結合[!DNL cookie]和行動ID會籍的[!UICONTROL segments]傳送至[!DNL Google]和[!DNL Advertising Cloud]目標，但請記住，[!UICONTROL Addressable Audiences]只會顯示[!DNL cookie] ID和目標之間的重疊。 [!DNL Audience Manager] 傳送100%的行動對象 [!UICONTROL destinations]給，但行動對象不會依量 [!UICONTROL Addressable Audience] 度測量。<br><br>**注意**:例如，以 [!UICONTROL segment] 人口為1,000,000的人為例。如果您將此[!UICONTROL segment]對應至[!DNL Google]或[!DNL Adobe Advertising Cloud]目標，則可能會看到[!UICONTROL Addressable Audience]共700,000台裝置，而[!UICONTROL Match Rate]共70%。 700,000會員資格由[!DNL cookie] ID組成，ID與[!UICONTROL destination]同步。 您的[!UICONTROL Addressable Audience]實際上可能會高很多，因為可定址的行動ID不會顯示在此量度中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 封鎖協力廠商 [!DNL cookies]。這可防止[!DNL Audience Manager]將ID與[!UICONTROL destination]同步。 由於[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)的推出，您可預期[!UICONTROL addressable audiences]不會包含[!DNL Safari]使用者。 |
| 追蹤的媒體曝光 | 由於廣告伺服器的最佳實務，廣告標籤中不會進行ID同步。 大量進行離站廣告的客戶將不會將使用者同步到這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可能會減少[!UICONTROL addressable audience]數量。 |

## [!UICONTROL Addressable Audiences] {#troubleshooting}疑難排解

除了曲面匹配率外，還可以使用[!UICONTROL Addressable Audiences]作為故障排除工具。

例如，假設您傳送區段至[!UICONTROL destination]，而[!UICONTROL destination]顯示低報告數。 檢查[!UICONTROL Addressable Audience]結果將顯示這是技術問題還是只顯示匹配率低的情況。 低比對率顯示您的[!UICONTROL destination]對您選取的區段並不是那麼好。 但是，[!DNL Audience Manager]和[!UICONTROL destination]之間的[!UICONTROL total addressable audience]數值的差異表示整合、同步或其他技術問題。 在這些情況下，請連絡您的客戶經理。
