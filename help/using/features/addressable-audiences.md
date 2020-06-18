---
description: 「可定址對象」功能和使用案例的概述。
keywords: DIL
seo-description: 「可定址對象」功能和使用案例的概述。
seo-title: 可定址受眾
solution: Audience Manager
title: 可定址受眾
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 7%

---


# 可定址對象 {#addressable-audiences}

功能與使 [!UICONTROL Addressable Audience] 用案例的概述。

## 什麼是可定址對象？ {#addressable-audience-description}

此功 [!UICONTROL Addressable Audiences] 能可顯示您在收集資料的所有屬性與所選目的地之間 [!DNL Audience Manager] 的對象重疊。 為協助您瞭解此概念，請檢視下圖。 每個社交圈之間的重疊代表不同類型的可定址觀眾。

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>目標的Audience Manager可定址對象</b> </p> </td> 
   <td colname="col2"> <p>在報告回顧期間，在平台層級與所有Audience Manager客戶互動且可能與您選擇的目的地相符的所有裝置計數。 </p> <p>此量度很有用，因為它顯示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience Manager可在特定目標目標上觸及的可定址對象總 <span class="keyword"> 數</span> 。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager <span class="keyword"></span> 設定檔存放區對於目標平台及其受眾規模而言有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶總受眾</b> </p> </td> 
   <td colname="col2"> <p>在回顧視窗中，已在您的屬性上實現規則型特徵或離線檔案中已載入特徵的裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>可定址對象符合率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顧視窗中，已實現規則型特徵或已登入特徵的裝置與我們已與所選目的地同步的裝置重疊計數，不論同步的時間為何。 </p> 
    </draft-comment> <p>此量度代表下列裝置： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">具有與所選目的地同步的 ID (不論同步的時間為何)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶符合率</b> </p> </td> 
   <td colname="col2"> <p>客戶可定址的受眾 ÷ 客戶總受眾，以 % 表示。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>區段總人口</b> </p> </td> 
   <td colname="col2"> <p>報表回顧期間，屬於您區段成員的所有裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段可定址的受眾</b> </p> </td> 
   <td colname="col2"> <p>在報表回顧期間屬於區段並在您的網站上同步作用中ID的使用者人數。 區段可以透過在 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md">Audience Marketplace</a> 中取得的特徵，包含您自己的第一方資料、第二方資料和第三方資料。 </p> <p> <p>提示： 當與1天回顧期間搭配使用時，此度量可協助您瞭解區段的目前狀態。 這是因為「區 <span class="wintitle"> 段可定址對象</span> 」量度代表在前一天一直留在區段中的使用者。 結合此點與 <span class="keyword"> Audience Manager每天重新整理</span><span class="wintitle"></span> 「可定址對象」的事實，結合此度量和回顧期間可提供區段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段符合率</b> </p> </td> 
   <td colname="col2"> <p>區段可定址的受眾 ÷ 區段總母體，以 % 表示。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## 可定址觀眾介面 {#addressable-audience-interface}

這個 [!UICONTROL Addressable Audience] 功能將這個抽象概念轉化為可量化的資料。 在此 [!DNL Audience Manager]功能中，此功能會顯示觀眾與資料視覺化的重疊，這些視覺化可提供一目瞭然的資訊，以及表格格式的數值資料。

[!UICONTROL Addressable Audiences] 的子菜單 **[!UICONTROL Audience Data > Destinations]**。 選取 **[!UICONTROL Integrated Platforms > Device-Based]** 以查看可定址的觀眾量度。

![](assets/addressable-audiences-landing.png)

您可在登陸頁面上看到的三個 [!UICONTROL Addressable Audiences] 度量代表：

