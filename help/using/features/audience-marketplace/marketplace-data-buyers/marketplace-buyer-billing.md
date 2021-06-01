---
description: Audience Marketplace資料購買者同意報告所有透過資料摘要中包含的特徵所提供的廣告曝光次數，這些特徵以每千個廣告曝光次數(CPM)的成本為基礎。 CPM使用情形應於每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用情況。
seo-description: Audience Marketplace資料購買者同意報告所有透過資料摘要中包含的特徵所提供的廣告曝光次數，這些特徵以每千個廣告曝光次數(CPM)的成本為基礎。 CPM使用情形應於每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用情況。
seo-title: 資料摘要購買者的計費方式
solution: Audience Manager
title: 資料摘要購買者的計費方式
keywords: 區段層級報表、區段層級、區段層級
uuid: d7236667-282b-4160-9909-579721af4016
feature: 訪客交易市場
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2064'
ht-degree: 1%

---

# 資料摘要購買者的計費方式 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意報告所有透過資料摘要中包含的特徵所提供的廣告曝光次數，這些特徵是以每千個廣告曝光次數([!DNL CPM])為基礎定價。 [!DNL CPM] 使用量在每個日曆月的第5天到期，並包含前一個月的資料。固定費用訂閱者不需要報告使用情況。

<br> 

## 如何報告CPM使用量{#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意報告所有透過資料摘要中包含的特徵所提供的廣告曝光次數([!DNL CPM])，這些特徵的定價是每千個廣告曝光次數的成本。[!DNL CPM] 使用量在每個日曆月的5天到期，且包含前一個月的資料。固定費用訂閱者不需要報告使用情況。

[!UICONTROL Audience Marketplace] 提供兩種報告使用情 [!DNL CPM] 況的方法：

