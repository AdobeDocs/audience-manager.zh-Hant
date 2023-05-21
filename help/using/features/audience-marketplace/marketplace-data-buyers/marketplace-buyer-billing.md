---
description: Audience Marketplace資料購買者同意使用資料饋送中包含的特徵報告所有廣告印象，這些特徵以每千個廣告印象(CPM)為基礎，定價。 CPM使用將在每個日曆月的第5天到期，並包括上個月的資料。 固定費用訂閱者無需報告使用情況。
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: 資料摘要購買者的計費方式
keywords: 分部級報告、分部級、分部級
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 1%

---

# 資料摘要購買者的計費方式 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意使用資料源中包含的特性報告所提供的所有廣告印象（以每千個廣告印象的成本定價）[!DNL CPM])基礎。 [!DNL CPM] 使用情況在每個日曆月的第5天到期，並包括上個月的資料。 固定費用訂閱者無需報告使用情況。

<br> 

## 如何報告CPM使用情況 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意報告所有使用資料源中包含的特徵提供的廣告印象，該資料源以每千個廣告印象的成本定價([!DNL CPM])基礎。 [!DNL CPM] 使用情況在每個日曆月的5天到期，並包括上個月的資料。 固定費用訂閱者無需報告使用情況。

[!UICONTROL Audience Marketplace] 提供了兩種報告方法 [!DNL CPM] 用法：