| 量度 | 說明 |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度代表 [!UICONTROL Customer Addressable Audience] 過去30天(如上 *表所述)。* |
| **[!UICONTROL Match Rate]** | 此量度代 [!UICONTROL Addressable Audience Match Rate] 表過去30天 *的量度*。 |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 在報告回顧期間與平台層級所有 [!DNL Audience Manager] 客戶互動且可能與此目標相符的所有裝置計數。 如需 [詳細資訊，請參閱平台層](/help/using/features/addressable-audiences.md#platform-level-metrics) 級量度。 |

按一下伺服器對伺服器目的地的名稱，以檢視可定址的觀眾資料。 請注意，此功能僅會傳回伺服器對伺服器目的地的資料，而且存取需要管理員權限。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測和規劃：** [!UICONTROL Segment Addressable Audience] 資料可讓您更精細地瞭解您打算傳送至目的地的細分，以利鎖定受眾並啟動受眾。

* **效能評論：** 此功 [!UICONTROL Addressable Audiences] 能也是疑難排解工具。 它可讓您檢視促銷活動成效、瞭解促銷活動觸及面，並讓您在看不到預期結果時，與目標／啟動合作夥伴進行交叉檢查。

### 使用第三方資料進行預測及對匹配率的影響

在購買協力廠商資料以贏取觀眾之前，客戶可以驗證與其他資料供應商的重疊。 這可協助您在購買新資料之前，做出明智的決策。 購買之協力廠商資料的ID同步不僅取決於您資料的重疊，還取決於協力廠商與所有其他客戶的 [!DNL Audience Manager] 足跡。 您的 [!DNL Adobe] 顧問可協助您找出其他相關資料來源，以最佳化客源開發活動。

### 行動使用者與比對率

嘗試連線或行動應用程 [!DNL Safari] 式使用者時，沒有第三方Cookie時會有差距。 因此，很難將使用者與某些合作夥伴同步，因為媒體傳送記錄中只提供同步的 [!DNL Adobe] 協力廠商Cookie的ID。 這就是為什麼您可能會發現目 [的地的匹配率](../features/addressable-audiences.md#low-match-rates) 很低。

## 可定址對象和目標中的日期範圍 {#date-ranges}

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

## 可定址對象量度 {#addressable-audience-metrics}

本節說明由提供的量度類型 [!UICONTROL Addressable Audiences]。

### 客戶層級量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客來到您的網站時，或您傳送傳入資料檔案時所發現之特徵的資料 [!DNL Audience Manager]。 這些量度可提供您帳戶的受眾規模完整檢視。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>客戶可定址的受眾</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顧視窗中，已實現規則型特徵或已登入特徵的裝置與我們已與所選目的地同步的裝置重疊計數，不論同步的時間為何。 </p> 
    </draft-comment> <p>此量度代表下列裝置： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">具有與所選目的地同步的 ID (不論同步的時間為何)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶總受眾</b> </p> </td> 
   <td colname="col2"> <p>在回顧視窗中，已在您的屬性上實現規則型特徵或離線檔案中已載入特徵的裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶符合率</b> </p> </td> 
   <td colname="col2"> <p>客戶可定址的受眾 ÷ 客戶總受眾，以 % 表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 區段層級符合量度 {#segment-level-metrics}

這些量度會傳回區段成員資格的資料。 它們可協助您更精細、更精確地檢視每個區段的受眾規模。

>[!NOTE]
>
>回顧視窗在區段層級的套用方式與在客戶層級的套用方式不同。 訪客可在10天前來到網站並瞭解某個特徵，而且自此可符合區段資格，並於2天前退出區段。 套用7天回顧時，這些訪客會計入區段層級，但不會計入客戶層級。

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>區段可定址的受眾</b> </p> </td> 
   <td colname="col2"> <p>在報表回顧期間屬於區段並在您的網站上同步作用中ID的使用者人數。 區段可以透過在 <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md">Audience Marketplace</a> 中取得的特徵，包含您自己的第一方資料、第二方資料和第三方資料。 </p> <p> <p>提示： 當與1天回顧期間搭配使用時，此度量可協助您瞭解區段的目前狀態。 這是因為「區 <span class="wintitle"> 段可定址對象</span> 」量度代表在前一天一直留在區段中的使用者。 結合此點與 <span class="keyword"> Audience Manager每天重新整理</span><span class="wintitle"></span> 「可定址對象」的事實，結合此度量和回顧期間可提供區段的最新快照。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段總人口</b> </p> </td> 
   <td colname="col2"> <p>報表回顧期間，屬於您區段成員的所有裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段符合率</b> </p> </td> 
   <td colname="col2"> <p>區段可定址的受眾 ÷ 區段總母體，以 % 表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 平台層級量度 {#platform-level-metrics}

此度量會傳回所有客戶所收集之活動的 [!DNL Audience Manager] 資料。 相較於整合的客戶，他們可以提供更廣泛的客戶觀 [!DNL Audience Manager] 眾。

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager的可定址對象</b> </p> </td> 
   <td colname="col2"> <p>在報告回顧期間，在平台層級與所有Audience Manager客戶互動且可能與您選擇的目的地相符的所有裝置計數。 </p> <p>此量度很有用，因為它顯示： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Audience Manager可在特定目標目標上觸及的可定址對象總 <span class="keyword"> 數</span> 。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Audience Manager <span class="keyword"></span> 設定檔存放區對於目標平台及其受眾規模而言有多大。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 比較客戶和區段可定址對象{#comparing-metrics}

您不應比較度量 [!UICONTROL Customer Addressable Audience] 和度 [!UICONTROL Segment Addressable Audience] 量，以判斷其中一個比另一個更重要。 這些是個別、不同和獨立的度量。 如上述定義所述，每個定義都源自不同的資料集。 因此，如果一個量度大於另一個量度，您應避免得出任何結論。 在比較這些時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 是以您自己的第 *一方資料的特性實現為基礎*。 此量度可提供您與資料合作夥伴整合的廣泛、完整檢視。

* [!UICONTROL Segment Addressable Audiences] 是以您自己第一 *方資料的區段資格，加上第二方及第三方資料為基礎*。 此量度可提供定位平台中可定址對象的精細、更精確檢視。

## 可定址對象匹配率低的原因 {#low-match-rates}

導致匹配率低或報告 [!UICONTROL Addressable Audience] 數字不一致的常見元素。

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>行動流量</b> </p> </td> 
   <td colname="col2"> <p>大部份的伺服器對伺服器整合都仰賴協力廠商Cookie所促成的同步程式。 不過，行動環境不會使用協力廠商Cookie。 因此，與區段大小相比，您的「可定址對象」數目看起來可能較低。 </p> <p>自2018年1月起，您可以在為Cookie型觀眾設定的相同Google和Adobe Advertising Cloud目的地中啟用行動觀眾。 雖然這表示您可以將結合了Cookie和行動ID會籍的區段傳送至您的Google和Advertising Cloud目標，但請記住「可定址對象」只會顯示Cookie ID和目標之間的重疊。 Audience Manager會傳送100%的行動對象至目標，但行動對象不會由「可定址對象」量度測量。 </p> <p> <p><b>注意</b>:  例如，以人口為1,000,000的區段為例。 如果您將此區段對應至Google或Adobe Advertising Cloud目標，您可能會看到700,000個裝置的可定址對象和70%的比對率。 700,000個會籍包含Cookie ID，這些ID與目標同步。 實際上，您的可定址對象可能會更高，因為可定址行動ID不會顯示在此量度中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari流量</b> </p> </td> 
   <td colname="col2"> <p>Safari會封鎖協力廠商Cookie。 這可防止Audience Manager將ID與目標同步。 隨著 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0的推出</a>，您可以預期可找對象不會包含Safari使用者。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>追蹤的媒體曝光</b> </p> </td> 
   <td colname="col2"> <p>由於廣告伺服器的最佳實務，廣告標籤中不會進行ID同步。 大量進行離站廣告的客戶將不會將使用者同步到這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可能會減少可定址的受眾數量。 </p> </td>
  </tr> 
 </tbody> 
</table>

## 可定址對象疑難排解 {#troubleshooting}

除了曲面匹配率外，還可以將其用作 [!UICONTROL Addressable Audiences] 故障排除工具。

<!-- addressable-audiences-troubleshooting.xml -->

例如，假設您傳送區段至目標，而該目標顯示低報告數。 檢查結 [!UICONTROL Addressable Audience] 果會顯示這是技術問題，還是只是低比對率的問題。 低比對率顯示您的目的地對您選取的區段並不太適合。 但是，目標與目標之間可定址讀者總數的差 [!DNL Audience Manager] 異表示整合、同步或其他技術問題。 在這些情況下，請連絡您的客戶經理。