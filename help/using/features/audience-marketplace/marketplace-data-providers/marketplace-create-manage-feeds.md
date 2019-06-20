---
description: 資料饋送需要名稱、說明、資料來源和計劃類型。動態消息會停用，直到您儲存並啓動動態消息為止。在Audience Marketplace> My Shared Data中設定公開或私人資料饋送。僅適用於資料賣方。
seo-description: 資料饋送需要名稱、說明、資料來源和計劃類型。動態消息會停用，直到您儲存並啓動動態消息為止。在Audience Marketplace> My Shared Data中設定公開或私人資料饋送。僅適用於資料賣方。
seo-title: 建立、價格和管理資料饋送
solution: Audience Manager
title: 建立、價格和管理資料饋送
topic: DIL API
uuid: e28c20b3-33fc-4485-1ee9-8530d126f741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

資料饋送需要名稱、說明、資料來源和計劃類型。動態消息會停用，直到您儲存並啓動動態消息為止。Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. 僅適用於資料賣方。

## Create a Public or Private Data Feed {#create-public-private-data-feed}

資料饋送需要名稱、說明、資料來源和計劃類型。動態消息會停用，直到您儲存並啓動動態消息為止。Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. 僅適用於資料賣方。

<!-- t_data_feed.xml -->

您必須擁有管理員權限才能建立公開或私人資料饋送。
若要建立資料饋送：

1. Click **[!UICONTROL New Data Feed]**.
1. 命名資料饋送。資料購買者可以根據名稱搜尋您的動態消息。
1. 提供簡短說明(最多255個字元)。

   良好描述應正確描述動態消息。For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). 說明文字可供搜尋，並協助購買者找到或評估您的動態消息。好的說明是吸引用戶資料饋送的重要部分。
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >作為此動態消息的一部分，任何屬於此資料來源的目前及未來特徵都會與您的資料購買者共用。

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   摘要可以包含多個計劃。計劃可包含多個使用案例。For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. 若要儲存並啓用資料饋送：
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Click **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* 無法刪除儲存和啓動的資料饋送。
   >* 購買者只會看到作用中的動態消息。


### 可選：建立私人資料饋送

[!UICONTROL Settings] 在區段中，將滑桿移至：

* **[!UICONTROL Private]** and **[!UICONTROL Branded]**：購買者 [!UICONTROL Marketplace] 清單會顯示供應商欄中的賣方名稱，並隱藏所有其他資料。

* **[!UICONTROL Private]** and **[!UICONTROL Unbranded]**：購買者 [!UICONTROL Marketplace] 清單只會顯示資料饋送名稱和說明。The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_贊_ this]
>
>* [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)


## 停用訂閱者的資料饋送 {#deactivate-data-feed}

[!UICONTROL Audience Marketplace] 作為資料供應商，您可以撤銷買家對訂閱資料饋送的存取權。您可能希望將買家從動態消息中移除，例如逾期支付/未付款或他們未正確使用特徵資料。

<!-- marketplace-deactiva4te-subscribers.xml -->

若要撤銷訂閱者：

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >包含逾期帳戶的資料饋送會以三角形/驚嘆號圖示標示。

1. [!UICONTROL Subscribers] 在欄中，按一下該動態消息訂閱者的藍色數字。如此會開啓訂閱詳細資訊頁面。
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. 如此會開啓確認對話方塊視窗。
1. [!UICONTROL Confirmation] 在快顯視窗中，按一下以 **[!UICONTROL Yes]** 停用訂閱或 **[!UICONTROL Cancel]** 結束訂閱，而不會變更訂閱。

### 停用訂閱者後會發生甚麼事

撤銷資料饋送的存取權會傳送通知電子郵件給資料買家帳戶中的所有管理員使用者。電子郵件包含一個附件，列出廢止的特性。此清單可協助用戶尋找並移除區段和模型中停用的特性。

### 計費和動態消息停用

移除資料饋送的存取權後，用戶就會對先前或當月的費用負責，視您停用動態消息而定。

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] 是 [!UICONTROL Audience Marketplace] 資料饋送中的重要元件。作為資料供應商，它們可讓您為您的饋送建立多個使用案例和價格選項。此外，為每個資料饋送建立一些計劃都是很好的策略。這可為購買者提供不同選項，供他們從尋找資料到模型或傳送至目的地時選擇。

[建立要選取的資料饋送](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)[!UICONTROL Plan Types]。

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case] 這些設定可讓賣家控制買家如何使用您的資料。

### 區段和重疊

**[!UICONTROL Segments and Overlap]** 使用案例建立了一個計劃，可讓買家比較 [特徵至特徵重疊報表中特徵資料](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)。Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

重疊比較可協助購買者：

* **擴大受眾覆蓋面：** 低重疊表示您的特性包含購買者之前未見過的使用者。因此，買家可能希望這些特性能新增使用者至他們的受眾細分。
* **增強現有受眾：** 重疊表示您的特徵包含類似購買者已知的使用者。因此，買家可能希望這些特性能夠為開發受眾帶來有針對性的漸進式改進。

請依照下列使用案例來定價：

* 度量單位：費用平平
* 價格：免費($0.00)

### 模型化

**[!UICONTROL Modeling]** 使用案例建立了一個計劃，可讓購買者使用 [演算法模型比較您的特徵與專家](../../../features/algorithmic-models/understanding-models.md#understanding-models)。購買者會查看模型結果，在共用類似轉換屬性的資料中尋找新的受眾。請依照下列使用案例來定價：

* 度量單位：費用平平
* 價格：折扣或市價價格

### 啟用

**[!UICONTROL Activation]** 使用案例可讓買家將資料傳送 [至目的地](../../../features/destinations/destinations.md)。使用此使用案例，購買者無法與重疊報表或演算法模型中的資料進行比較。請依照下列使用案例來定價：

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

帳單和價格選項可控制買家如何支付您的資料。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 帳單週期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 「月費」是</span></b> 唯一的選項。帳單週期會於每月10日結束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 度量單位</span></b> </td> 
   <td colname="col2">以CPM費率或固定費用向資料購買者收費。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 有了CPM定價，資料購買者就需要自行使用報告。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Wit固定費用價格，資料購買者不會報告使用量，因為他們收取固定費率。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 價格</span></b> </td>
   <td colname="col2"> 賣方向購買者收取CPM費率或平費價格(以美元計)。 </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

**[!UICONTROL Additional Notes]** 在欄位中，需要一些時間來描述動態消息中的每個資料計劃。好的簡短說明有助於買家瞭解資料饋送中每個計劃的內容或目的。購買者可以在搜尋或評估新資料來源時閱讀資料饋送和計劃說明。

## Manage Private Data Feed Requests {#manage-private-requests}

管理買家私人饋送要求的供應商工作流程。

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. 按一下私人資料饋送的名稱。
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. 確認或取消確認彈出畫面中所選取的動作。

>[!MORE_贊_ this]
>
>* [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. 您可以為已提交訂閱請求的用戶或請求資料饋送詳細資訊的訂閱者提供折扣。Discounts apply to [!DNL CPM] and flat rate feeds. 當您想要為新客戶提供訂閱獎勵或獎勵客戶忠誠度時，折扣可以派上用場。

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

若要折扣一個動態消息，請將折扣金額加至折扣欄位，並確認您的變更。Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)