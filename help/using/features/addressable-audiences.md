---
description: 「可定址對象」功能和使用案例的概述。
keywords: DIL
seo-description: 「可定址對象」功能和使用案例的概述。
seo-title: 可定址對象
solution: Audience Manager
title: 可定址對象
topic: DIL API
uuid: 3eb1335a-6949-452b-b77 a-697c2256 cb3
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Addressable Audience {#addressable-audiences}

「可定址對象」功能和使用案例的概述。

## What is an Addressable Audience? {#addressable-audience-description}

[!UICONTROL Addressable Audiences] 此功能會顯示您在所有屬性中看到的受眾之間重疊的情形，其中 [!DNL Audience Manager] 包括收集資料和您選擇的目的地。為協助您瞭解此概念，請參閱下圖。每個社交圈之間的重疊代表可定址對象的不同類型。

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
   <td colname="col1"> <p> <b>Audience Manager對目的地的可定址對象</b> </p> </td> 
   <td colname="col2"> <p>所有在報表回顧期間與所有Audience Manager客戶互動的裝置，並可與您選擇的目的地相符。 </p> <p>此度量很有用，因為它會顯示您： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager</span> 可觸及特定目標目的地的總定址對象大小。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055"><span class="keyword"> Audience Manager</span> 設定檔存放區的大小，適用於定位平台和受眾規模。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶總觀眾人數</b> </p> </td> 
   <td colname="col2"> <p>在回顧視窗中，已在您的屬性上實現規則型特徵或離線檔案中的已登錄特徵的裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>可定址對象匹配率</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顧視窗和裝置中已實現規則型特徵或已登入特徵的裝置重疊計數，無論同步時間為何，我們都具有ID同步至選擇的目的地。 </p> 
    </draft-comment> <p>此度量代表下列裝置： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">不論同步時間為何，都能與所選目的地同步。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶匹配率</b> </p> </td> 
   <td colname="col2"> <p>客戶可定址對象*「客戶總觀眾」以百分比表示。 </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>區段總人口數</b> </p> </td> 
   <td colname="col2"> <p>報表回顧期間，屬於區段成員之所有裝置的計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段可定址對象</b> </p> </td> 
   <td colname="col2"> <p>在報表回顧期間內，屬於區段且在您的網站上具有作用中ID同步的使用者人數。Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>秘訣：在天回顧期間使用此度量，可協助您瞭解區段的目前狀態。This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段匹配率</b> </p> </td> 
   <td colname="col2"> <p>群體可定址讀者訓練圖總計人口族群總計為%。 </p> </td> 
  </tr>  
 </tbody> 
</table>

## Addressable Audience Interface {#addressable-audience-interface}

[!UICONTROL Addressable Audience] 此功能將此抽象概念轉變為可量化的資料。In [!DNL Audience Manager], this feature displays audience overlap with data visualizations that provide at-a-glance information along with numeric data in tabular form.

[!UICONTROL Addressable Audiences]**[!UICONTROL Audience Data > Destinations]**&#x200B;位於中。Select **[!UICONTROL Integrated Platforms > Device-Based]** to see addressable audiences metrics.

![](assets/addressable-audiences-landing.png)

可在「可定址對象」著陸頁面上看到的三個度量代表：

| 量度 | 說明 |
---------|----------|
| **可定址對象(裝置)** | This metric represents the Customer Addressable Audience (described in the table above) *for the last 30 days.* |
| **匹配比率** | This metric represents the Addressable Audience Match Rate (described in the table above) *for the last 30 days*. |
| **期限可定址對象(裝置)** | 所有在報表回顧期間與所有Audience Manager客戶互動的裝置，並可與此目的地相符。See [Platform-Level Metrics](/help/using/features/addressable-audiences.md#platform-level-metrics) for more information. |

按一下伺服器至伺服器目的地的名稱，即可檢視可定址的觀眾資料。注意，此功能只會傳回伺服器至伺服器目的地的資料，存取權限則需要管理員權限。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測與規劃：**[!UICONTROL Segment Addressable Audience] 資料可為您規劃要傳送至目標群體並啓用的群體，提供更精細的粒度。

* **效能審核：**[!UICONTROL Addressable Audiences] 此功能也是疑難排解工具。它可讓您檢視促銷活動績效、瞭解促銷活動覆蓋範圍，並讓您透過鎖定/啓動合作夥伴進行交叉檢查，如果您看不到預期結果。

### 使用第三方資料進行預測及對匹配比率的影響

在購買觀眾贏取的第三方資料之前，客戶可以驗證與其他資料供應商重疊的情形。這可協助您在購買新資料之前做出明智決策。The ID syncs for purchased third-party data rely not only on the overlap of your data but also on third-party providers’ footprints with all other [!DNL Audience Manager] customers. [!DNL Adobe] 您的顧問可以幫助您識別其他相關資料來源，以最佳化預測促銷活動。

### 行動使用者與匹配率

There are gaps when trying to connect [!DNL Safari] or mobile app users where there are no third-party cookies present. That makes it difficult to sync users with some partners because only those [!DNL Adobe] IDs for synced third-party cookies are provided in the media delivery logs. This is a reason why you might see [low match rates](../features/addressable-audiences.md#low-match-rates) for your destinations.

## Date Ranges in Addressable Audiences and Destinations {#date-ranges}

Read the sections below for available date ranges and how data ages out of each interval in the reports for an [!UICONTROL Addressable Audience] or [!UICONTROL Destination].

## Available Date Ranges and Time Zones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Reports for your [!UICONTROL Addressable Audiences] and [Destinations](../features/destinations/destinations.md) use the same date range intervals. 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此區間會從午夜到前24小時的中間時段執行。它不是即時或目前的度量。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

All dates and date ranges are set in the [!DNL UTC] time zone. See [Time Zones in Audience Manager](../reference/aam-time-zones.md).

## Data in Date Range Intervals {#date-range-intervals}

[!UICONTROL Addressable Audience] 和 [!UICONTROL Destination] 度量會在所選時間間隔內傳回獨特使用者計數。例如，訪客只被計算一次，即使他們多次前來您的網站。第一次瀏覽是唯一瀏覽，並被記錄下來。後續瀏覽會傳回瀏覽，因為它們不是唯一的，所以不會計入。

日期範圍包含所選時間間隔或較舊的資料。此外，每個報表間隔會隨著時間流逝而逾時。For example, let's assume you see 2 visitors after choosing the [!UICONTROL Last 30 Days] option. 在報表中，這些訪客：

* *將* 包含在較長時間間隔(60天、90天和存留期)傳回的結果中。
* *不會* 包含 [!UICONTROL Last 30 Day] 在選項前面的較短間隔中(目前、天和14天)。

And, on day 31, these visitors only show up in the 60 day, 90 day, and [!UICONTROL Lifetime] results. 他們已淘汰30天的間隔。Visitors do not age out of the [!UICONTROL Lifetime] interval.

## Addressable Audience Metrics {#addressable-audience-metrics}

This section describes the types of metrics provided by [!UICONTROL Addressable Audiences].

### Customer-Level Metrics {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

These metrics return data for traits realized when visitors come to your site or when you send inbound data files to [!DNL Audience Manager]. 這些度量可完整檢視您帳戶的對象大小。

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>客戶可定址對象</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>在回顧視窗和裝置中已實現規則型特徵或已登入特徵的裝置重疊計數，無論同步時間為何，我們都具有ID同步至選擇的目的地。 </p> 
    </draft-comment> <p>此度量代表下列裝置： 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Have realized either a rule-based or an onboarded trait during the look-back window <b>AND</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">不論同步時間為何，都能與所選目的地同步。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶總觀眾人數</b> </p> </td> 
   <td colname="col2"> <p>在回顧視窗中，已在您的屬性上實現規則型特徵或離線檔案中的已登錄特徵的裝置計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>客戶匹配率</b> </p> </td> 
   <td colname="col2"> <p>客戶可定址對象*「客戶總觀眾」以百分比表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segment-Level Match Metrics {#segment-level-metrics}

這些量度會傳回區段成員資格的資料。它們可讓您更詳細精確地檢視每個區段的觀眾大小。

>[!NOTE]
>
>在區段層級套用回顧視窗的方式與客戶層級不同。訪客可以進入網站並在10天前實現特徵，而且他們可以自之後取得區段，並在2天前離開區段。套用天回顧時，這些訪客將會計入區段層級，但不會計入客戶層級。

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>區段可定址對象</b> </p> </td> 
   <td colname="col2"> <p>在報表回顧期間內，屬於區段且在您的網站上具有作用中ID同步的使用者人數。Segments can include your own first-party data and second party and third party data, via traits acquired in the <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>秘訣：在天回顧期間使用此度量，可協助您瞭解區段的目前狀態。This is because the <span class="wintitle"> Segment Addressable Audience</span> metric represents the users who stayed in a segment throughout the previous day. Combine this with the fact that <span class="keyword"> Audience Manager</span> refreshes <span class="wintitle"> Addressable Audiences</span> daily, combining this metric and lookback period provides the most up-to-date snapshot of your segments. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段總人口數</b> </p> </td> 
   <td colname="col2"> <p>報表回顧期間，屬於區段成員之所有裝置的計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段匹配率</b> </p> </td> 
   <td colname="col2"> <p>群體可定址讀者訓練圖總計人口族群總計為%。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform-Level Metrics {#platform-level-metrics}

此度量會傳回所有Audience Manager客戶收集之活動的資料。相較於匯總的Audience Manager客戶，他們可以提供更廣泛的客戶觀眾檢視。

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
   <td colname="col2"> <p>所有在報表回顧期間與所有Audience Manager客戶互動的裝置，並可與您選擇的目的地相符。 </p> <p>此度量很有用，因為它會顯示您： </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> <span class="keyword"> Audience Manager</span> 可觸及特定目標目的地的總定址對象大小。 </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055"><span class="keyword"> Audience Manager</span> 設定檔存放區的大小，適用於定位平台和受眾規模。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comparing Customer and Segment Addressable Audiences{#comparing-metrics}

You shouldn't compare the [!UICONTROL Customer Addressable Audience] and [!UICONTROL Segment Addressable Audience] metrics to determine if one is more significant than the other. 這些是不同、不同和獨立量度。如上述定義所述，每一項都衍生自不同的資料集。有鑒於此，如果一個量度大於另一個度量，您應避免嘲笑任何結論。在比較這些問題時，您可以說：

* [!UICONTROL Customer Addressable Audiences] 是根據您自己的第一方資料實作而 **&#x200B;定。此度量可提供廣泛、完整的資料合作夥伴整合檢視。

* [!UICONTROL Segment Addressable Audiences] 是根據您自己第一方資料的區段資格 *，加上第二方和第三方資料*。此度量可提供定位平台中可定址受眾的精細、更精確檢視。

## Causes of Low Match Rates for Addressable Audiences {#low-match-rates}

Common elements responsible for low [!UICONTROL Addressable Audience] match rates or discrepancies in reported numbers.

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
   <td colname="col2"> <p>大部份的伺服器對伺服器整合都依賴於協力廠商Cookie提供的同步程序。不過，行動環境不會使用第三方Cookie。因此，相較於區段大小，您的「可定址對象」數目看起來可能比較低。 </p> <p>自2018年月起，您可以在為Cookie對象設定的相同Google和Adobe Advertising Cloud目的地中啓用行動對象。雖然這表示您可以將結合Cookie和行動ID會籍的區段傳送至您的Google和Advertising Cloud目的地，但請記住，「可定址對象」只會顯示Cookie ID和目的地之間的重疊。Audience Manager會將100%的行動觀眾傳送至目的地，但行動對象不會由「可定址對象」度量測量。 </p> <p> <p><b>注意</b>：例如，假設擁有1,000,000人口的區段。如果您將此區段對應至Google或Adobe Advertising Cloud目的地，您可能會看到700，000部裝置的定址對象，以及70%的匹配率。700，000的成員資格包含與目的地同步的Cookie ID。事實上，您的可定址對象可能會更高，因為可定址的行動ID不會出現在此量度中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari流量</b> </p> </td> 
   <td colname="col2"> <p>Safari封鎖第三方Cookie。如此可防止Audience Manager與目的地同步ID。With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, you can expect your addressable audiences not to include Safari users. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>追蹤媒體印象</b> </p> </td> 
   <td colname="col2"> <p>基於廣告伺服器最佳實務，ID同步不會在廣告標記內進行。大量離站廣告的客戶不會將使用者與這些環境中的協力廠商整合同步。此外，大量收集的媒體曝光資料可降低可定址的對象數目。 </p> </td>
  </tr> 
 </tbody> 
</table>

## Troubleshooting with Addressable Audiences {#troubleshooting}

In addition to surfacing match rates, you can also use [!UICONTROL Addressable Audiences] as a troubleshooting tool.

<!-- addressable-audiences-troubleshooting.xml -->

例如，假設您將區段傳送至目的地，而該目的地顯示的是低報告次數。Checking the [!UICONTROL Addressable Audience] results will show you if this is a technical problem or just a case of low match rates. 低匹配率顯示您的目的地對您選取的區段並非所有絕佳。不過，Audience Manager和目的地之間的可定址人數總計差異，表示整合、同步或其他技術問題。在這種情況下，請連絡您的帳戶管理員。