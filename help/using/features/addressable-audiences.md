---
description: 「可定址對象」功能與使用案例的概觀。
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: 可定址對象
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

[!UICONTROL Addressable Audience]功能和使用案例的概觀。

## 什麼是[!UICONTROL Addressable Audience]？ {#addressable-audience-description}

[!UICONTROL Addressable Audiences]功能會顯示您在[!DNL Audience Manager]收集資料的所有屬性中看到的對象與您選取的目的地之間的重疊。 為協助您瞭解此概念，請參閱下圖。 每個圓圈之間的重疊代表不同型別的可定址對象。

![](assets/addressableAudienceVenn.png)


| 量度 | 說明 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience]的[!UICONTROL Destination] | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與您選擇的[!UICONTROL destination]相符的所有裝置計數。 <br><br>此量度非常有用，因為它會顯示： <ul><li>[!UICONTROL addressable audience]在特定目標[!DNL Audience Manager]上可觸及的總[!UICONTROL destination]的大小。</li><li>目標平台的[!DNL Audience Manager]設定檔集區以及其對象的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧期間，已在您的屬性上實現[!UICONTROL rule-based trait]或從離線檔案中實現[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Customer Addressable Audience] | 在回顧期間已實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置，以及我們與所選[!UICONTROL destination]具有ID同步的裝置的重疊計數（不論同步的時間為何）。<br><br>此量度代表具備下列條件的裝置：<ul><li>已在回顧期間[!UICONTROL rule-based]實現[!UICONTROL onboarded trait]或`AND`</li><li>具有與所選[!UICONTROL destination]同步的ID （不論同步的時間為何）。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]÷[!UICONTROL Customer Total Audience]以百分比表示。 |
| [!UICONTROL Total Segment Population] | 報表回顧期間屬於[!UICONTROL segment]成員的所有裝置計數。 |
| [!UICONTROL Segment Addressable Audience] | 在報表回顧期間屬於[!UICONTROL segment]且在您的網站上具有同步作用中ID的使用者數目。 [!UICONTROL Segments]可以透過在[!UICONTROL traits]Audience Marketplace[中取得的](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，包含您自己的第一方資料以及第二方和第三方資料。 <br><br>提示：搭配1天回顧期間使用時，此量度可協助您瞭解[!UICONTROL segments]的目前狀態。 這是因為[!UICONTROL Segment Addressable Audience]量度代表前一天留在[!UICONTROL segment]中的使用者。 結合[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實，結合此量度和回顧期間可提供您[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]÷[!UICONTROL Total Segment Population]以百分比表示。 |

## [!UICONTROL Addressable Audiences]介面 {#addressable-audience-interface}

[!UICONTROL Addressable Audience]功能將此抽象概念變成可量化的資料。 在[!DNL Audience Manager]中，此功能顯示與資料視覺效果重疊的受眾，這些視覺效果提供一目瞭然的資訊以及表格形式的數值資料。

[!UICONTROL Addressable Audiences]位於&#x200B;**[!UICONTROL Audience Data > Destinations]**。 選取&#x200B;**[!UICONTROL Integrated Platforms > Device-Based]**&#x200B;以檢視可定址對象量度。

![](assets/addressable-audiences-landing.png)

您可以在[!UICONTROL Addressable Audiences]登陸頁面上看到的三個量度代表：

| 量度 | 說明 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度代表過去30天的[!UICONTROL Customer Addressable Audience] （如上表所述） *。* |
| **[!UICONTROL Match Rate]** | 此量度代表過去30天[!UICONTROL Addressable Audience Match Rate]的&#x200B;*（如上表所述）*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與此[!UICONTROL destination]相符的所有裝置計數。 如需詳細資訊，請參閱[平台層級量度](/help/using/features/addressable-audiences.md#platform-level-metrics)。 |

按一下[!UICONTROL server-to-server destination]的名稱以檢視可定址對象資料。 請注意，此功能只會傳回[!UICONTROL server-to-server destinations]的資料，而且存取需要系統管理員許可權。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測與規劃：** [!UICONTROL Segment Addressable Audience]資料可讓您對要傳送至目的地以進行對象目標定位與啟用的區段，進行更精細的劃分。

* **效能評論：** [!UICONTROL Addressable Audiences]功能也是疑難排解工具。 它可讓您檢閱行銷活動績效、瞭解行銷活動觸及率，並讓您在沒有看到預期結果時與鎖定目標/啟用合作夥伴進行交叉檢查。

### 使用第三方資料進行勘探，以及對匹配率的關聯

在購買第三方資料以進行受眾贏取之前，客戶可以驗證與其他資料提供者的重疊。 這可協助您在購買新資料之前做出明智的決定。 所購買協力廠商資料的ID同步不僅取決於您的資料重疊，還取決於協力廠商提供者與所有其他[!DNL Audience Manager]客戶的足跡。 您的[!DNL Adobe]顧問可協助您識別其他相關資料來源，以最佳化潛在客戶促銷活動。

### 行動使用者和匹配率

嘗試連線[!DNL Safari]或沒有第三方[!DNL cookies]的行動應用程式使用者時，發生間隙。 這會導致難以與某些合作夥伴同步使用者，因為媒體傳遞記錄中只提供已同步第三方[!DNL Adobe]的[!DNL cookies] ID。 這就是您可能會看到[有](../features/addressable-audiences.md#low-match-rates)低符合率[!UICONTROL destinations]的原因。

## [!UICONTROL Addressable Audiences]和[!UICONTROL Destinations]中的日期範圍 {#date-ranges}

請閱讀以下各節，以瞭解可用的日期範圍，以及[!UICONTROL Addressable Audience]或[!UICONTROL Destination]的資料在報表中如何超過每個間隔。

## 可用的日期範圍和時區 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您[!UICONTROL Addressable Audiences]和[目的地](../features/destinations/destinations.md)的報告使用相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔會從前24小時的午夜執行至午夜。 這不是即時或目前的量度。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍皆設定在[!DNL UTC]時區。 請參閱Audience Manager[中的](../reference/aam-time-zones.md)時區。

## 日期範圍間隔中的資料 {#date-range-intervals}

[!UICONTROL Addressable Audience]與[!UICONTROL Destination]量度會傳回所選時間間隔內的不重複使用者計數。 例如，即使訪客多次造訪您的網站，也只會計數一次。 第一次造訪是不重複造訪，且會進行記錄。 後續的造訪會為回訪，且不會計入，因為這些造訪並非為唯一。

日期範圍包含所選時間間隔或更早時間的資料。 而且，資料會隨著時間流逝而老化超過每個報表間隔。 例如，假設您選擇[!UICONTROL Last 30 Days]選項後看到2位訪客。 在報表中，這些訪客：

* *將包含在較長的時間間隔（60天、90天和存留期）傳回的結果中*。
* *不會包含在*&#x200B;選項（目前、7天和14天）之前的較短間隔中的[!UICONTROL Last 30 Day]。

而且在第31天，這些訪客只會在60天、90天和[!UICONTROL Lifetime]個結果中出現。 他們已超過30天的間隔。 訪客不會超過[!UICONTROL Lifetime]間隔。

## [!UICONTROL Addressable Audiences]個量度 {#addressable-audience-metrics}

本節說明[!UICONTROL Addressable Audiences]所提供的度量型別。

### 客戶層級量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客造訪您的網站或您將傳入資料檔案傳送至[!DNL Audience Manager]時所實現之特徵的資料。 這些量度可全面檢視您帳戶的對象規模。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 在回顧期間實現[!UICONTROL rule-based trait]或[!UICONTROL onboarded trait]的裝置以及我們與所選目的地具有ID同步的裝置（不論同步的時間為何）的重疊計數。<br><br>此量度代表具備下列條件的裝置：<ul><li>已在回顧期間[!UICONTROL rule-based]實現[!UICONTROL onboarded trait]或`AND`</li><li>具有與所選[!UICONTROL destination]同步的ID （不論同步的時間為何）。</li></ul> |
| [!UICONTROL Customer Total Audience] | 在回顧期間，已在您的屬性上實現[!UICONTROL rule-based trait]或從離線檔案中實現[!UICONTROL onboarded trait]的裝置計數。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]÷[!UICONTROL Customer Total Audience]以百分比表示。 |

### 區段層級比對量度 {#segment-level-metrics}

這些量度會傳回[!UICONTROL segment]成員資格的資料。 它們有助於提供每個[!UICONTROL segments]的更細微且精確的對象人數檢視。

>[!NOTE]
>
>在[!UICONTROL segment]層級套用回顧期間的方式與客戶層級不同。 訪客可在10天前造訪網站並實現[!UICONTROL trait]，且在此後可符合[!UICONTROL segment]的資格，並在[!UICONTROL segment] 2天前退出。 套用7天回顧時，這些訪客將在[!UICONTROL segment]層級計算，但不會計入客戶層級。

| 量度 | 說明 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 在報表回顧期間屬於[!UICONTROL segment]且在您的網站上具有同步作用中ID的使用者數目。 區段可以透過在[!UICONTROL traits]Audience Marketplace[中取得的](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，包含您自己的第一方資料、第二方資料和第三方資料。<br><br>提示：搭配1天回顧期間使用時，此量度可協助您瞭解[!UICONTROL segments]的目前狀態。 這是因為[!UICONTROL Segment Addressable Audience]量度代表前一天留在[!UICONTROL segment]中的使用者。 結合[!DNL Audience Manager]每天重新整理[!UICONTROL Addressable Audiences]的事實，結合此量度和回顧期間可提供您[!UICONTROL segments]的最新快照。 |
| [!UICONTROL Total Segment Population] | 報表回顧期間屬於[!UICONTROL segment]成員的所有裝置計數。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]÷[!UICONTROL Total Segment Population]以百分比表示。 |

### 平台層級量度 {#platform-level-metrics}

此量度會傳回所有[!DNL Audience Manager]客戶所收集之活動的資料。 與彙總的[!DNL Audience Manager]客戶相比，他們可以提供更廣闊的客戶對象檢視。

| 量度 | 說明 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 在報告回顧期間與平台層級的所有[!DNL Audience Manager]客戶互動且可能與您選擇的[!UICONTROL destination]相符的所有裝置計數。 <br><br>此量度非常有用，因為它會顯示：<ul><li>[!UICONTROL total addressable audience]可以到達特定目標定位目的地的[!DNL Audience Manager]大小。</li><li>目標平台的[!DNL Audience Manager]設定檔集區以及其對象的大小。</li></ul> |

## 比較[!UICONTROL Customer]與[!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

您不應比較[!UICONTROL Customer Addressable Audience]與[!UICONTROL Segment Addressable Audience]量度，以判斷其中一個量度是否比另一個量度更重要。 這些量度是不同的、不同的和獨立的量度。 如上述定義所述，這些資料都是從不同的資料集衍生而來。 有鑑於此，如果某個量度大於另一個量度，則應避免得出任何結論。 比較這些時，您只能說：

* [!UICONTROL Customer Addressable Audiences]是以您自己的第一方資料[!UICONTROL trait]的&#x200B;*實現*&#x200B;為基礎。 此量度提供您與資料合作夥伴整合的廣泛、完整檢視。

* [!UICONTROL Segment Addressable Audiences]是以您自己的第一方資料，加上第二方和第三方資料&#x200B;*的區段資格*&#x200B;為基礎。 此量度可讓您在目標定位平台上更精細、更準確地檢視您的[!UICONTROL addressable audiences]。

## [!UICONTROL Addressable Audiences]低符合率的成因 {#low-match-rates}

造成低[!UICONTROL Addressable Audience]匹配率或報告數字差異的通用元素。

| 原因 | 說明 |
|---|---|
| 行動流量 | 大多數[!UICONTROL server-to-server]整合依賴協力廠商[!DNL cookies]所協助的同步化程式。 不過，行動環境不使用第三方[!DNL cookies]。 因此，您的[!UICONTROL Addressable Audiences]數字與[!UICONTROL segment]大小相比可能顯得太低。 <br><br>自2018年1月起，您可以在為[!DNL Google]受眾設定的相同[!DNL Adobe Advertising Cloud]和[!UICONTROL cookie-based]目的地中啟用行動受眾。 雖然這表示您可以連同結合的[!UICONTROL segments]和行動識別碼成員資格將[!DNL cookie]傳送至您的[!DNL Google]和[!DNL Advertising Cloud]目的地，但請注意，[!UICONTROL Addressable Audiences]只會顯示[!DNL cookie] ID和目的地之間的重疊。 [!DNL Audience Manager]將100%的行動對象傳送至[!UICONTROL destinations]，但行動對象並非由[!UICONTROL Addressable Audience]量度測量。 <br><br>**附註**：例如，以1,000,000為母體的[!UICONTROL segment]為例。 如果您將此[!UICONTROL segment]對應至[!DNL Google]或[!DNL Adobe Advertising Cloud]目的地，您可能會看到700,000部裝置中的[!UICONTROL Addressable Audience]部和70%的[!UICONTROL Match Rate]部。 700,000的成員資格由[!DNL cookie]個ID組成，這些ID與[!UICONTROL destination]同步。 事實上，您的[!UICONTROL Addressable Audience]可能更高，因為可定址行動ID不會出現在此量度中。 |
| [!DNL Safari]流量 | [!DNL Safari]封鎖第三方[!DNL cookies]。 這可防止[!DNL Audience Manager]與[!UICONTROL destination]同步ID。 隨著[ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)的推出，您可以預期您的[!UICONTROL addressable audiences]不會包含[!DNL Safari]位使用者。 |
| 已追蹤的媒體曝光數 | 由於廣告伺服器最佳實務的緣故，系統不會在廣告標籤中進行ID同步。 進行大量站外廣告的客戶不會將使用者同步到這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可能會減少[!UICONTROL addressable audience]個數字。 |

## 疑難排解[!UICONTROL Addressable Audiences] {#troubleshooting}

除了呈現符合率，您也可以使用[!UICONTROL Addressable Audiences]作為疑難排解工具。

例如，假設您傳送區段至[!UICONTROL destination]，且[!UICONTROL destination]顯示低報告數字。 檢查[!UICONTROL Addressable Audience]結果將顯示這是技術問題，還是匹配率偏低。 低符合率顯示您的[!UICONTROL destination]對您選取的區段來說並不完美。 但是，[!UICONTROL total addressable audience]與[!DNL Audience Manager]之間的[!UICONTROL destination]數字差異表示整合、同步或其他技術問題。 在這些情況下，請聯絡您的客戶經理。
