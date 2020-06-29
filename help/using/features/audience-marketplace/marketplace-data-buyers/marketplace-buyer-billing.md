---
description: Audience Marketplace資料購買者同意使用資料饋送中包含的特性來報告所有提供的廣告印象，這些特性以每千個廣告印象(CPM)的成本為定價基礎。 CPM使用情形應於每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用情形。
seo-description: Audience Marketplace資料購買者同意使用資料饋送中包含的特性來報告所有提供的廣告印象，這些特性以每千個廣告印象(CPM)的成本為定價基礎。 CPM使用情形應於每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用情形。
seo-title: 資料摘要購買者的計費方式
solution: Audience Manager
title: 資料摘要購買者的計費方式
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 1%

---


# 資料摘要購買者的計費方式 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意使用資料饋送中包含的特性來報告所有提供的廣告印象(以每千個廣告印象([!DNL CPM])為基礎)。 [!DNL CPM] 使用情形應於每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用情形。

<br> 

## 如何報告CPM使用情形 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意使用資料饋送中包含的特性來報告所有提供的廣告印象，這些特性以每千個廣告印象([!DNL CPM])為基礎。 [!DNL CPM] 使用情形應於每個日曆月的5天到期，並包含上個月的資料。 固定費用訂閱者不需要報告使用情形。

[!UICONTROL Audience Marketplace] 提供兩種報告使用情況的 [!DNL CPM] 方式：

