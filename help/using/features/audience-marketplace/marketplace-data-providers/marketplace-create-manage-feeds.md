---
description: 資料摘要需要名稱、說明、資料來源和規劃類型。 摘要會停用，直到您儲存並啟動摘要為止。 在「Audience Marketplace>我的共用資料」中設定公開或私人資料摘要。 僅供資料銷售者使用。
seo-description: 資料摘要需要名稱、說明、資料來源和規劃類型。 摘要會停用，直到您儲存並啟動摘要為止。 在「Audience Marketplace>我的共用資料」中設定公開或私人資料摘要。 僅供資料銷售者使用。
seo-title: 建立、定價和管理資料摘要
solution: Audience Manager
title: 建立、定價和管理資料摘要
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: 訪客交易市場
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# 建立、定價和管理資料摘要 {#create-price-and-manage-data-feeds}

## 建立公用或專用資料饋送{#create-public-private-data-feed}

資料摘要需要名稱、說明、資料來源和規劃類型。 摘要會停用，直到您儲存並啟動摘要為止。 在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中設定公開或私人資料饋送。 僅供資料銷售者使用。

<!-- t_data_feed.xml -->

您必須擁有管理員權限，才能建立公開或私人資料摘要。
若要建立資料摘要：

1. 按一下 **[!UICONTROL New Data Feed]**.
1. 為資料摘要命名。 資料購買者可以根據名稱搜尋您的摘要。
1. 提供簡短說明（最多255個字元）。

   好的說明應能準確描述您的摘要。 例如，您可以包含行銷類別、人口統計和地理涵蓋範圍的文字（例如[!DNL US]或北美）。 說明文字可供搜尋，並可協助購買者尋找或評估您的摘要。 良好的說明是吸引資料饋送的訂閱者的重要部分。
1. 從&#x200B;**[!UICONTROL Data Source]**&#x200B;選項中選擇資料源。 資料摘要僅限於單一資料來源。 您無法指派多個資料來源至相同的資料摘要。

   >[!IMPORTANT]
   >
   >屬於此資料來源的任何目前和未來特徵，都會與您的資料購買者共用，作為此摘要的一部分。

1. 在[!UICONTROL Plan Types]中，選擇要使用的選項，然後按一下&#x200B;**[!UICONTROL Add Plan]**。

   摘要可包含多個計畫。 計畫可包含多個使用案例。 如需詳細資訊，請參閱[資料摘要的計畫類型](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)。

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以儲存資料摘要&#x200B;*而不要*&#x200B;啟動。
1. 若要儲存及啟用資料摘要：
   1. 將&#x200B;**[!UICONTROL Availability]**&#x200B;滑桿移至&#x200B;**[!UICONTROL Active]**。
   1. 按一下 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* 無法刪除儲存和啟用的資料摘要。
   >* 買家只看到活動摘要。


### 可選：建立私人資料摘要

在[!UICONTROL Settings]區段中，將滑桿移至：

* **[!UICONTROL Private]** 和 **[!UICONTROL Branded]**:買方清單在 [!UICONTROL Marketplace] 提供方列中顯示賣方的名稱，並隱藏所有其他資料。

* **[!UICONTROL Private]** 和 **[!UICONTROL Unbranded]**:購買者清單 [!UICONTROL Marketplace] 只會顯示資料摘要名稱和說明。資料提供程式名稱顯示為[!UICONTROL Private Seller]。

若要查看私人摘要對購買者的看法，請參閱「私人資料摘要」中的「購買者」區段[](../../../features/audience-marketplace/marketplace-private-feeds.md)。

## 停用訂閱者的資料饋送 {#deactivate-data-feed}

作為[!UICONTROL Audience Marketplace]資料提供者，您可以撤銷購買者對訂閱資料饋送的存取權。 您可能因為延遲付款/不支付費用等原因，或買家不當使用特徵資料，而想從摘要中移除買家。

<!-- marketplace-deactiva4te-subscribers.xml -->

要撤消訂閱者，請執行以下操作：

1. 在[!UICONTROL My Shared Data]中，查找訂閱者正在使用的饋送。

   >[!NOTE]
   >
   >含有逾期帳戶的資料摘要會以三角形/驚嘆號圖示標籤。

1. 在[!UICONTROL Subscribers]欄中，按一下會計算該摘要訂閱者的藍色數字。 這會開啟訂閱詳細資訊頁面。
1. 將&#x200B;**[!UICONTROL Subscription]**&#x200B;滑桿移至&#x200B;**[!UICONTROL Off]**。 這會開啟確認對話方塊視窗。
1. 在[!UICONTROL Confirmation]快顯視窗中，按一下&#x200B;**[!UICONTROL Yes]**&#x200B;停用訂閱，或按一下&#x200B;**[!UICONTROL Cancel]**&#x200B;結束而不變更訂閱。

### 停用訂閱者後會發生什麼事

撤銷資料摘要的存取權會傳送通知電子郵件給資料購買者帳戶中的所有管理員使用者。 電子郵件包含列出已撤銷特徵的附件。 此清單可協助訂閱者從其區段和模型中尋找和移除停用的特徵。

### 帳單和摘要停用

移除資料摘要的存取權後，訂閱者需根據您停用摘要的時間，對前一個月或本月的費用負責。

