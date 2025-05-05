---
description: Audience Marketplace資料購買者同意報告所有使用資料摘要中所含特徵提供的廣告曝光次數，這些特徵是以每千次廣告曝光次數(CPM)的成本定價。 CPM使用量會在每個日曆月的第5天到期，並包含前個月的資料。 固定費用訂閱者不需要報告使用量。
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: 資料摘要購買者的計費方式
keywords: 區段層級報告、區段層級、區段層級
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# 資料摘要購買者的計費方式 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意報告所有使用資料摘要中所含特徵提供的廣告曝光次數，這些特徵是以每千次廣告曝光次數([!DNL CPM])的成本定價。 [!DNL CPM]使用量會在每個行事曆月的5日到期，並包含前個月的資料。 固定費用訂閱者不需要報告使用量。

<br> 

## 如何報告CPM使用量 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace]資料購買者同意報告所有使用資料摘要中所含特徵提供的廣告曝光次數，這些特徵是以每千次廣告曝光次數([!DNL CPM])的成本定價。 [!DNL CPM]使用量會在每個日曆月的5日到期，並包含上個月的資料。 固定費用訂閱者不需要報告使用量。

[!UICONTROL Audience Marketplace]提供兩種報告[!DNL CPM]使用狀況的方式：

* **區段層級報告**：這是建議的[!DNL CPM]使用情況報告方法。 當您在區段層級報告[!DNL CPM]使用量時，資料摘要層級報告區段會自動根據[CPM資料摘要的成本歸因](#cost-attribution)中所述的演演算法，填入對應的使用量金額。
* **資料摘要層級報告**：此方法需要您根據[CPM資料摘要的成本歸因](#cost-attribution)中所述的演演算法，個別報告每個資料摘要的[!DNL CPM]使用量。 不過，這種方法比區段層級報告更冗長且容易出錯。

<br> 

## 報告區段層級的CPM使用量 {#segment-level-report}

[!UICONTROL Segment Usage]索引標籤可讓您報告區段層級使用量，同時顯示依對應目的地分組的區段。

在報告區段層級的[!DNL CPM]使用量後，[!UICONTROL Audience Marketplace]會根據CPM資料摘要的[成本歸因](#cost-attribution)，自動指派對應的資料摘要正確使用量。

若要報告區段層級的[!DNL CPM]使用量：

1. 移至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 選取&#x200B;**[!UICONTROL Segment Usage]**&#x200B;標籤。
1. 填寫區段的使用情況。 如果您只需要報告部分割槽段的使用情況，則可以使用[!UICONTROL Search]方塊來篩選區段。
1. 按一下 **[!UICONTROL Edit Segments Usage]**。
1. 在[!UICONTROL Usage]欄中輸入[!DNL CPM]使用量。
1. 完成時按一下&#x200B;**[!UICONTROL Save]**&#x200B;並檢閱確認對話方塊。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 按一下 **[!UICONTROL Confirm]**。

另請觀看我們的影片示範，瞭解如何報告區段層級的使用情況：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 在資料摘要層級報告CPM使用量 {#feed-level-report}

資料摘要層級報告比較繁瑣，而且容易發生錯誤程式，因為您必須個別計算每個資料摘要的[!DNL CPM]使用量。 建議您改為[報告區段層級](#segment-level-report)的CPM使用量。

若要報告區段層級的[!DNL CPM]使用量：

1. 移至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
2. 選取&#x200B;**[!UICONTROL Feed Usage]**&#x200B;標籤。
3. 使用[!UICONTROL Search]方塊來篩選資料摘要，並識別您需要報告使用情況的資料摘要。
4. 按一下 **[!UICONTROL Edit Feeds Usage]**。
5. 根據CPM資料摘要[&#128279;](#cost-attribution)的成本歸因，計算每個資料摘要的[!DNL CPM]使用量，並在[!UICONTROL Usage]欄中輸入。
6. 完成時按一下&#x200B;**[!UICONTROL Save]**&#x200B;並檢閱確認對話方塊。

   ![confirm-feed-use](assets/confirm-feed-usage.png)

7. 按一下 **[!UICONTROL Confirm]**。

<br> 

## 大量報告

若要減少報告[!DNL CPM]使用量時的錯誤和額外負荷，您可以使用大量報告選項來下載包含資料摘要和區段的[!DNL CSV]檔案、填寫使用量，然後將其上傳回[!DNL Audience Manager]。 您可以使用大量報告來報告摘要和區段使用情況。

若要大量更新[!DNL CPM]使用量：

1. 移至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 根據您要更新的報告型別，選取&#x200B;**[!UICONTROL Feed Usage]**&#x200B;或&#x200B;**[!UICONTROL Segment Usage]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Edit Feeds Usage]**&#x200B;或&#x200B;**[!UICONTROL Edit Segments Usage]**。
1. 按一下&#x200B;**[!UICONTROL download the current usage]**&#x200B;以確定您使用有效的CSV檔案。
1. 開啟電腦上的檔案，並填入使用情況報表。
1. 按一下&#x200B;**[!UICONTROL Choose a CSV file]**&#x200B;以上傳更新的使用量報告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager]會在您上傳檔案後立即驗證該檔案，並在偵測到檔案中是否有任何錯誤時提示您。

<br> 

### 大量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 無效的輸入 | [!DNL Audience Manager]在[!DNL CSV]檔案結構描述中偵測到變更，例如遺漏欄或變更欄標題。 | 避免變更表格結構。 |
| 找不到 | 針對[!UICONTROL Segment Level Reporting]，[!DNL Audience Manager]無法識別[!UICONTROL Segment ID]與[!UICONTROL Destination ID]組合。 針對[!UICONTROL Feed Level Reporting]，[!DNL Audience Manager]無法識別[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]組合。 | 針對[!UICONTROL Segment Level Reporting]，檢查[!UICONTROL Segment ID]與[!UICONTROL Destination ID]組合是否有效。 針對[!UICONTROL Feed Level Reporting]，檢查[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]及[!UICONTROL Use Case]組合是否有效。 |
| 找到重複的記錄 | [!DNL Audience Manager]偵測到具有不同曝光值的重複記錄。 | 請檢閱報表，並確認您沒有針對相同的資料摘要或區段報告不同的使用量值。 |
| 不支援的值 | [!DNL Audience Manager]在[!DNL Audience Manager]欄中偵測到非數值。 | 檢閱報告，並確定您只在[!DNL Audience Manager]欄中輸入數值。 |
| 必填欄位的標題遺失 | [!DNL Audience Manager]偵測到必要欄位遺漏資料表標題。 [!UICONTROL Segment Level Reporting]的必要欄位為： [!UICONTROL Segment ID]、[!UICONTROL Destination ID]。 [!UICONTROL Feed Level Reporting]的必要欄位為： [!UICONTROL Data Provider Name]、[!UICONTROL Data Feed Name]、[!UICONTROL Use Case] | 檢閱報告，並確認表格標題未遭竄改。 |

>[!NOTE]
>從[!DNL CSV]使用量報告中移除資料列對現有使用量報告沒有任何影響。 [!DNL Audience Manager]僅處理報告中包含的欄位。

<br> 

## [!DNL CPM]報告最佳實務

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>一律報告曝光總數</b> </p> </td> 
   <td colname="col2"> <p>針對CPM曝光總數： </p>
   <p> 報告曝光總數，但不使用小數。 Audience Manager會根據您報告的總數自動計算CPM。</p><p>如果您需要報告1,234,567次曝光數，請如實報告。 您不需要將曝光總數除以1,000即可計算CPM。</p><p>用來使用Adobe Target或Analytics目的地等工具最佳化您的網頁或應用程式內容（內容最佳化）的特徵，不會貢獻CPM計畫的使用量總計。 資料提供者通常會使用固定費用計畫獲得「內容最佳化」的補償。</p><p>如需詳細資訊，請參閱<a href="#cost-attribution">CPM資料摘要的成本歸因</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅持每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報表系統會在每月5日之後關閉。 如果您未能在此日期之前回報CPM使用量，則須將該金額新增至下一月的報表中。 例如，假設您在10月使用1000次曝光、錯過10月的報告截止日期，並在11月使用1000次曝光。 在此案例中，您會在12月報告10月和11月總計(2000) （介於1日與5日之間）。</p><p><b>提示</b>：您應該一律報告下個月第1天和第5天之間的上一個月CPM使用量。</p><p>您可以在新的日曆月的第5日報告CPM使用量，但不建議這麼做。 在每月5日前報告CPM使用量，可讓Audience Manager有時間檢查及處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## cpm資料摘要的成本歸因 {#cost-attribution}

在[!UICONTROL Audience Marketplace]中，您必須針對每個區段每月自行報告曝光金額。 我們建議在區段層級報告[!DNL CPM]的使用量，以便自動完成成本歸因。

<!-- marketplace_cpm_billing.xml -->

### 帳單摘要 {#billing-summary}

您必須在每個日曆月的第1天和第5天之間提交[!DNL CPM]個資料摘要曝光金額。 若要正確執行此動作，我們建議您[報告區段層級](#segment-level-report)的CPM使用量。

>[!TIP]
>當您在區段層級報告[!DNL CPM]的使用量時，資料摘要層級報告區段會自動填入對應的使用量金額。

若您需要[!UICONTROL Report CPM Usage at Data Feed Level]，您必須個別編譯每個摘要在上一個日曆月傳送的所有曝光數，並根據本文所述的計費配置進行報告。

在您針對上個日曆月彙報[!DNL CPM]個數字後，[!DNL Adobe]將執行下列動作：

* 根據每個已訂閱資料摘要的[!DNL CPM]費率建立商業發票並開立帳單。
* 根據您報告的[!DNL CPM]使用支付資料提供者（賣家）所缺費用。

>[!IMPORTANT]
>
>身為購買者，所有回報的曝光總計都必須為真實且準確。 如果您未依每個月的第5天報告曝光總數，則必須包含下個月未報告月份的總數。

<br> 

## 根據特徵資格規則在摘要層級指派曝光 {#assign-impressions}

[!UICONTROL Activation]使用案例可讓您在對應的資料摘要中使用特徵，在[區段產生器](../../../features/segments/segment-builder.md)中建立區段，並將這些區段對應至目的地。 布林運運算元[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]可讓您設定特徵和區段資格條件。

當您[在資料摘要層級](#feed-level-report)報告CPM使用情形時，您必須根據特徵資格規則中使用的[!DNL Boolean]運運算元，按比例為每個資料摘要分配曝光數。 下表列出如何依布林值規則或特徵型別正確分配曝光次數。

>[!TIP]
>[在區段層級](#segment-level-report)報告CPM使用量，以便Audience Manager自動完成資料摘要層級報告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則資格邏輯或型別 </th> 
   <th colname="col2" class="entry"> 帳單分佈 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">和</span> </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數，套用至使用布林值<span class="wintitle">與</span>條件之規則型區段中的所有提供者特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">或</span> </p> </td> 
   <td colname="col2"> <p>將傳遞的曝光總數加權配置，套用至使用布林值OR條件的規則型區段中的所有提供者特徵。 加權配置使用下列公式計算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數，套用至使用布林值<span class="wintitle"> NOT</span>條件之規則型區段中的所有提供者特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演演算法區段 </p> </td> 
   <td colname="col2"> <p>在包含演演算法特徵的區段中，將100%的傳遞曝光總數套用至所有提供者摘要。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帳單範例 {#billing-examples}

以下範例旨在說明如何在資料摘要層級完成[!DNL CPM]使用量配置。

>[!IMPORTANT]
>建議您改為[報告區段層級](#segment-level-report)的CPM使用量，以自動完成此程式。

讓我們考慮下列情況：

![計費範例](assets/billing-examples.png)

<br> 

### 案例1：具有AND資格規則的區段

此區段包含來自不同資料提供者的3個特徵。 由於區段資格是以[!UICONTROL AND]條件為基礎，訪客必須從所有三個摘要實現特徵，才能符合區段的資格。

![](assets/billing-segment-and.png)

若有[!UICONTROL AND]條件，您必須將當月收到的100%曝光數指派給全部三個資料提供者。 在[!UICONTROL Audience Marketplace > Payables]區段中，您將每個提供者的1,000,000次曝光數計入評分。

此範例適用於使用[!DNL Boolean] [!UICONTROL NOT]運運算元的區段或包含演演算法特徵的區段。

<br> 

### 案例2：具有OR資格規則的區段

此區段包含來自不同資料提供者的3個特徵。 由於區段資格是以[!UICONTROL OR]條件為基礎，訪客必須至少實現三個特徵中的一個，才能符合該區段的資格。

我們無法分辨哪個特徵造成印象，因為資格是以[!UICONTROL OR]條件為基礎。 因此，在[!UICONTROL Audience Marketplace > Payables]區段中，您會根據特徵母體，以曝光總數的加權配置來評價每個提供者。

![帳單 — 區段 — 或](assets/billing-segment-or.png)

<br> 

### 案例3：包含模型與啟用使用案例的區段

此範例說明如何根據兩個資料摘要使用案例進行歸因：模型及啟用。 在此範例中，我們檢視兩個資料提供者，其資訊如下：

![資料摘要](assets/feed-use-cases.png)

在下表中，區段X包含兩個特徵T1和T2，區段規則T1或T2，其中：

* T1是資料摘要A中的特徵；
* T2是演演算法特徵，根據資料摘要A和資料摘要B的第三方特徵建模。

此區段已對應至目的地，並使用[區段層級報表](#segment-level-report)，在一個月內為此區段輸入1,000,000次曝光數。

這1,000,000次曝光中：

* T1佔區段人口的40%，這表示資訊源A有400,000次曝光次數。
* T2佔區段人口的60%，這表示對摘要A和摘要B有600,000次曝光。

在資料摘要層級，曝光的分配方式為：

* 資料摘要A會從特徵T2 （以資料摘要A和資料摘要B的特徵為模型，因此兩者都會收到曝光數）接收600,000次曝光數，而特徵T1 （資料摘要A的特徵）接收400,000次曝光數，總計為1,000,000次曝光數。
* 資料摘要B從特徵T2接收600,000次曝光數（請參閱上述說明），並從特徵T1接收0次曝光數。

依資料摘要和使用案例的簡單劃分如下：

![摘要劃分](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>對於模型使用案例，您應該只報告啟動時的CPM使用量。 如果您只執行模型，但不啟動模型，則不需要使用量報表。

<br> 

## 固定費用資料摘要的計費和曝光分配 {#billing-flat-fee}

固定費用資料摘要每個月都會向您收取固定金額，無論訂閱何時開始或您使用的曝光次數為何。 部分月份的使用或間隔不按比例分攤費用。 與CPM計費一樣，Adobe將會產生發票，並以您訂閱的資料摘要的每月固定費用率向您計費。

例如，假設您決定於月中開啟摘要中的某些特徵。 無論您何時開始訂閱或啟用特定特徵，仍會按每月全額費率向您收費。