* **區段層級報表**: 這是建議的使 [!DNL CPM] 用報告方法。 當您在區 [!DNL CPM] 段層級報告使用情形時，資料饋送層級報告區段會根據CPM資料饋送的成本歸因中所述的演算法，自動填入對應的使用 [量金額](#cost-attribution)。
* **資料饋送層級報表**: 此方法要求您根據CPM資料饋送 [!DNL CPM] 的成本歸因中所述演算法，個別報告每 [個資料饋送的使用情況](#cost-attribution)。 不過，與區段層級報表相比，此方法更麻煩，而且容易出錯。

<br> 

## 在區段層級報告CPM使用情形 {#segment-level-report}

此標 [!UICONTROL Segment Usage] 簽可讓您報告區段層級的使用情形，同時顯示依其對應目標分組的區段。

在區段層 [!DNL CPM] 級報告使用情形後， [!UICONTROL Audience Marketplace] 根據CPM資料饋送的成本歸因，自動指派對應的資料饋 [送正確的使用情形](#cost-attribution)。

若要在區 [!DNL CPM] 段層報告使用情況：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**。
1. 選擇選 **[!UICONTROL Segment Usage]** 項卡。
1. 填寫區段的使用情形。 如果您只需 [!UICONTROL Search] 報告其中一些區段的使用情況，可使用方塊來篩選區段。
1. 按一下 **[!UICONTROL Edit Segments Usage]**.
1. 在列中 [!DNL CPM] 輸入使用量 [!UICONTROL Usage] 金額。
1. 完成 **[!UICONTROL Save]** 時按一下並查看確認對話框。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 按一下 **[!UICONTROL Confirm]**.

另請參閱我們的視訊展示，說明如何報告區段層級的使用情形：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 資料饋送層級的報表CPM使用情形 {#feed-level-report}

資料饋送層級報表較為繁雜，而且容易出錯，因為您必須個別計算每個資料饋送 [!DNL CPM] 的使用情形。 我們建議您改為 [在區段層級報告CPM使用](#segment-level-report) 。

若要在區 [!DNL CPM] 段層報告使用情況：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**。
2. 選擇選 **[!UICONTROL Feed Usage]** 項卡。
3. 使用方 [!UICONTROL Search] 塊篩選資料饋送，並識別您報告使用情況所需的資料饋送。
4. 按一下 **[!UICONTROL Edit Feeds Usage]**.
5. 根據 [!DNL CPM] CPM資料饋送的「成本歸因」計算每個資料饋送的使 [用情形](#cost-attribution)，並在欄中輸 [!UICONTROL Usage] 入。
6. 完成 **[!UICONTROL Save]** 時按一下並查看確認對話框。

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. 按一下 **[!UICONTROL Confirm]**.

<br> 

## 大量報告

若要減少報告使用時的錯 [!DNL CPM] 誤和開銷，您可以使用大量報告選項來下載包含資料饋送和區段的 [!DNL CSV] 檔案、填寫使用情形，然後將它上傳回 [!DNL Audience Manager]。 您可以使用大量報告來報告動態消息和區段使用情形。

若要大量 [!DNL CPM] 更新使用：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**。
1. 選擇 **[!UICONTROL Feed Usage]** 或標 **[!UICONTROL Segment Usage]** 簽，視您要更新的報表類型而定。
1. 按一下 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**。
1. 按一 **[!UICONTROL download the current usage]** 下以確定您使用有效的CSV檔案。
1. 在您的電腦上開啟檔案並填寫使用狀況報告。
1. 按一 **[!UICONTROL Choose a CSV file]** 下以上傳更新的使用狀況報表。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 當您上傳檔案時，會立即驗證它，並提示您是否偵測到檔案中的任何錯誤。

<br> 

### 大量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 輸入無效 | [!DNL Audience Manager] 檢測到檔案模式 [!DNL CSV] 中的更改，如缺少列或列標題的更改。 | 避免更改表結構。 |
| 找不到 | 因 [!UICONTROL Segment Level Reporting]為 [!DNL Audience Manager] 無法識別 [!UICONTROL Segment ID] 和組 [!UICONTROL Destination ID] 合。 因 [!UICONTROL Feed Level Reporting]為， [!DNL Audience Manager] 無法識別 [!UICONTROL Data Provider Name]、 [!UICONTROL Feed Name]和組合 [!UICONTROL Use Case] 。 | 對於 [!UICONTROL Segment Level Reporting]，檢查和組合的 [!UICONTROL Segment ID] 有 [!UICONTROL Destination ID] 效性。 對 [!UICONTROL Feed Level Reporting]於，檢查組合、 [!UICONTROL Data Provider Name]和組 [!UICONTROL Feed Name]合的有 [!UICONTROL Use Case] 效性。 |
| 找到重複記錄 | [!DNL Audience Manager] 檢測到具有不同印象值的重複記錄。 | 檢閱報表，確定您未針對相同資料饋送或區段報告不同的使用值。 |
| 不支援的值 | [!DNL Audience Manager] 在列中檢測到非數 [!DNL Audience Manager] 值。 | 檢閱報表，並確定您只在欄中輸入數 [!DNL Audience Manager] 值。 |
| 遺失必要欄位的標題 | [!DNL Audience Manager] 偵測到必填欄位遺失表格標題。 對於 [!UICONTROL Segment Level Reporting]，必填欄位為： [!UICONTROL Segment ID], [!UICONTROL Destination ID]ý? 對於 [!UICONTROL Feed Level Reporting]，必填欄位為： [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name] [!UICONTROL Use Case] | 檢閱報表，並確定表格標題未遭竄改。 |

>[!NOTE]
>從使用狀況報 [!DNL CSV] 表移除列對現有使用狀況報表沒有任何影響。 [!DNL Audience Manager] 僅處理報表中包含的欄位。

<br> 

## [!DNL CPM] 報告最佳做法

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
   <td colname="col2"> <p>對於CPM印象總計： </p>
   <p> 報告曝光總數，不使用小數。 Audience Manager會根據您報告的總數自動計算CPM。</p><p>如果您需要報告1,234,567個印象，則報告完全如此。 您不需要將曝光總數除以1,000即可計算CPM。</p><p>使用Adobe Target或Analytics目的地等工具來最佳化您的網頁或應用程式內容（內容最佳化）的特性，不會對CPM計畫的「使用」總計有所貢獻。 資料提供者通常會使用固定費用計畫來補償內容最佳化。</p><p>如需詳 <a href="#cost-attribution">細資訊，請參閱CPM資料饋送的</a> 「成本歸因」。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅持每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報告系統在每月5號之後關閉。 如果您未能報告CPM使用情形，您必須將該金額新增至下個月的報告。 例如，假設您在10月使用1000個曝光次數、錯過10月的報表截止日期，並在11月使用1000個曝光次數。 在本例中，您會在12月1日至5日報告10月和11月的總計（2000年）。</p><p><b>提示</b>: 您應一律嘗試在下個月的第1天到第5天之間，報告上個月的CPM使用情形。</p><p>您可以報告CPM使用情形，最遲於新日曆月的5日，但不建議這麼做。 在每月5日之前報告CPM使用情形，讓Audience Manager有時間檢查及處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM資料饋送的成本歸因 {#cost-attribution}

在此 [!UICONTROL Audience Marketplace] 中，您必須針對每個區段每月自行報告曝光金額。 我們建議在 [!DNL CPM] 區段層級報告使用情形，以便自動完成成本歸因。

<!-- marketplace_cpm_billing.xml -->

### 帳單摘要 {#billing-summary}

您必須在 [!DNL CPM] 每個日曆月的第1天到第5天之間提交資料饋送曝光金額。 若要正確執行此動作，我們建議您在區段 [層級報告CPM使用情形](#segment-level-report)。

>[!TIP]
>在區段層 [!DNL CPM] 級報告使用情形時，資料饋送層級報告區段會自動填入對應的使用量金額。

如果您需要， [!UICONTROL Report CPM Usage at Data Feed Level]您必須個別匯整前一個日曆月內每個饋送傳遞的所有印象，並根據本文所述的帳單分配來報告這些印象。

在您報 [!DNL CPM] 告上一個日曆月的編號後， [!DNL Adobe] 將執行下列動作：

* 根據每個訂閱資料饋送的費率， [!DNL CPM] 建立發票和帳單。
* 根據您所報告的使用情況，支付資料提供者（銷售者）欠付的 [!DNL CPM] 費用。

>[!IMPORTANT]
>
>作為購買者，所有報告的曝光總數必須真實而準確。 如果您未能在每月的第5天前報告印象總計，您必須包含下個月未報告月份的總計。

<br> 

## 根據特徵資格規則在動態消息層級指派曝光 {#assign-impressions}

使用 [!UICONTROL Activation] 案例可讓您在對應的資料饋送中使用特徵，在「區段產生器」中建 [立區段](../../../features/segments/segment-builder.md) ，並將這些區段對應至目標。 布林運算 [!UICONTROL AND]子、 [!UICONTROL OR]和 [!UICONTROL NOT] 可讓您設定特徵和區段限定條件。

在「資 [料饋送層級」報告CPM使用情形時](#feed-level-report)，您必鬚根據特徵限定規則中使用的運算子，按比例分配每個資料 [!DNL Boolean] 饋送的印象。 下表列出如何依布林規則或特徵類型正確分配印象。

>[!TIP]
>[在區段層級報告CPM使用](#segment-level-report) ，讓Audience Manager自動完成資料饋送層級報告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則限定邏輯或類型 </th> 
   <th colname="col2" class="entry"> 帳單分發 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 和</span> </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數套用至使用布林值 <span class="wintitle"> AND條件之規則型區段中的所有提供者特徵</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或</span> </p> </td> 
   <td colname="col2"> <p>在使用布林OR條件的規則型區段中，將已傳遞印象總計的加權分配套用至所有提供者特徵。 加權分配乃使用下列公式計算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數套用至使用布林值 <span class="wintitle"> NOT條件之規則型區段中的所有提供者特徵</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法區段 </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數套用至包含演算法特徵之區段中的所有提供者饋送。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帳單範例 {#billing-examples}

下列範例旨在說明如何在資 [!DNL CPM] 料饋送層級進行使用量分配。

>[!IMPORTANT]
>建議您改為在 [區段層級報告CPM使用](#segment-level-report) ，以自動完成此程式。

讓我們考慮以下情況：

![billing-examples](assets/billing-examples.png)

<br> 

### 案例1: 具有AND資格規則的區段

此區段包含來自個別資料提供者的3個特徵。 由於區段資格是以條件為 [!UICONTROL AND] 基礎，因此訪客必須從所有三個動態消息中瞭解特性，才能符合區段資格。

![](assets/billing-segment-and.png)

有了條 [!UICONTROL AND] 件，您必須將當月收到的曝光數的100%指派給所有三個資料提供者。 在該 [!UICONTROL Audience Marketplace > Payables] 節中，您對每個提供者評分為1,000,000個印象。

此範例適用於使用運算子的 [!DNL Boolean] 區段或 [!UICONTROL NOT] 包含演算法特徵的區段。

<br> 

### 案例2: 具有OR資格規則的區段

此區段包含來自個別資料提供者的3個特徵。 由於區段資格是以條件為 [!UICONTROL OR] 基礎，因此訪客必須實現三個特徵中的至少一個才能符合區段資格。

我們無法判斷哪個特徵會造成印象，因為資格是以條件為 [!UICONTROL OR] 基礎。 因此，在區段中，您 [!UICONTROL Audience Marketplace > Payables] 會根據特徵人口，為每位提供者評分加權的印象總數。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3: 具有模型和啟動使用案例的區段

此範例說明根據兩個資料饋送使用案例（模型和啟動）來歸因。 在此範例中，我們檢視了兩個資料提供者，其中包含下列資訊：

![資料饋送](assets/feed-use-cases.png)

在下表中，區段X包含兩個特徵，T1和T2，區段規則為T1或T2，其中：

* T1是資料饋送A的特徵；
* T2是以「資料饋送A」和「資料饋送B」的第三方特徵為模型的演算法特徵。

區段會對應至目標，而使用區段層級報表，該區段在一個月內會輸入1,000,000 [個印象](#segment-level-report)。

在這1,000,000個印象中：

* T1佔區段人口的40%，相當於動態消息A的400,000印象。
* T2佔區段人口的60%，相當於動態消息A和動態消息B有600,000個曝光。

在資料饋送層級，印象的分配方式為：

* 資料饋送A從特徵T2（以資料饋送A和資料饋送B的特徵為模型，因此都會收到曝光）接收600,000次曝光，而從特徵T1（資料饋送A的特徵）接收400,000次曝光，總計1,000,000次曝光。
* 資料饋送B從特徵T2接收600,000個印象（請參閱上述說明），從特徵T1接收0個印象。

依資料饋送和使用案例的一覽式劃分如下：

![動態消息劃分](assets/feed-breakdown-alt.png)

<br> 

## 固定費用資料饋送的計費和印象分配 {#billing-flat-fee}

固定費用資料饋送每月向您收取固定金額，不論訂閱何時開始或您使用多少印象。 部分月份使用或間隔不按比例支付費用。 和CPM帳單一樣，Adobe會針對您訂閱的資料饋送，以每月固定費率產生髮票並向您收費。

例如，假設您決定在月中旬開啟動態消息中的特定特徵。 無論您是在何時開始訂閱或啟動特定特性，您仍會以每月全額計費。