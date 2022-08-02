---
description: 可定址受眾功能和使用案例的概述。
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: 可定址受眾
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

概述 [!UICONTROL Addressable Audience] 功能和使用案例。

## 什麼是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

的 [!UICONTROL Addressable Audiences] 功能顯示您在所有屬性中看到的受眾之間的重疊 [!DNL Audience Manager] 收集資料和所選目標。 要幫助您瞭解此概念，請查看下圖。 每個圓之間的重疊表示不同類型的可定址觀眾。

![](assets/addressableAudienceVenn.png)


| 量度 | 說明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 為 [!UICONTROL Destination] | 所有與所有設備互動的設備的計數 [!DNL Audience Manager] 在報告回顧期間處於平台級別的客戶，可與您選擇的 [!UICONTROL destination]。 <br><br>此度量很有用，因為它顯示： <ul><li>總大小 [!UICONTROL addressable audience] 那 [!DNL Audience Manager] 可以觸及特定目標 [!UICONTROL destination]。</li><li>多大 [!DNL Audience Manager] 配置檔案池用於目標平台及其受眾的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已實現以下任一項的設備數 [!UICONTROL rule-based trait] 你的財產或 [!UICONTROL onboarded trait] 從離線檔案中刪除。 |
| [!UICONTROL Customer Addressable Audience] | 已實現A的設備的重疊計數 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 在回查窗口和與所選設備進行ID同步的設備 [!UICONTROL destination] 不管同步時間。<br><br>此度量表示以下設備：<ul><li>已經意識到 [!UICONTROL rule-based] 或 [!UICONTROL onboarded trait] 在回顧窗口 `AND`</li><li>與所選的ID同步 [!UICONTROL destination] 不管同步時間。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |
| [!UICONTROL Total Segment Population] | 屬於您的所有設備的計數 [!UICONTROL segment] 在報告回顧期間。 |
| [!UICONTROL Segment Addressable Audience] | 屬於的用戶數 [!UICONTROL segment] 在報告回查期間，並在您的站點上同步活動ID。 [!UICONTROL Segments] 可以包括您自己的第一方資料、第二和第三方資料，通過 [!UICONTROL traits] 在 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。 <br><br>提示：當與1天回顧時段一起使用時，此度量可幫助您瞭解當前狀態 [!UICONTROL segments]。 這是因為 [!UICONTROL Segment Addressable Audience] 度量表示留在 [!UICONTROL segment] 前一天。 把這和 [!DNL Audience Manager] 刷新 [!UICONTROL Addressable Audiences] 每天，將此度量與回望時段相結合，提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 介面 {#addressable-audience-interface}

的 [!UICONTROL Addressable Audience] 特徵將這個抽象概念轉化為可量化的資料。 在 [!DNL Audience Manager]，此功能顯示受眾與資料可視化的重疊，這些可視化提供一覽式資訊以及表格形式的數字資料。

[!UICONTROL Addressable Audiences] 位於 **[!UICONTROL Audience Data > Destinations]**。 選擇 **[!UICONTROL Integrated Platforms > Device-Based]** 查看可定址的受眾度量。

![](assets/addressable-audiences-landing.png)

您在 [!UICONTROL Addressable Audiences] 登錄頁表示：

| 量度 | 說明 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此度量表示 [!UICONTROL Customer Addressable Audience] （見上表） *最後30天。* |
| **[!UICONTROL Match Rate]** | 此度量表示 [!UICONTROL Addressable Audience Match Rate] （見上表） *過去30天*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 所有與所有設備互動的設備的計數 [!DNL Audience Manager] 在報告回顧期間處於平台級別的客戶，可與此相匹配 [!UICONTROL destination]。 請參閱 [平台級度量](/help/using/features/addressable-audiences.md#platform-level-metrics) 的子菜單。 |

按一下 [!UICONTROL server-to-server destination] 查看可定址的受眾資料。 注意，此功能返回資料 [!UICONTROL server-to-server destinations] 僅和訪問需要管理員權限。

![](assets/addressableAudiences.png)

查看此資料可幫助您：

* **預測和規劃：** [!UICONTROL Segment Addressable Audience] 資料使您能夠更精細地瞭解您計畫發送到目標的網段，以便針對受眾和激活受眾。

* **效能審查：** 的 [!UICONTROL Addressable Audiences] 功能也是故障排除工具。 它允許您查看市場活動績效、瞭解市場活動影響範圍，並允許您與目標/激活合作夥伴進行交叉檢查，如果您看不到預期的結果。

### 利用第三方資料進行勘探及其對匹配率的影響

在購買第三方資料以獲取受眾之前，客戶可以驗證與其他資料提供商的重疊。 這有助於您在購買新資料之前做出明智的決定。 購買的第三方資料的ID同步不僅取決於資料的重疊，還取決於第三方提供商對所有其他資料的足跡 [!DNL Audience Manager] 客戶。 您 [!DNL Adobe] 顧問可以幫助您確定其他相關資料源，以優化潛在客戶活動。

### 移動用戶和匹配率

嘗試連接時存在間隙 [!DNL Safari] 或沒有第三方的移動應用用戶 [!DNL cookies] 現在。 這使得用戶很難與某些合作夥伴同步，因為只有那些 [!DNL Adobe] 已同步第三方的ID [!DNL cookies] 在媒體傳遞日誌中提供。 這就是你可能看到 [低匹配率](../features/addressable-audiences.md#low-match-rates) 為 [!UICONTROL destinations]。

## 日期範圍 [!UICONTROL Addressable Audiences] 和 [!UICONTROL Destinations] {#date-ranges}

請閱讀以下各節，瞭解可用日期範圍以及資料如何在報告中的每個間隔之外老化 [!UICONTROL Addressable Audience] 或 [!UICONTROL Destination]。

## 可用日期範圍和時區 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您的報告 [!UICONTROL Addressable Audiences] 和 [目標](../features/destinations/destinations.md) 使用相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔從前24小時時段的午夜到午夜。 它不是即時或當前時間度量。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍均在 [!DNL UTC] 時區。 請參閱 [Audience Manager中的時區](../reference/aam-time-zones.md)。

## 日期範圍內的資料間隔 {#date-range-intervals}

的 [!UICONTROL Addressable Audience] 和 [!UICONTROL Destination] 度量返回所選時間間隔內的唯一用戶計數。 例如，即使訪問者多次來到您的站點，也只能計數一次。 第一次訪問是獨特的訪問並錄制。 隨後的訪問是回訪，並且不計算在內，因為這些訪問並非唯一。

日期範圍包含所選時間間隔或舊時間的資料。 而且，資料會隨著時間的流逝而從每個報告間隔中老化。 例如，假設您在選擇 [!UICONTROL Last 30 Days] 的雙曲餘切值。 在報告中，這些訪問者：

* *將* 包含在較長時間間隔（60天、90天和生命週期）返回的結果中。
* *不會* 包含在 [!UICONTROL Last 30 Day] 選項（當前、7天和14天）。

而在第31天，這些訪客只在60天，90天出現 [!UICONTROL Lifetime] 結果。 他們在30天的間隔內過了年。 遊客不會在 [!UICONTROL Lifetime] 間隔。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本節介紹由 [!UICONTROL Addressable Audiences]。

### 客戶級別指標 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些度量返回訪問者訪問您的站點或將入站資料檔案發送到時所實現的特徵的資料 [!DNL Audience Manager]。 這些指標提供了您帳戶的受眾規模的全面視圖。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 已實現A的設備的重疊計數 [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 在回查窗口和設備期間，無論同步時間如何，我們都與所選目標進行ID同步。<br><br>此度量表示以下設備：<ul><li>已經意識到 [!UICONTROL rule-based] 或 [!UICONTROL onboarded trait] 在回顧窗口 `AND`</li><li>與所選的ID同步 [!UICONTROL destination] 不管同步時間。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已實現以下任一項的設備數 [!UICONTROL rule-based trait] 你的財產或 [!UICONTROL onboarded trait] 從離線檔案中刪除。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 段級匹配度量 {#segment-level-metrics}

這些度量返回資料 [!UICONTROL segment] 成員身份。 它們有助於為您的每個用戶提供更精確、更精確的受眾規模視圖 [!UICONTROL segments]。

>[!NOTE]
>
>回顧窗口在 [!UICONTROL segment] 級別與客戶級別不同。 訪問者可以來到該網站，瞭解 [!UICONTROL trait] 10天前，他們有資格 [!UICONTROL segment] 從那時起就退出了 [!UICONTROL segment] 兩天前。 當應用7天回顧時，這些訪問者將被計算在 [!UICONTROL segment] 但不在客戶級別。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 屬於的用戶數 [!UICONTROL segment] 在報告回查期間，並在您的站點上同步活動ID。 資料段可以包括您自己的第一方資料以及第二方和第三方資料， [!UICONTROL traits] 在 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)。<br><br>提示：當與1天回顧時段一起使用時，此度量可幫助您瞭解當前狀態 [!UICONTROL segments]。 這是因為 [!UICONTROL Segment Addressable Audience] 度量表示留在 [!UICONTROL segment] 前一天。 把這和 [!DNL Audience Manager] 刷新 [!UICONTROL Addressable Audiences] 每天，將此度量與回望時段相結合，提供您的最新快照 [!UICONTROL segments]。 |
| [!UICONTROL Total Segment Population] | 屬於您的所有設備的計數 [!UICONTROL segment] 在報告回顧期間。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台級度量 {#platform-level-metrics}

此度量返回所有活動收集的資料 [!DNL Audience Manager] 客戶。 與匯總的客戶相比，它們可以提供更廣的客戶觀點 [!DNL Audience Manager] 客戶。

| 量度 | 說明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 所有與所有設備互動的設備的計數 [!DNL Audience Manager] 在報告回顧期間處於平台級別的客戶，可與您選擇的 [!UICONTROL destination]。 <br><br>此度量很有用，因為它顯示：<ul><li>大小 [!UICONTROL total addressable audience] 那 [!DNL Audience Manager] 可以到達特定的目標。</li><li>多大 [!DNL Audience Manager] 配置檔案池用於目標平台及其受眾的大小。</li></ul> |

## 比較 [!UICONTROL Customer] 和 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不應將 [!UICONTROL Customer Addressable Audience] 和 [!UICONTROL Segment Addressable Audience] 來確定其中一個是否比另一個更重要。 這些是獨立、不同和獨立的度量。 如上述定義所述，每個資料集都是從不同的資料集派生的。 因此，如果一個度量大於另一個度量，則應避免得出任何結論。 在比較這些時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 基於 [!UICONTROL trait] 實現 *你自己的第一方資料*。 此指標提供了與資料合作夥伴整合的全面視圖。

* [!UICONTROL Segment Addressable Audiences] 基於分部資格 *第一方資料，以及第二和第三方資料*。 此度量提供了您的 [!UICONTROL addressable audiences] 瞄準平台。

## 導致匹配率低的原因 [!UICONTROL Addressable Audiences] {#low-match-rates}

造成低的共同因素 [!UICONTROL Addressable Audience] 匹配比率或報告數字中的差異。

| 原因 | 說明 |
|---|---|
| 移動通信 | 最多 [!UICONTROL server-to-server] 整合依賴於第三方協助的同步進程 [!DNL cookies]。 但是，移動環境不使用第三方 [!DNL cookies]。 因此，您 [!UICONTROL Addressable Audiences] 數字與 [!UICONTROL segment] 大小。 <br><br>從2018年1月起，您可以在同一時間激活移動觀眾 [!DNL Google] 和 [!DNL Adobe Advertising Cloud] 目標設定 [!UICONTROL cookie-based] 觀眾。 而這意味著你可以 [!UICONTROL segments] 組合 [!DNL cookie] 和移動ID成員資格 [!DNL Google] 和 [!DNL Advertising Cloud] 目的地，記住 [!UICONTROL Addressable Audiences] 僅顯示 [!DNL cookie] ID和目標。 [!DNL Audience Manager] 將100%的移動觀眾 [!UICONTROL destinations]，但移動觀眾不是由 [!UICONTROL Addressable Audience] 度量。 <br><br>**注釋**:例如， [!UICONTROL segment] 人口100萬。 如果映射此 [!UICONTROL segment] 到 [!DNL Google] 或 [!DNL Adobe Advertising Cloud] 目的地，你可能看到 [!UICONTROL Addressable Audience] 70萬台設備和 [!UICONTROL Match Rate] 百分之七十。 700,000名成員包括 [!DNL cookie] ID與 [!UICONTROL destination]。 您 [!UICONTROL Addressable Audience] 事實上，可能會更高，因為可定址移動ID不會出現在此度量中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 阻止第三方 [!DNL cookies]。 這防止 [!DNL Audience Manager] 將ID與 [!UICONTROL destination]。 隨著 [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)你希望 [!UICONTROL addressable audiences] 不包括 [!DNL Safari] 。 |
| 跟蹤媒體印象 | 由於廣告伺服器最佳實踐，在廣告標籤中不會生成ID同步。 進行大量非現場廣告的客戶將無法將這些環境中的用戶與第三方整合同步。 另外，大量收集的媒體印象資料可以減少 [!UICONTROL addressable audience] 數字。 |

## 故障排除 [!UICONTROL Addressable Audiences] {#troubleshooting}

除曲面匹配率外，還可以使用 [!UICONTROL Addressable Audiences] 作為故障排除工具。

例如，假設您將段發送到 [!UICONTROL destination] 還有 [!UICONTROL destination] 顯示低報告數。 檢查 [!UICONTROL Addressable Audience] 結果將顯示這是技術問題還是匹配率低的情況。 低匹配率顯示 [!UICONTROL destination] 對於選定的段來說並不是那麼好。 然而， [!UICONTROL total addressable audience] 數字 [!DNL Audience Manager] 和 [!UICONTROL destination] 表示整合、同步或其他技術問題。 在這些情況下，請與您的客戶經理聯繫。