## 資料摘要的規劃類型{#plan-types}

[!DNL Plan types] 是資料摘要中的必 [!UICONTROL Audience Marketplace] 要元件。資料提供者可讓您為摘要建立多個使用案例和價格選項。 此外，為每個資料摘要建立一些計畫，可能是個不錯的策略。 這可讓購買者在尋找資料以建立模型或傳送至目的地時，有不同的選擇。

[建立要選取](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) 的資料饋 [!UICONTROL Plan Types]送。

![](assets/plan_types.png)

## 計畫類型和使用案例選項{#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case]設定可讓賣家控制買家使用您資料的方式。

### 區段和重疊

**[!UICONTROL Segments and Overlap]**&#x200B;使用案例會建立一個計畫，讓購買者可以比較[trait-to-trait重疊報表](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)中的特徵資料。 此外，購買者可將您的資料新增至區段，並與[segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)和[segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md)報表進行比較。

每個資料摘要至少必須包含一個[!UICONTROL Segments and Overlap]使用案例。 如果摘要本身或與其他使用案例結合時未包含[!UICONTROL Segments and Overlap]使用案例，則資料摘要中的購買者無法訂閱其他計畫。

重疊比較可協助購買者：

* **延伸受眾觸及：** 重疊程度低，表示您的特徵包含購買者以前從未見過的使用者。因此，買家可能會想要這些特徵將新使用者新增至其受眾區段。
* **增強現有對象：** 高重疊表示您的特徵包含的使用者與購買者已知的使用者類似。因此，購買者可能希望這些特徵有助於針對已開發受眾進行有針對性的漸進改善。

此使用案例的價格如下：

* 單位：固定費用
* 價格：免費（0.00美元）

### 模型

**[!UICONTROL Modeling]**&#x200B;使用案例會建立計畫，讓購買者透過[演算法模型](../../../features/algorithmic-models/understanding-models.md#understanding-models)來比較您的特徵與其特徵。 購買者可查看模型結果，在您的資料中尋找與自己共用類似轉換屬性的新對象。 此使用案例的價格如下：

* 單位：固定費用
* 價格：折扣或市價

### 啟用

**[!UICONTROL Activation]**&#x200B;使用案例可讓購買者將資料傳送至[destination](../../../features/destinations/destinations.md)。 透過此使用案例，購買者無法比較含有重疊報表或演算法模型的資料。 此使用案例的價格如下：

* 單位：[!DNL CPM]
* 價格：[!DNL CPM]市場匯率

## 帳單和價格選項 {#billing}

帳單和價格選項控制購買者如何為您的資料付費。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 計費週期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 每月在</span></b> 阿雷爾西是唯一的選擇。帳單週期於每月第10天結束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 單位</span></b> </td> 
   <td colname="col2">以CPM費率或固定費用向資料購買者收費。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 透過CPM定價，資料購買者必須自行報告使用狀況。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">由於費用定價固定，資料購買者不會報告使用情況，因為他們收取固定費率。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 價格</span></b> </td>
   <td colname="col2"> 賣方以CPM費率或固定費用價格（以美元計）向買方收費的金額。 </td>
  </tr> 
 </tbody> 
</table>

## 計畫說明{#plan-notes}

在&#x200B;**[!UICONTROL Additional Notes]**&#x200B;欄位中，花一些時間說明摘要中的每個資料計畫。 簡短的說明可協助購買者了解資料摘要中每個計畫的內容或用途。 購買者在搜尋或評估新資料來源時，可以閱讀資料摘要和計畫說明。

## 管理私人資料摘要請求{#manage-private-requests}

管理買家私人摘要請求的提供者工作流程。

要複查、批准或拒絕採購員請求，請轉至[!UICONTROL My Shared Data]並：

<!-- t_private_feed_workflows.xml -->

1. 按一下私人資料摘要的名稱。
2. 按一下&#x200B;**[!UICONTROL Access Requests]**&#x200B;以檢閱所有想要存取您資料摘要的購買者。
3. 在每個請求框的[!UICONTROL Allow Access]部分，按一下複選標籤以批准請求，或按X拒絕訪問。
4. 在確認快顯視窗中確認或取消您選取的動作。

## 資料提供者優惠 {#discounts}

在[!UICONTROL Audience Marketplace]中，折扣可讓您降低個別訂閱者的資料摘要發佈價格。 您可以為已提交訂閱請求的訂閱者或已請求資料摘要詳細資料的訂閱者提供折扣。 折扣適用於[!DNL CPM]和固定費率饋送。 如果您想要為新客戶提供訂閱獎勵或獎勵客戶忠誠度，折扣將有所幫助。

## 對資料摘要{#apply-discounts}套用折扣

<!-- marketplace-seller-discounts.xml -->

若要折扣摘要，請將折扣金額以%的形式新增至折扣欄位，並確認您的變更。 資料提供者可以從以下任一點折扣[!UICONTROL Audience Marketplace]中的資料饋送：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在這些範例中，賣方已將10%的折扣加入[!UICONTROL Software Audience]資料摘要中。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 檢閱折扣摘要{#review-discounted-feeds}

資料提供者可在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**&#x200B;中查看其所有訂閱者和折扣摘要。

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)

