---
description: Audience Marketplace資料購買者同意根據每千個廣告印象(CPM)的成本，來報告資料饋送所提供的所有廣告印象。CPM使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。
seo-description: Audience Marketplace資料購買者同意根據每千個廣告印象(CPM)的成本，來報告資料饋送所提供的所有廣告印象。CPM使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。
seo-title: 資料饋送購買者帳單
solution: Audience Manager
title: 資料饋送購買者帳單
keywords: 區段層級報告、區段層級、區段層級
uuid: d7236667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: a8320894c0efcf46bd3236494e1aa7b1eded24d1

---


# 資料饋送購買者帳單 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意使用每千個廣告印象([!DNL CPM])基準成本來報告資料饋送所提供的所有廣告印象。[!DNL CPM] 使用量會在每個日曆月份的第天到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。

<br> 

## 如何報告CPM使用情形 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意根據每千個廣告印象([!DNL CPM])基準所支付的成本，報告所提供的所有廣告印象。[!DNL CPM] 使用量會在每個日曆月份的天內到期，並包含上個月的資料。收取較高費用用戶不需要報告使用量。

[!UICONTROL Audience Marketplace] 提供兩種報告 [!DNL CPM] 用途的方式：

* **區段層級報告**：這是建議 [!DNL CPM] 的使用報表方法。當您在區段層級報告 [!DNL CPM] 使用情形時，資料饋送層級報告區域會根據CPM資料饋送 [](#cost-attribution)成本歸因中所述的演算法，自動填入相應的使用量。
* **資料饋送層級報告**：此方法要求您根據CCPM資料饋送 [!DNL CPM][成本歸因中所述的演算法個別報告每個資料饋送的使用量](#cost-attribution)。不過，此方法較麻煩且容易出錯，而非區段層級報告。

<br> 

## 區段層級報告CPM使用情形 {#segment-level-report}

[!UICONTROL Segment Usage] 此標籤可讓您報告區段層級使用情形，同時顯示依對應目的地分組的區段。

在區段層級使用報表 [!DNL CPM] 使用後， [!UICONTROL Audience Marketplace] 根據CPM資料饋送的 [「成本歸因](#cost-attribution)」，自動指派正確的資料饋送正確使用。

若要在區段層級報告 [!DNL CPM] 使用情形：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;前往。
1. 選取 **[!UICONTROL Segment Usage]** 標籤。
1. 填寫區段的使用情形。如果您只需要對部分區段進行報告，即可使用 [!UICONTROL Search] 此方塊篩選區段。
1. Click **[!UICONTROL Edit Segments Usage]**.
1. 在欄中輸入 [!DNL CPM] 使用 [!UICONTROL Usage] 量。
1. 在完成時按一下， **[!UICONTROL Save]** 檢閱確認對話方塊。

   ![確認區段使用](assets/confirm-segment-usage.png)

1. Click **[!UICONTROL Confirm]**.

另請參閱我們的影片示範如何報告區段層級使用情形：

>[!VIDEO](https://video.tv.adobe.com/v/25522/?captions=chi_hant)

 

## 報告資料饋送層級的CPM使用量 {#feed-level-report}

資料饋送層級報告較為麻煩且容易出錯，因為您必須個別計算每個資料饋送的 [!DNL CPM] 使用量。建議您改為 [在區段層級](#segment-level-report) 報告CPM使用情形。

若要在區段層級報告 [!DNL CPM] 使用情形：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;前往。
2. 選取 **[!UICONTROL Feed Usage]** 標籤。
3. 使用 [!UICONTROL Search] 方塊來篩選資料饋送，並識別您需要報告的資料饋送。
4. Click **[!UICONTROL Edit Feeds Usage]**.
5. 根據CPM [!DNL CPM] 資料饋送 [](#cost-attribution)的成本歸因計算每個資料饋送的使用量，然後在 [!UICONTROL Usage] 欄中輸入。
6. 在完成時按一下， **[!UICONTROL Save]** 檢閱確認對話方塊。

   ![確認摘要使用](assets/confirm-feed-usage.png)

7. Click **[!UICONTROL Confirm]**.

<br> 

## 大量報告

若要在報告 [!DNL CPM] 使用時減少錯誤和負荷，您可以使用批量報告選項下載包含資料饋送和區段 [!DNL CSV] 的檔案、填寫使用量，然後將其上傳回 [!DNL Audience Manager]。您可以使用大量報告來報告摘要和區段使用情形。

若要大量更新 [!DNL CPM] 使用：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;前往。
1. 視您要更新的報表類型，選取或 **[!UICONTROL Feed Usage]****[!UICONTROL Segment Usage]** 標籤。
1. 按一下 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**。
1. 按一下 **[!UICONTROL download the current usage]** 以確定您使用有效的CSV檔案。
1. 開啓電腦上的檔案，然後填寫使用報表。
1. 按一下 **[!UICONTROL Choose a CSV file]** 以上傳更新的使用狀況報表。

   ![usation-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 當檔案一上傳，並提示您偵測檔案中的任何錯誤時，就會加以驗證。

<br> 

### 大量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 無效輸入 | [!DNL Audience Manager] 偵測 [!DNL CSV] 到檔案結構中的變更，例如遺漏欄或欄標題變更。 | 避免變更表格結構。 |
| 找不到 | 對於 [!UICONTROL Segment Level Reporting]， [!DNL Audience Manager] 無法識別 [!UICONTROL Segment ID][!UICONTROL Destination ID] 和組合。對於 [!UICONTROL Feed Level Reporting]， [!DNL Audience Manager] 無法識別 [!UICONTROL Data Provider Name]和 [!UICONTROL Feed Name][!UICONTROL Use Case] 組合。 | 對於 [!UICONTROL Segment Level Reporting]，請檢查 [!UICONTROL Segment ID] 與 [!UICONTROL Destination ID] 組合的有效性。對於 [!UICONTROL Feed Level Reporting]，請檢查 [!UICONTROL Data Provider Name]和 [!UICONTROL Feed Name][!UICONTROL Use Case] 組合的有效性。 |
| 找到重復的記錄 | [!DNL Audience Manager] 偵測到具有不同曝光值的重復記錄。 | 檢閱報表並確定您不會針對相同資料饋送或區段報告不同的使用值。 |
| 不支援的值 | [!DNL Audience Manager] 已偵測 [!DNL Audience Manager] 到欄中的非數值。 | 檢閱報表並確定您只在 [!DNL Audience Manager] 欄中輸入數值。 |
| 遺失必填欄位標題 | [!DNL Audience Manager] 偵測到強制欄位遺失表格標題。對於 [!UICONTROL Segment Level Reporting]，強制欄位為： [!UICONTROL Segment ID][!UICONTROL Destination ID]對於 [!UICONTROL Feed Level Reporting]，強制欄位為： [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name][!UICONTROL Use Case] | 檢閱報表並確定表格標題未遭到竄改。 |

>[!NOTE]
>從 [!DNL CSV] 使用報表移除列對現有的使用報表沒有任何影響。[!DNL Audience Manager] 只會處理報表中包含的欄位。

<br> 

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
   <p> 報告曝光總數，而不使用小數。Audience Manager會根據您報告的總數自動計算CPM。</p><p>如果您需要報告1,234,567印象，請如實報告。您不需要將曝光總數除以1,000計算CPM。</p><p>使用Adobe Target或Analytics目的地等工具最佳化網頁或應用程式內容(內容最佳化)的特性不會對CPM計劃的「使用量」總計貢獻貢獻。資料供應商通常會使用付費費用計劃獲得內容最佳化的補償。</p><p>如需詳細資訊，請參閱 <a href="#cost-attribution">CPM資料饋送</a> 的成本歸因。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅守每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報告系統會在每個月的第五個月之後關閉。如果您未報告CPM使用情況，則必須將該金額新增至下個月的報表。例如，假設您在10月使用了1000印象，錯過10月的報告期限，並在11月使用1000印象。在此情況下，您會報告12月和11月(2000)到12日之間的總計(2000)。</p><p><b>秘訣</b>：您應一律嘗試報告下個月第一個月到第五個月之間的CPM使用情形。</p><p>您最遲可以在新日曆月份的第個時間報告CPM使用，但不建議這麼做。每個月在第五個月前報告CPM使用情形，可讓Audience Manager時間檢查和處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM資料饋送的成本歸因 {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report express value，for your each of your segments.建議您在區段層級報告 [!DNL CPM] 使用量，以便自動完成成本歸因。

<!-- marketplace_cpm_billing.xml -->

### 帳單摘要 {#billing-summary}

您必須在每個日曆月份的第一個和第五個天之間提交 [!DNL CPM] 資料饋送曝光金額。若要正確執行此作業，建議您 [在區段層級報告CPM使用情形](#segment-level-report)。

>[!TIP]
>當您在區段層級報告 [!DNL CPM] 使用情形時，資料饋送層級報告區域會自動填入對應的使用量。

在您需要 [!UICONTROL Report CPM Usage at Data Feed Level]時，您必須個別編譯前一個日曆月份中每個饋送的所有印象，並根據本文所述的計費配置來報告這些印象。

在您的前一個日曆月份報告 [!DNL CPM] 數字後，將 [!DNL Adobe] 執行下列動作：

* 建立發票，並根據每個訂閱資料饋送 [!DNL CPM] 的費率向您收費。
* 根據您所報告 [!DNL CPM] 的用途支付資料供應商(賣方)費用。

>[!IMPORTANT]
>
>身為購買者，所有報告的曝光總數必須是真實且正確的。如果您未在每月的第天前報告曝光總數，則必須包含下個月未回報月份的總計。

<br> 

## 根據特徵資格規則在動態消息層級指派印象 {#assign-impressions}

[!UICONTROL Activation] 使用案例可讓您使用對應資料饋送中的特性來建立 [區段產生器](../../../features/segments/segment-builder.md) 中的區段，並將這些區段對應至目的地。布林運算元 [!UICONTROL AND]， [!UICONTROL OR]並 [!UICONTROL NOT] 讓您設定特徵和區段資格的條件。

當您 [在資料饋送層級](#feed-level-report)報告CPM使用情形時，您必須根據特徵資格規則中使用 [!DNL Boolean] 的運算子，為每個資料饋送分配比例。下表列出如何依布林規則或特徵類型正確分配印象。

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
   <td colname="col2"> <p>將100%的傳遞印象總計套用至使用布林 <span class="wintitle"> AND</span> 條件之規則區段中的所有提供者特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或</span> </p> </td> 
   <td colname="col2"> <p>在使用布林OR條件的規則區段中，將傳送的印象總數加權分配給所有提供者特徵。加權配置是使用下列公式計算：</p><p><code>(特徵人口/區段人口量)*印象數* CPM成本</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>將100%的遞送印象總計套用至使用布林 <span class="wintitle"> NOT</span> 條件之規則區段中的所有提供者特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法區段 </p> </td> 
   <td colname="col2"> <p>將100%的遞送曝光總數套用至包含演算法特徵之區段中的所有提供者摘要。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帳單範例 {#billing-examples}

下列範例旨在說明 [!DNL CPM] 如何在資料饋送層級完成使用分配。

>[!IMPORTANT]
>建議您改為 [在區段層級](#segment-level-report) 報告CPM使用情形，讓此程序自動完成。

假設下列情況：

![帳單範例](assets/billing-examples.png)

<br> 

### 案例1：具有AND資格的區段

此區段包含來自不同資料供應商的個特性。由於區段符合是 [!UICONTROL AND] 以條件為基礎，所以訪客必須從三個動態消息實現特徵，才能符合區段資格。

![](assets/billing-segment-and.png)

[!UICONTROL AND] 有了條件，您必須將當月收到的印象指派給所有三個資料供應商。[!UICONTROL Audience Marketplace > Payables] 在區段中，您為每個提供者評分1,000,000印象。

此範例適用於使用 [!DNL Boolean][!UICONTROL NOT] 運算子或包含演算法特性之區段的區段。

<br> 

### 案例2：具有OR資格的區段

此區段包含來自不同資料供應商的個特性。由於區段符合是 [!UICONTROL OR] 以條件為基礎，所以訪客必須至少實現這三項特性之一才能符合區段資格。

我們無法辨別哪些特徵會造成曝光，因為資格是根據 [!UICONTROL OR] 條件而定。因此， [!UICONTROL Audience Marketplace > Payables] 在區段中，您會根據特徵人口來加權每個提供者加權配置的加權。

![帳單區段-或](assets/billing-segment-or.png)

<br> 

### 案例3：具有模型和啓動使用案例的區段

此範例說明根據兩個資料饋送使用案例的歸因-模型和啓動。在此範例中，我們尋找兩個資料提供者，其中包含下列資訊：

![資料饋送](assets/feed-use-cases.png)

在下表中，區段X包含兩個特性：T和T2，以及區段規則T1OR T2，其中：

* T是資料饋送A的特徵；
* T是模型特徵，以第三方特徵為模型，來自資料饋送A和資料饋送B。

區段會映射至目的地，並使用 [區段層級報告](#segment-level-report)，在一個月內輸入該區段的1,000,000印象。

在這些1,000,000印象中：

* T佔40%的區段人口，為動態消息A帶來400,000印象。
* T佔60%的區段人口，為動態消息A和動態消息B帶來600,000印象。

在資料饋送層級，配置的方式為：

* 資料饋送A收到來自特徵T的600,000印象(以資料饋送A和資料饋送B的特徵為模型，因此會收到來自特徵T的印象)和400,000印象(來自資料饋送A的特徵)，累積1,000,000印象。
* 資料饋送B收到特徵T的600,000印象(請參閱上述說明)和特徵T的0印象。

資料饋送和使用案例的詳盡詳盡分析如下：

![摘要劃分](assets/feed-breakdown-alt.png)

<br> 

## 持平費用資料饋送的計費和曝光分配 {#billing-flat-fee}

固定費用資料饋送會每月向您帳單，無論訂閱開始或您使用的印象為何。費用不會計算在部分月份使用或間隔。如同CPM帳單，Adobe會產生發票，並以每月、固定費用費率的方式為您訂閱資料饋送收費。

例如，假設您決定在一個月中開啓動態消息中的某些特性。無論您何時開始訂閱或啓動特定特性，無論您是以每月的價格計費，都還是可以收費。