* **段級報告**:這是推薦的 [!DNL CPM] 用法報告方法。 報告時 [!DNL CPM] 在段級的使用情況下，資料饋送級報告部分會根據中所述的算法自動填寫相應的使用量 [CPM資料源的成本分配](#cost-attribution)。
* **資料饋送級報告**:此方法要求您單獨報告 [!DNL CPM] 每個資料饋送的使用情況，基於中所述的算法 [CPM資料源的成本分配](#cost-attribution)。 但是，與段級報告相比，這種方法更加繁瑣且容易出錯。

<br> 

## 報告段級CPM使用情況 {#segment-level-report}

的 [!UICONTROL Segment Usage] 頁籤允許您報告段級使用情況，同時顯示按它們所映射到的目標分組的段。

報告後 [!DNL CPM] 在段級別， [!UICONTROL Audience Marketplace] 根據 [CPM資料源的成本分配](#cost-attribution)。

報告 [!DNL CPM] 在段級別：

1. 轉到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 選擇 **[!UICONTROL Segment Usage]** 頁籤。
1. 填寫段的用法。 您可以使用 [!UICONTROL Search] 框，以篩選某些段。
1. 按一下 **[!UICONTROL Edit Segments Usage]**.
1. 輸入 [!DNL CPM] 使用量 [!UICONTROL Usage] 的雙曲餘切值。
1. 按一下 **[!UICONTROL Save]** 完成後，查看確認對話框。

   ![確認段使用](assets/confirm-segment-usage.png)

1. 按一下 **[!UICONTROL Confirm]**.

另請參閱我們的視頻演示，瞭解如何報告段級使用情況：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 在資料饋送級別報告CPM使用情況 {#feed-level-report}

資料饋送級別報告是一個比較繁瑣且容易出錯的過程，因為您必須單獨計算 [!DNL CPM] 每個資料饋送的使用情況。 我們建議你 [報告段級CPM使用情況](#segment-level-report) 的雙曲餘切值。

報告 [!DNL CPM] 在段級別：

1. 轉到 **[!UICONTROL Audience Marketplace > Payables]**。
2. 選擇 **[!UICONTROL Feed Usage]** 頁籤。
3. 使用 [!UICONTROL Search] 框，用於篩選資料源並標識需要報告使用情況的源。
4. 按一下 **[!UICONTROL Edit Feeds Usage]**.
5. 計算 [!DNL CPM] 每個資料饋送的使用情況 [CPM資料源的成本分配](#cost-attribution)，並輸入 [!UICONTROL Usage] 的雙曲餘切值。
6. 按一下 **[!UICONTROL Save]** 完成後，查看確認對話框。

   ![確認源使用](assets/confirm-feed-usage.png)

7. 按一下 **[!UICONTROL Confirm]**.

<br> 

## 批量報告

在報告時減少錯誤和開銷 [!DNL CPM] 用法，您可以使用批量報告選項下載 [!DNL CSV] 包含資料源和段的檔案，填寫使用情況，然後將其上載回 [!DNL Audience Manager]。 您可以使用批量報告報告源和段使用情況。

要更新 [!DNL CPM] 批量使用：

1. 轉到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 選擇 **[!UICONTROL Feed Usage]** 或 **[!UICONTROL Segment Usage]** 頁籤，具體取決於要更新的報告類型。
1. 按一下 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**。
1. 按一下 **[!UICONTROL download the current usage]** 以確保使用有效的CSV檔案。
1. 開啟電腦上的檔案並填寫使用情況報告。
1. 按一下 **[!UICONTROL Choose a CSV file]** 上載更新的使用情況報告。

   ![使用報告 — csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上載檔案後立即驗證該檔案，如果檔案檢測到檔案中有任何錯誤，則會提示您。

<br> 

### 批量報告驗證錯誤

| 錯誤訊息 | 說明 | 修正 |
| ------------- | -------------| -----|
| 輸入無效 | [!DNL Audience Manager] 檢測到 [!DNL CSV] 檔案架構，如缺少列或對列標題的更改。 | 避免更改表結構。 |
| 找不到 | 對於 [!UICONTROL Segment Level Reporting]。 [!DNL Audience Manager] 無法識別 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 的下界。 對於 [!UICONTROL Feed Level Reporting]。 [!DNL Audience Manager] 無法識別 [!UICONTROL Data Provider Name]。 [!UICONTROL Feed Name], [!UICONTROL Use Case] 的下界。 | 對於 [!UICONTROL Segment Level Reporting]，檢查 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 的下界。 對於 [!UICONTROL Feed Level Reporting]，檢查 [!UICONTROL Data Provider Name]。 [!UICONTROL Feed Name], [!UICONTROL Use Case] 的下界。 |
| 找到重複記錄 | [!DNL Audience Manager] 檢測到具有不同印象值的重複記錄。 | 複查報告，並確保不報告相同資料饋送或段的不同使用值。 |
| 不支援的值 | [!DNL Audience Manager] 在 [!DNL Audience Manager] 的雙曲餘切值。 | 查看報告並確保僅在 [!DNL Audience Manager] 的雙曲餘切值。 |
| 缺少必需欄位的標題 | [!DNL Audience Manager] 檢測到必填欄位缺少表標題。 對於 [!UICONTROL Segment Level Reporting]，必填欄位為： [!UICONTROL Segment ID]。 [!UICONTROL Destination ID]。 對於 [!UICONTROL Feed Level Reporting]，必填欄位為： [!UICONTROL Data Provider Name]。 [!UICONTROL Data Feed Name]。  [!UICONTROL Use Case] | 查看報告並確保表頭未被篡改。 |

>[!NOTE]
>從 [!DNL CSV] 使用情況報告對現有使用情況報告沒有任何影響。 [!DNL Audience Manager] 僅處理報告中包含的欄位。

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
   <td colname="col1"> <p><b>始終報告印數總數</b> </p> </td> 
   <td colname="col2"> <p>對於CPM印象總計： </p>
   <p> 報告印數總數，不使用小數。 Audience Manager根據報告的總數自動計算CPM。</p><p>如果你需要報告1234567個印象，就照這樣報告。 計算CPM時，不需要將印象總數除以1000。</p><p>用於使用諸如Adobe Target或分析目標等工具優化您的Web或應用內容（內容優化）的特性不會影響CPM計畫的使用總計。 資料提供商通常使用統一費用計畫對內容優化進行補償。</p><p>請參閱 <a href="#cost-attribution">CPM資料源的成本分配</a> 的子菜單。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>堅持每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報告系統在每月5號以後關閉。 如果到時未能報告CPM使用情況，則必須將該金額添加到下月的報告中。 比如說10月份用了1000個印，11月份錯過了10月份的報告截止時間，10月份用了1000個印。 在這種情況下，您將報告12月1日至5日的10月和11月總數（2000年）。</p><p><b>提示</b>:您應始終嘗試在下月的第1天至第5天之間報告上個月的CPM使用情況。</p><p>您可以在新日曆月的第5天報告CPM使用情況，但不建議這樣做。 在每月5日之前報告CPM使用情況給Audience Manager檢查和處理資料的時間。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM資料源的成本分配 {#cost-attribution}

在 [!UICONTROL Audience Marketplace] 您必須每月為每個細分市場自行報告印象金額。 我們建議報告 [!DNL CPM] 在段層使用，以便自動完成成本分配。

<!-- marketplace_cpm_billing.xml -->

### 開單摘要 {#billing-summary}

您必須提交 [!DNL CPM] 每個日曆月的第1天至第5天之間的資料饋送印象量。 要正確執行此操作，我們建議您 [報告段級CPM使用情況](#segment-level-report)。

>[!TIP]
>報告時 [!DNL CPM] 在段級的使用情況下，資料饋送級報告部分自動填充相應的使用量。

你需要 [!UICONTROL Report CPM Usage at Data Feed Level]，您必須單獨編譯上一個日曆月內每個訂閱源發送的所有印象，並根據本文中描述的開單分配來報告這些印象。

報告完 [!DNL CPM] 上一個日曆月的編號， [!DNL Adobe] 將執行以下操作：

* 根據 [!DNL CPM] 每個訂閱資料饋送的速率。
* 根據您報告的資料提供商（銷售商）支付的費用 [!DNL CPM] 。

>[!IMPORTANT]
>
>作為買家，所有報告的印象總計必須真實而準確。 如果在每月的第5天之前未報告印象合計，則必須包括下個月未報告月份的合計。

<br> 

## 基於特質資格規則的進貨印象分配 {#assign-impressions}

的 [!UICONTROL Activation] 用例允許您使用相應資料饋送中的特徵在 [段生成器](../../../features/segments/segment-builder.md) 將這些段映射到目標。 布爾運算子 [!UICONTROL AND]。 [!UICONTROL OR], [!UICONTROL NOT] 讓你為特徵和分段資格設定條件。

當你 [在資料饋送級別報告CPM使用情況](#feed-level-report)，您必鬚根據 [!DNL Boolean] 在特徵限定規則中使用的運算子。 下表列出了如何按布爾規則或特性類型正確分配印象。

>[!TIP]
>[報告段級CPM使用情況](#segment-level-report) 使資料饋送級別報告通過Audience Manager自動完成。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則限定邏輯或類型 </th> 
   <th colname="col2" class="entry"> 開單分配 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 和</span> </p> </td> 
   <td colname="col2"> <p>將100%的已傳遞印象合計應用於使用布爾型的基於規則的段中的所有提供程式特徵 <span class="wintitle"> 和</span> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或</span> </p> </td> 
   <td colname="col2"> <p>對使用布爾或條件的基於規則的段中的所有提供程式特徵應用已傳遞印象合計的加權分配。 加權分配採用以下公式計算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>將100%的已傳遞印象合計應用於使用布爾型的基於規則的段中的所有提供程式特徵 <span class="wintitle"> 不</span> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法段 </p> </td> 
   <td colname="col2"> <p>將100%的已傳遞印象總數應用於包含算法特徵的片段中的所有提供者源。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 開單示例 {#billing-examples}

以下示例旨在說明 [!DNL CPM] 使用分配在資料饋送級別完成。

>[!IMPORTANT]
>我們建議你 [報告段級CPM使用情況](#segment-level-report) 而不是自動完成此進程。

讓我們考慮以下情形：

![計費示例](assets/billing-examples.png)

<br> 

### 案例1:具有AND資格規則的細分市場

此段包含來自獨立資料提供程式的3個特徵。 由於分部資格基於 [!UICONTROL AND] 條件是，訪問者必須從所有三種飼料中獲得特徵才能進入該片段。

![](assets/billing-segment-and.png)

與 [!UICONTROL AND] 條件，您必須將該月收到的印象的100%分配給所有三個資料提供程式。 在 [!UICONTROL Audience Marketplace > Payables] 部分，您向每家供應商提供100萬印象。

此示例適用於使用 [!DNL Boolean] [!UICONTROL NOT] 運算子或包含算法特徵的段。

<br> 

### 案例二：具有或資格規則的段

此段包含來自獨立資料提供程式的3個特徵。 由於分部資格基於 [!UICONTROL OR] 條件是，訪問者必須認識到其中至少一種特徵才能進入該片段。

我們無法判斷哪種特質會造成印象，因為資格認定是基於 [!UICONTROL OR] 的子菜單。 因此，在 [!UICONTROL Audience Marketplace > Payables] 部分，您根據特徵群體對每個供應商的總印象進行加權分配。

![計費段或](assets/billing-segment-or.png)

<br> 

### 案例三：具有建模和激活使用案例的段

此示例基於兩個資料源使用案例（建模和激活）描述屬性。 在本示例中，我們查看了兩個資料提供程式，其中包含以下資訊：

![資料饋送](assets/feed-use-cases.png)

在下表中，段X包含兩個特徵，即T1和T2，段規則為T1或T2，其中：

* T1是Data Feed A的一個特徵；
* T2是以Data Feed A和Data Feed B中的第三方特徵為模型的算法特性。

該段映射到一個目標，並且在一個月內為此段輸入1,000,000個印數，使用 [段級報告](#segment-level-report)。

這100萬印象中：

* T1佔Feed A的40%，相當於40萬張印象。
* T2佔Feed A和Feed B的60%，這相當於60萬次印象。

在資料饋送級別，分配印象的方式是：

* Data Feed A從特徵T2（基於資料饋送A和資料饋送B的特徵建模，因此兩者都獲得了印象）和特徵T1（即資料饋送A的特徵）獲得了60萬印象，總計100萬印象。
* Data Feed B從特徵T2獲得600,000個印象（見上面的說明），從特徵T1獲得0個印象。

按資料饋送和使用情形分列的概覽細目如下：

![進給故障](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>對於建模用例，您只應在激活時報告CPM使用情況。 如果只運行模型，但不激活它，則不需要使用情況報告。

<br> 

## 統一費用資料源的計費和印象分配 {#billing-flat-fee}

統一費用資料每月向您支付固定金額，而不管訂閱何時開始或您使用多少印象。 部分月份使用情況或間隔不按比例分攤費用。 與CPM計費一樣，Adobe將為您訂閱的資料源按每月統一費率生成發票和賬單。

比如，假設你決定在月中的飼料中開啟某些特徵 無論您何時開始訂閱或激活特定特徵，您仍將按每月全額收費。
