---
description: Audience Marketplace資料購買者同意根據每千個廣告印象(CPM)的成本，來報告資料饋送所提供的所有廣告印象。CPM使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。
seo-description: Audience Marketplace資料購買者同意根據每千個廣告印象(CPM)的成本，來報告資料饋送所提供的所有廣告印象。CPM使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。
seo-title: 資料饋送購買者帳單
solution: Audience Manager
title: 資料饋送購買者帳單
topic: DIL API
uuid: d7236667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] 使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意根據每千個廣告印象([!DNL CPM])基準所支付的成本，報告所提供的所有廣告印象。[!DNL CPM] 使用量會在每個日曆月份的天內到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。

[!UICONTROL Audience Marketplace] 提供兩種報告 [!DNL CPM] 用途的方式：

* **區段層級報告**：這是建議 [!DNL CPM] 的使用報表方法。When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **資料饋送層級報告**：此方法要求您根據CCPM資料饋送 [!DNL CPM][成本歸因中所述的演算法個別報告每個資料饋送的使用量](#cost-attribution)。不過，此方法較麻煩且容易出錯，而非區段層級報告。

## Report CPM Usage at Segment Level {#segment-level-report}

[!UICONTROL Segment Usage] 此標籤可讓您報告區段層級使用情形，同時顯示依對應目的地分組的區段。

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** 前往。
2. Select the **[!UICONTROL Segment Usage]** tab.
3. 填寫區段的使用情形。You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. Click **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.
   ![確認區段使用](assets/confirm-segment-usage.png)
7. Click **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** 前往。
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. Click **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.

   ![確認摘要使用](assets/confirm-feed-usage.png)

7. Click **[!UICONTROL Confirm]**.

## 大量報告

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. 您可以使用大量報告來報告摘要和區段使用情形。

To update [!DNL CPM] usage in bulk:

1. **[!UICONTROL Audience Marketplace > Payables]** 前往。
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. 開啓電腦上的檔案，然後填寫使用報表。
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usation-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 當檔案一上傳，並提示您偵測檔案中的任何錯誤時，就會加以驗證。

### 大量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 無效輸入 | [!DNL Audience Manager] 偵測 [!DNL CSV] 到檔案結構中的變更，例如遺漏欄或欄標題變更。 | 避免變更表格結構。 |
| 找不到 | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| 找到重復的記錄 | [!DNL Audience Manager] 偵測到具有不同曝光值的重復記錄。 | 檢閱報表並確定您不會針對相同資料饋送或區段報告不同的使用值。 |
| 不支援的值 | [!DNL Audience Manager] 已偵測 [!DNL Audience Manager] 到欄中的非數值。 | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| 遺失必填欄位標題 | [!DNL Audience Manager] 偵測到強制欄位遺失表格標題。For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | 檢閱報表並確定表格標題未遭到竄改。 |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] 只會處理報表中包含的欄位。

## [!DNL CPM] 報告最佳實務

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>一律報告印象總數</b> </p> </td> 
   <td colname="col2"> <p>對於CPM曝光總計： </p>
   <p> 報告曝光總數，而不使用小數。Audience Manager會根據您報告的總數自動計算CPM。</p><p>如果您需要報告1,234,567印象，請如實報告。您不需要將曝光總數除以1,000計算CPM。</p><p>使用Adobe Target或Analytics目的地等工具最佳化網頁或應用程式內容(內容最佳化)的特性不會對CPM計劃的「使用量」總計貢獻貢獻。資料供應商通常會使用付費費用計劃獲得內容最佳化的補償。</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅守每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報告系統會在每個月的第五個月之後關閉。如果您未報告CPM使用情況，則必須將該金額新增至下個月的報表。例如，假設您在10月使用了1000印象，錯過10月的報告期限，並在11月使用1000印象。在此情況下，您會報告12月和11月(2000)到12日之間的總計(2000)。</p><p><b>秘訣</b>：您應一律嘗試報告下個月第一個月到第五個月之間的CPM使用情形。</p><p>您最遲可以在新日曆月份的第個時間報告CPM使用，但不建議這麼做。每個月在第五個月前報告CPM使用情形，可讓Audience Manager時間檢查和處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>身為購買者，所有報告的曝光總數必須是真實且正確的。如果您未在每月的第天前報告曝光總數，則必須包含下個月未回報月份的總計。

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

[!UICONTROL Activation] 使用案例可讓您使用對應資料饋送中的特性來建立 [區段產生器](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) 中的區段，並將這些區段對應至目的地。The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. 下表列出如何依布林規則或特徵類型正確分配印象。

>[!TIP]
>[在區段層級](#segment-level-report) 報告CPM使用情形，讓Audience Manager自動完成資料饋送層級報告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則資格邏輯或類型 </th> 
   <th colname="col2" class="entry"> 帳單配送 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或</span> </p> </td> 
   <td colname="col2"> <p>在使用布林OR條件的規則區段中，將傳送的印象總數加權分配給所有提供者特徵。加權配置是使用下列公式計算：</p><p><code>(特徵人口/區段人口量)*印象數* CPM成本</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法區段 </p> </td> 
   <td colname="col2"> <p>將100%的遞送曝光總數套用至包含演算法特徵之區段中的所有提供者摘要。 </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

假設下列情況：

![帳單範例](assets/billing-examples.png)

### 案例1：具有AND資格的區段

此區段包含來自不同資料供應商的個特性。Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

[!UICONTROL AND] 有了條件，您必須將當月收到的印象指派給所有三個資料供應商。[!UICONTROL Audience Marketplace > Payables] 在區段中，您為每個提供者評分1,000,000印象。

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### 案例2：具有OR資格的區段

此區段包含來自不同資料供應商的個特性。Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![帳單區段-或](assets/billing-segment-or.png)

>[!MORE_贊_ this]
>
>* [持平費用資料饋送的計費和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

固定費用資料饋送會每月向您帳單，無論訂閱開始或您使用的印象為何。費用不會計算在部分月份使用或間隔。如同CPM帳單，Adobe會產生發票，並以每月、固定費用費率的方式為您訂閱資料饋送收費。

例如，假設您決定在一個月中開啓動態消息中的某些特性。無論您何時開始訂閱或啓動特定特性，無論您是以每月的價格計費，都還是可以收費。