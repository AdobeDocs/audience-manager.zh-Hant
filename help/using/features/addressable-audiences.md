---
description: 「可定址對象」功能和使用案例的概述。
keywords: DIL
seo-description: 「可定址對象」功能和使用案例的概述。
seo-title: 可定址受眾
solution: Audience Manager
title: 可定址受眾
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

功能與使 [!UICONTROL Addressable Audience] 用案例的概述。

## 什麼是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

此功 [!UICONTROL Addressable Audiences] 能可顯示您在收集資料的所有屬性與所選目的地之間 [!DNL Audience Manager] 的對象重疊。 為協助您瞭解此概念，請檢視下圖。 每個社交圈之間的重疊代表不同類型的可定址觀眾。

![](assets/addressableAudienceVenn.png)


| 量度 | 說明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] for a [!UICONTROL Destination] | 在報告回顧期間與平台層級所有 [!DNL Audience Manager] 客戶互動且可能與您選擇的裝置相符的所有裝置計數 [!UICONTROL destination]。 <br><br>此量度很有用，因為它顯示： <ul><li>特定目標可觸及 [!UICONTROL addressable audience] 的 [!DNL Audience Manager] 總計大小 [!UICONTROL destination]。</li><li>定位平 [!DNL Audience Manager] 台的設定檔存放區有多大，其受眾也有多大。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧視窗中，已在您的屬 [!UICONTROL rule-based trait] 性上或離線檔案 [!UICONTROL onboarded trait] 中實現的裝置計數。 |
| [!UICONTROL Addressable Audience Match Rate] | 在回顧視窗中已實現或已實現 [!UICONTROL rule-based trait][!UICONTROL onboarded trait] ID同步的裝置的重疊計數，以及我們與所選裝置ID同步的 [!UICONTROL destination] 裝置（不論同步時間）。<br><br>此量度代表下列裝置：<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 在報告回顧期間，屬於您的所有 [!UICONTROL segment] 裝置的計數。 |
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. [!UICONTROL Segments] 可透過在Audience Marketplace中取得，加入您自己的第一方資料以及第 [!UICONTROL traits] 二方和第 [三方資料](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。 <br><br>提示： 當與1天回顧期間搭配使用時，此度量可協助您瞭解您的目前狀態 [!UICONTROL segments]。 這是因為量 [!UICONTROL Segment Addressable Audience] 度代表在前一天一直呆 [!UICONTROL segment] 在其中的使用者。 結合這項功能與每日 [!DNL Audience Manager] 重新整 [!UICONTROL Addressable Audiences] 理的事實，結合此度量和回顧期間可提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 介面 {#addressable-audience-interface}

這個 [!UICONTROL Addressable Audience] 功能將這個抽象概念轉化為可量化的資料。 在此 [!DNL Audience Manager]功能中，此功能會顯示觀眾與資料視覺化的重疊，這些視覺化可提供一目瞭然的資訊，以及表格格式的數值資料。

[!UICONTROL Addressable Audiences] 的子菜單 **[!UICONTROL Audience Data > Destinations]**。 選取 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可定址的觀眾量度。

![](assets/addressable-audiences-landing.png)

您可在登陸頁面上看到的三個 [!UICONTROL Addressable Audiences] 度量代表：

| 量度 | 說明 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度代表 [!UICONTROL Customer Addressable Audience] 過去30天(如上 *表所述)。* |
| **[!UICONTROL Match Rate]** | 此量度代 [!UICONTROL Addressable Audience Match Rate] 表過去30天 *的量度*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在報告回顧期間與平台層級所有 [!DNL Audience Manager] 客戶互動且可能符合此條件的所有裝置計數 [!UICONTROL destination]。 如需 [詳細資訊，請參閱平台層](/help/using/features/addressable-audiences.md#platform-level-metrics) 級量度。 |

按一下名稱可檢視可 [!UICONTROL server-to-server destination] 定址的觀眾資料。 請注意，此功能僅傳回資料， [!UICONTROL server-to-server destinations] 而且存取需要管理員權限。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測和規劃：** [!UICONTROL Segment Addressable Audience] 資料可讓您更精細地瞭解您打算傳送至目的地的細分，以利鎖定受眾並啟動受眾。

* **效能評論：** 此功 [!UICONTROL Addressable Audiences] 能也是疑難排解工具。 它可讓您檢視促銷活動成效、瞭解促銷活動觸及面，並讓您在看不到預期結果時，與目標／啟動合作夥伴進行交叉檢查。

### 使用第三方資料進行預測及對匹配率的影響

在購買協力廠商資料以贏取觀眾之前，客戶可以驗證與其他資料供應商的重疊。 這可協助您在購買新資料之前，做出明智的決策。 購買之協力廠商資料的ID同步不僅取決於您資料的重疊，還取決於協力廠商與所有其他客戶的 [!DNL Audience Manager] 足跡。 您的 [!DNL Adobe] 顧問可協助您找出其他相關資料來源，以最佳化客源開發活動。

### 行動使用者與比對率

嘗試連線或行動應用程 [!DNL Safari] 式使用者時，沒有協力廠商存在時會有 [!DNL cookies] 差距。 因此，很難將使用者與某些合作夥伴同步，因為媒體傳送記錄中只 [!DNL Adobe] 提供同步 [!DNL cookies] 的第三方ID。 這就是為什麼您會發現 [匹配率低](../features/addressable-audiences.md#low-match-rates)[!UICONTROL destinations]。

## 日期範圍(在 [!UICONTROL Addressable Audiences] 和 [!UICONTROL Destinations] {#date-ranges}

請閱讀以下各節，瞭解可用的日期範圍，以及報表中某或的資料在每個間隔之外的 [!UICONTROL Addressable Audience] 老化 [!UICONTROL Destination]。

## 可用日期範圍和時區 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您和目標的報 [!UICONTROL Addressable Audiences] 表 [會使用](../features/destinations/destinations.md) 相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔從前24小時時段的「午夜」到「午夜」。 它不是即時或目前的度量。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍皆設定在時 [!DNL UTC] 區中。 See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## 日期範圍間隔中的資料 {#date-range-intervals}

和 [!UICONTROL Addressable Audience] 度量 [!UICONTROL Destination] 會傳回所選時間間隔內的獨特使用者計數。 例如，即使訪客多次造訪您的網站，訪客也只會被計算一次。 第一次瀏覽是獨特的瀏覽，並會被錄制。 後續的瀏覽是回訪，因為並非唯一，所以不會計入。

日期範圍包含所選時間間隔或較舊日期的資料。 而且，資料會隨著時間流逝而在每個報告間隔中老化。 例如，假設您在選擇選項後看到2位訪 [!UICONTROL Last 30 Days] 客。 在報表中，這些訪客：

* *將包含* 在較長時間間隔（60天、90天和期限）傳回的結果中。
* *不會包含* 在選項前的較短間隔( [!UICONTROL Last 30 Day] 目前、7天和14天)中。

而在第31天，這些訪客只會在60天、90天和結果中出 [!UICONTROL Lifetime] 現。 他們已經過了30天的間隔。 訪客不會在間隔內過 [!UICONTROL Lifetime] 時。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本節說明由提供的量度類型 [!UICONTROL Addressable Audiences]。

### 客戶層級量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客來到您的網站時，或您傳送傳入資料檔案時所發現之特徵的資料 [!DNL Audience Manager]。 這些量度可提供您帳戶的受眾規模完整檢視。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顧視窗期間已實現或已實現 [!UICONTROL rule-based trait][!UICONTROL onboarded trait] 的裝置的重疊計數，以及我們擁有與所選目的地同步ID的裝置（不論同步時間）。<br><br>此量度代表下列裝置：<ul><li>Have realized either a [!UICONTROL rule-based] or an [!UICONTROL onboarded trait] during the look-back window `AND`</li><li>Have an ID sync with the chosen [!UICONTROL destination] regardless of the time of syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧視窗中，已在您的屬 [!UICONTROL rule-based trait] 性上或離線檔案 [!UICONTROL onboarded trait] 中實現的裝置計數。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 區段層級符合量度 {#segment-level-metrics}

這些量度會傳回會籍的 [!UICONTROL segment] 資料。 它們可協助您更精細、更精確地檢視每個人的受眾規模 [!UICONTROL segments]。

>[!NOTE]
>
>在層級套用回顧視窗的方 [!UICONTROL segment] 式與在客戶層級不同。 訪客可以在10天前來此網站， [!UICONTROL trait] 並瞭解自此之後，他們可以符合 [!UICONTROL segment] 一個資格並退出 [!UICONTROL segment] 2天前。 套用7天回顧時，這些訪客會計入層級， [!UICONTROL segment] 但不會計入客戶層級。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | The number of users who have belonged to the [!UICONTROL segment] during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via [!UICONTROL traits] acquired in the [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>提示： 當與1天回顧期間搭配使用時，此度量可協助您瞭解您的目前狀態 [!UICONTROL segments]。 這是因為量 [!UICONTROL Segment Addressable Audience] 度代表在前一天一直呆 [!UICONTROL segment] 在其中的使用者。 結合這項功能與每日 [!DNL Audience Manager] 重新整 [!UICONTROL Addressable Audiences] 理的事實，結合此度量和回顧期間可提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Total Segment Population] | 在報告回顧期間，屬於您的所有 [!UICONTROL segment] 裝置的計數。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台層級量度 {#platform-level-metrics}

此度量會傳回所有客戶所收集之活動的 [!DNL Audience Manager] 資料。 相較於整合的客戶，他們可以提供更廣泛的客戶觀 [!DNL Audience Manager] 眾。

| 量度 | 說明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在報告回顧期間與平台層級所有 [!DNL Audience Manager] 客戶互動且可能與您選擇的裝置相符的所有裝置計數 [!UICONTROL destination]。 <br><br>此量度很有用，因為它顯示：<ul><li>特定定位目 [!UICONTROL total addressable audience] 標可 [!DNL Audience Manager] 觸及的大小。</li><li>定位平 [!DNL Audience Manager] 台的設定檔存放區有多大，其受眾也有多大。</li></ul> |

## 比較 [!UICONTROL Customer] 和 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不應比較度量 [!UICONTROL Customer Addressable Audience] 和度 [!UICONTROL Segment Addressable Audience] 量，以判斷其中一個比另一個更重要。 這些是個別、不同和獨立的度量。 如上述定義所述，每個定義都源自不同的資料集。 因此，如果一個量度大於另一個量度，您應避免得出任何結論。 在比較這些時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 是以您自己 [!UICONTROL trait] 的 *第一方資料實現為基礎*。 此量度可提供您與資料合作夥伴整合的廣泛、完整檢視。

* [!UICONTROL Segment Addressable Audiences] 是以您自己第一 *方資料的區段資格，加上第二方和第三方資料為基礎*。 此量度可提供定位平台中您的詳細、更 [!UICONTROL addressable audiences] 精確的檢視。

## 對於低匹配率的原因 [!UICONTROL Addressable Audiences] {#low-match-rates}

導致匹配率低或報告 [!UICONTROL Addressable Audience] 數字不一致的常見元素。

| 原因 | 說明 |
|---|---|
| 行動流量 | 大部 [!UICONTROL server-to-server] 分整合都依賴協力廠商促成的同步程式 [!DNL cookies]。 不過，行動環境不會使用協力廠商 [!DNL cookies]。 因此，與大小相 [!UICONTROL Addressable Audiences] 比，您的數字可能看起來很 [!UICONTROL segment] 低。 <br><br>自2018年1月起，您可以在為觀眾設定的相同和目的地 [!DNL Google] 中啟 [!DNL Adobe Advertising Cloud] 動行動觀眾 [!UICONTROL cookie-based] 。 雖然這表示您可以將結合 [!UICONTROL segments] 的 [!DNL cookie] 和行動ID會籍傳送至您的 [!DNL Google] 和目的地，但請記住，只 [!DNL Advertising Cloud] 會顯示ID和目的地的 [!UICONTROL Addressable Audiences][!DNL cookie] 重疊。 [!DNL Audience Manager] 傳送100%的行動對象 [!UICONTROL destinations]給，但行動對象不會依量度 [!UICONTROL Addressable Audience] 測量。 <br><br>**注意&#x200B;**: 例如，以一[!UICONTROL segment]百萬人口為例。 如果您將此對[!UICONTROL segment]應至[!DNL Google]或目的[!DNL Adobe Advertising Cloud]地，您可能會看到700,000[!UICONTROL Addressable Audience]部裝置和70%[!UICONTROL Match Rate]的裝置。 700,000個會籍包含ID,[!DNL cookie]其ID與同步[!UICONTROL destination]。 實際[!UICONTROL Addressable Audience]上，您的可能性要高得多，因為可定址的行動ID不會出現在此量度中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 封鎖協力廠商 [!DNL cookies]。 這會阻 [!DNL Audience Manager] 止ID與同步 [!UICONTROL destination]。 隨著 [ITP 2.0的推出](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)，您可以預期不 [!UICONTROL addressable audiences] 會包含使用 [!DNL Safari] 者。 |
| 追蹤的媒體曝光 | 由於廣告伺服器的最佳實務，廣告標籤中不會進行ID同步。 大量進行離站廣告的客戶將不會將使用者同步到這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可減少 [!UICONTROL addressable audience] 數量。 |

## 疑難排解 [!UICONTROL Addressable Audiences] {#troubleshooting}

除了曲面匹配率外，還可以將其用作 [!UICONTROL Addressable Audiences] 故障排除工具。

例如，假設您傳送區段給，且顯示 [!UICONTROL destination] 低報 [!UICONTROL destination] 告數目。 檢查結 [!UICONTROL Addressable Audience] 果會顯示這是技術問題，還是只是低比對率的問題。 低比對率顯示您 [!UICONTROL destination] 的區段並不是那麼適合您。 但是，與之間的數 [!UICONTROL total addressable audience] 字差異表 [!DNL Audience Manager] 明是 [!UICONTROL destination] 整合、同步或其他技術問題。 在這些情況下，請連絡您的客戶經理。