* **區段層級報表**:這是建議的使 [!DNL CPM] 用報告方法。當您報告區段層級的[!DNL CPM]使用量時，資料摘要層級的報告區段會根據CPM資料摘要](#cost-attribution)的[成本歸因中所述的演算法，自動填入對應的使用量。
* **資料摘要層級報表**:此方法需要您根據CPM資 [!DNL CPM] 料摘要的成本歸因中所述的演算法，個別報 [告每個資料摘要的使用情況](#cost-attribution)。不過，此方法比區段層級的報表更繁瑣且容易出錯。

<br> 

## 區段層級{#segment-level-report}的報表CPM使用量

[!UICONTROL Segment Usage]標籤可讓您報告區段層級的使用情形，同時顯示依其對應目的地分組的區段。

在報告區段層級的[!DNL CPM]使用量後， [!UICONTROL Audience Marketplace]會根據CPM資料饋送的[成本歸因](#cost-attribution)自動指派對應的資料饋送正確的使用量。

若要報告區段層級的[!DNL CPM]使用量：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 選擇&#x200B;**[!UICONTROL Segment Usage]**&#x200B;頁簽。
1. 填入區段的使用情形。 如果您只需要報告其中某些區段的使用情況，可以使用[!UICONTROL Search]方塊來篩選區段。
1. 按一下 **[!UICONTROL Edit Segments Usage]**.
1. 在[!UICONTROL Usage]欄中輸入[!DNL CPM]使用量。
1. 完成後，按一下&#x200B;**[!UICONTROL Save]**&#x200B;並查看確認對話框。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 按一下 **[!UICONTROL Confirm]**.

另請參閱我們的影片示範，以了解如何報告區段層級的使用情形：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 資料摘要層級{#feed-level-report}的報表CPM使用量

資料摘要層級的報表較為繁瑣且容易出錯，因為您必須個別計算每個資料摘要的[!DNL CPM]使用量。 建議您改為[以區段層級](#segment-level-report)報表CPM使用量。

若要報告區段層級的[!DNL CPM]使用量：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
2. 選擇&#x200B;**[!UICONTROL Feed Usage]**&#x200B;頁簽。
3. 使用[!UICONTROL Search]方塊來篩選資料摘要，並識別您需要針對哪些摘要來報告使用狀況。
4. 按一下 **[!UICONTROL Edit Feeds Usage]**.
5. 根據CPM資料摘要的[成本歸因](#cost-attribution)計算每個資料摘要的[!DNL CPM]使用量，並在[!UICONTROL Usage]欄中輸入。
6. 完成後，按一下&#x200B;**[!UICONTROL Save]**&#x200B;並查看確認對話框。

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. 按一下 **[!UICONTROL Confirm]**.

<br> 

## 大量報告

若要減少報告[!DNL CPM]使用情形時的錯誤和額外負荷，您可以使用大量報告選項來下載包含資料摘要和區段的[!DNL CSV]檔案、填寫使用情形，然後將其上傳回[!DNL Audience Manager]。 您可以使用大量報告來報告摘要和區段使用情況。

若要大量更新[!DNL CPM]使用情況：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 根據您要更新的報表類型，選取&#x200B;**[!UICONTROL Feed Usage]**&#x200B;或&#x200B;**[!UICONTROL Segment Usage]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Edit Feeds Usage]**&#x200B;或&#x200B;**[!UICONTROL Edit Segments Usage]**。
1. 按一下&#x200B;**[!UICONTROL download the current usage]**&#x200B;以確定您使用有效的CSV檔案。
1. 在電腦上開啟檔案，並填入使用狀況報表。
1. 按一下&#x200B;**[!UICONTROL Choose a CSV file]**&#x200B;以上傳更新的使用情況報表。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 會在您上傳檔案時立即驗證該檔案，並提示您是否偵測到檔案中的任何錯誤。

<br> 

### 大量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 輸入無效 | [!DNL Audience Manager] 檢測到檔案架 [!DNL CSV] 構中的更改，如缺少列或列標題的更改。 | 避免更改表結構。 |
| 找不到 | 對於[!UICONTROL Segment Level Reporting],[!DNL Audience Manager]無法識別[!UICONTROL Segment ID]和[!UICONTROL Destination ID]組合。 對於[!UICONTROL Feed Level Reporting],[!DNL Audience Manager]無法識別[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]組合。 | 對於[!UICONTROL Segment Level Reporting]，檢查[!UICONTROL Segment ID]和[!UICONTROL Destination ID]組合的有效性。 對於[!UICONTROL Feed Level Reporting]，檢查[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]組合的有效性。 |
| 找到重複記錄 | [!DNL Audience Manager] 檢測到具有不同曝光值的重複記錄。 | 檢閱報表，並確認不會針對相同資料摘要或區段報告不同的使用值。 |
| 不支援的值 | [!DNL Audience Manager] 在列中檢測到非數值 [!DNL Audience Manager] 值。 | 檢閱報表，並確認您只在[!DNL Audience Manager]欄中輸入數值。 |
| 缺少必填欄位的標題 | [!DNL Audience Manager] 檢測到必填欄位缺少表標題。對於[!UICONTROL Segment Level Reporting]，必填欄位為：[!UICONTROL Segment ID]、[!UICONTROL Destination ID]。 對於[!UICONTROL Feed Level Reporting]，必填欄位為：[!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | 檢閱報表，並確認表格標題未被篡改。 |

>[!NOTE]
>從[!DNL CSV]使用狀況報表中移除列對現有使用狀況報表沒有任何影響。 [!DNL Audience Manager] 只會處理報表中包含的欄位。

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
   <td colname="col1"> <p><b>一律報告曝光總數</b> </p> </td> 
   <td colname="col2"> <p>對於CPM曝光總計： </p>
   <p> 報告曝光總數，不使用小數。 Audience Manager會根據您報告的總數自動計算CPM。</p><p>若您需要報告1,234,567次曝光，報告方式與此完全相同。 您不需要將曝光總數除以1,000即可計算CPM。</p><p>使用Adobe Target或Analytics目的地等工具來最佳化您的網頁或應用程式內容（內容最佳化）的特徵，不會對CPM計畫的「使用量」總計產生任何影響。 資料提供者通常會使用固定費用計畫來補償內容最佳化。</p><p>如需詳細資訊，請參閱CPM資料饋送的<a href="#cost-attribution">成本歸因</a> 。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅持每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報告系統每月5號後關閉。 如果您未依此報告CPM使用量，則必須將該金額新增至下個月的報告。 例如，假設您在10月使用1000次曝光數、錯過10月報表的最後期限，並在11月使用1000次曝光數。 在這種情況下，您將在12月1日至5日報告10月和11月的合計（2000年）。</p><p><b>提示</b>:您應一律嘗試報告下月第1天至第5天之間前一個月的CPM使用量。</p><p>您可以將CPM使用量報告至新日曆月的5日，但不建議這麼做。 在每月5日之前報告CPM使用量，可讓Audience Manager有時間檢查及處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM資料饋送的成本歸因{#cost-attribution}

在[!UICONTROL Audience Marketplace]中，您必須針對每個區段每月自行報告曝光量。 建議您在區段層級報告[!DNL CPM]使用情況，以便自動完成成本歸因。

<!-- marketplace_cpm_billing.xml -->

### 帳單摘要{#billing-summary}

您必須在每個日曆月的第1天和第5天之間提交[!DNL CPM]資料摘要曝光量。 若要正確執行此動作，建議您[在區段層級](#segment-level-report)報告CPM使用量。

>[!TIP]
>當您報告區段層級的[!DNL CPM]使用量時，資料摘要層級報告區段會自動填入對應的使用量金額。

若您需要[!UICONTROL Report CPM Usage at Data Feed Level]，您必須個別匯整前一個日曆月份中每個摘要所傳送的所有曝光數，並根據本文所述的計費分配來報告。

在報告前一個日曆月的[!DNL CPM]數字後， [!DNL Adobe]將執行以下操作：

* 根據每個訂閱資料饋送的[!DNL CPM]費率建立發票和帳單。
* 根據您報告的[!DNL CPM]使用情況支付資料提供者（銷售者）應繳費用。

>[!IMPORTANT]
>
>身為購買者，所有報告的曝光總計必須真實且準確。 如果您無法在每月的第5天前報告曝光總計，則必須包含下個月未報告月份的總計。

<br> 

## 根據特徵資格規則{#assign-impressions}在摘要層級指派曝光數

[!UICONTROL Activation]使用案例可讓您在對應的資料摘要中使用特徵，在[區段產生器](../../../features/segments/segment-builder.md)中建立區段，並將這些區段對應至目的地。 布林運算子[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]可讓您設定特徵和區段資格的條件。

當您[在資料摘要層級](#feed-level-report)報告CPM使用情形時，您必鬚根據特徵資格規則中使用的[!DNL Boolean]運算子，以成比例方式為每個資料摘要分配曝光數。 下表列出如何依布林規則或特徵類型正確配置曝光次數。

>[!TIP]
>[「區段層級」的報表CPM使用量](#segment-level-report) ，讓資料摘要層級報表由Audience Manager自動完成。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則資格邏輯或類型 </th> 
   <th colname="col2" class="entry"> 帳單分配 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 和</span> </p> </td> 
   <td colname="col2"> <p>在使用布林值<span class="wintitle"> AND</span>條件的規則型區段中，將100%的傳送曝光總數套用至所有提供者特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或</span> </p> </td> 
   <td colname="col2"> <p>在使用布林值OR條件的規則型區段中，將傳送曝光總計的加權分配套用至所有提供者特徵。 加權分配使用下列公式計算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>在使用布林值<span class="wintitle"> NOT</span>條件的規則型區段中，將100%的傳送曝光總數套用至所有提供者特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法區段 </p> </td> 
   <td colname="col2"> <p>將100%傳遞的曝光總數套用至包含演算法特徵之區段中的所有提供者摘要。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帳單範例{#billing-examples}

以下範例旨在說明如何在資料饋送層級進行[!DNL CPM]使用量分配。

>[!IMPORTANT]
>建議您改為在區段層級[報告CPM使用量](#segment-level-report)，自動完成此程式。

讓我們考慮下列案例：

![帳單範例](assets/billing-examples.png)

<br> 

### 案例1:具有和資格規則的區段

此區段包含來自個別資料提供者的3個特徵。 由於區段資格是根據[!UICONTROL AND]條件，訪客必須從所有三個摘要實現特徵，才能符合區段資格。

![](assets/billing-segment-and.png)

若使用[!UICONTROL AND]條件，您必須將當月收到的曝光數的100%指派給所有三個資料提供者。 在[!UICONTROL Audience Marketplace > Payables]區段中，您對每個提供者給予1,000,000曝光次數的評分。

此範例適用於使用[!DNL Boolean] [!UICONTROL NOT]運算子的區段，或包含演算法特徵的區段。

<br> 

### 案例2:具有OR資格規則的區段

此區段包含來自個別資料提供者的3個特徵。 由於區段資格是根據[!UICONTROL OR]條件，因此訪客必須實現三個特徵中的至少一個才能符合區段資格。

我們無法判斷哪個特徵會造成曝光，因為資格是根據[!UICONTROL OR]條件。 因此，在[!UICONTROL Audience Marketplace > Payables]區段中，您會根據特徵母體，以加權配置的曝光總數來評給每個提供者。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3:具有模型和啟用使用案例的區段

此範例說明以兩個資料摘要使用案例（模型和啟用）為基礎的歸因。 在此範例中，我們查看了兩個資料提供者，其資訊如下：

![data-feed](assets/feed-use-cases.png)

在下表中，區段X包含T1和T2這兩個特徵，以及區段規則T1或T2，其中：

* T1是資料摘要A的特徵；
* T2是根據資料摘要A和資料摘要B的協力廠商特徵所建立的演算法特徵。

區段對應至目的地，並使用[區段層級報表](#segment-level-report)在一個月內為此區段輸入1,000,000曝光次數。

其中1,000,000次曝光：

* T1佔區段母體的40%，這表示摘要A有400,000次曝光。
* T2佔區段母體的60%，這表示摘要A和摘要B有600,000次曝光。

在資料摘要層級，曝光數的分配方式為：

* 資料摘要A會從特徵T2（此模型是根據資料摘要A和資料摘要B的特徵建立，因此兩者皆會收到曝光數）接收600,000次曝光數，從特徵T1（資料摘要A的特徵）接收400,000次曝光數，總計1,000,000次曝光數。
* 資料摘要B從特徵T2收到600,000次曝光（請參閱上述說明），從特徵T1收到0次曝光。

依資料摘要和使用案例的簡單劃分如下：

![摘要劃分](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>對於模型使用案例，您只應在啟動時報告CPM使用情況。 如果您只執行模型，但未啟動模型，則不需要使用情況報告。

<br> 

## 固定費用資料摘要的計費和曝光分配{#billing-flat-fee}

固定費用資料摘要每月會向您收取固定金額，無論訂閱何時開始或您使用的曝光次數為何。 部分月用量或間隔不按比例分攤費用。 與CPM帳單一樣，Adobe會為您訂閱的資料饋送，以每月固定費率產生髮票和帳單。

例如，假設您在月中決定開啟摘要中的某些特徵。 無論您是何時開始訂閱或啟動特定特徵，系統仍會以每月全額計費。
