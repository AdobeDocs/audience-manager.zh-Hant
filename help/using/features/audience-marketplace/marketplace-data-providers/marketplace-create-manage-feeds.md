---
description: 資料饋送需要名稱、說明、資料來源和計畫類型。 動態消息會停用，直到您儲存並啟動動態消息為止。 在「對象市集>我的共用資料」中設定公開或私人資料饋送。 僅供資料銷售者使用。
seo-description: 資料饋送需要名稱、說明、資料來源和計畫類型。 動態消息會停用，直到您儲存並啟動動態消息為止。 在「對象市集>我的共用資料」中設定公開或私人資料饋送。 僅供資料銷售者使用。
seo-title: 建立、定價和管理資料饋送
solution: Audience Manager
title: 建立、定價和管理資料饋送
topic: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
translation-type: tm+mt
source-git-commit: 979c853a3be94f1cda57e4f376d0033d6e8a06a5

---


# 建立、定價和管理資料饋送 {#create-price-and-manage-data-feeds}

## 建立公開或私人資料饋送 {#create-public-private-data-feed}

資料饋送需要名稱、說明、資料來源和計畫類型。 動態消息會停用，直到您儲存並啟動動態消息為止。 在中設定公用或私用資料饋送 **[!UICONTROL Audience Marketplace > My Shared Data]**。 僅供資料銷售者使用。

<!-- t_data_feed.xml -->

您必須擁有管理員權限，才能建立公用或私用資料饋送。
若要建立資料饋送：

1. 按一下 **[!UICONTROL New Data Feed]**.
1. 命名資料饋送。 資料購買者可以根據名稱搜尋您的動態消息。
1. 提供簡短說明（最多255個字元）。

   正確的描述應正確描述您的動態消息。 例如，您可以包含行銷類別、人口統計和地理涵蓋範圍的文字(例如 [!DNL US] 北美地區)。 描述文字是可搜尋的，可協助購買者尋找或評估您的動態消息。 良好的說明是吸引訂閱者加入資料饋送的重要部分。
1. 從選項中選擇資料 **[!UICONTROL Data Source]** 源。 資料饋送僅限單一資料來源。 您無法將多個資料來源指派給相同的資料饋送。

   >[!IMPORTANT]
   >
   >屬於此資料來源的任何目前和未來特徵都會與您的資料購買者共用，做為此動態消息的一部分。

1. 在 [!UICONTROL Plan Types]中，選擇要使用的選項並按一下 **[!UICONTROL Add Plan]**。

   動態消息可包含多個計畫。 計畫可包含多個使用案例。 如需詳細資訊，請 [參閱資料饋送的計畫類型](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)。

1. 按一 **[!UICONTROL Save]** 下以儲存您的資料饋送， *而不* 需加以啟動。
1. 若要儲存並啟用資料饋送：
   1. 將滑桿 **[!UICONTROL Availability]** 移至 **[!UICONTROL Active]**。
   1. 按一下 **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* 無法刪除已儲存和啟用的資料饋送。
   >* 購買者只會看見作用中的動態消息。


### 可選：建立私人資料饋送

在該部 [!UICONTROL Settings] 分中，將滑塊移動到：

* **[!UICONTROL Private]** 和 **[!UICONTROL Branded]**:買方清單 [!UICONTROL Marketplace] 在提供方列中顯示賣方名稱，所有其它資料都隱藏。

* **[!UICONTROL Private]** 和 **[!UICONTROL Unbranded]**:採購者清單僅 [!UICONTROL Marketplace] 會顯示資料饋送名稱和說明。 資料提供者名稱會顯示為 [!UICONTROL Private Seller]。

若要查看私人動態消息對購買者的外觀，請參閱「私人資料動態消息」中的 [購買者區段](../../../features/audience-marketplace/marketplace-private-feeds.md)。

## 停用訂閱者的資料饋送 {#deactivate-data-feed}

身為資 [!UICONTROL Audience Marketplace] 料提供者，您可以撤銷買方對已訂閱資料饋送的存取權。 您可能想從動態消息中移除買家，原因包括延遲付款／不支付費用，或他們不當使用特徵資料。

<!-- marketplace-deactiva4te-subscribers.xml -->

要撤銷訂戶：

1. 在中 [!UICONTROL My Shared Data]尋找訂閱者使用的動態消息。

   >[!NOTE]
   >
   >含逾期帳戶的資料饋送會以三角形／驚嘆號圖示標示。

1. 在欄中， [!UICONTROL Subscribers] 按一下該動態消息的訂閱者計數藍色數字。 這會開啟訂閱詳細資訊頁面。
1. 將滑桿 **[!UICONTROL Subscription]** 移至 **[!UICONTROL Off]**。 這將開啟確認對話框窗口。
1. 在快顯 [!UICONTROL Confirmation] 視窗中，按一 **[!UICONTROL Yes]** 下以停用訂閱，或 **[!UICONTROL Cancel]** 在不變更訂閱的情況下結束。

### 停用訂閱者後會發生什麼

廢止資料饋送的存取權會傳送通知電子郵件給資料購買者帳戶中的所有管理員使用者。 電子郵件包含列出已撤銷特徵的附件。 此清單可協助訂閱者從其區段和模型中尋找和移除停用的特徵。

### 帳單和動態消息停用

在您移除資料饋送的存取權後，訂閱者需負責上個月或目前月份的費用，視您停用動態消息的時間而定。

## 資料饋送的規劃類型 {#plan-types}

[!DNL Plan types] 是資料饋送中的必 [!UICONTROL Audience Marketplace] 要元件。 身為資料提供者，他們可讓您為動態消息建立多個使用案例和價格選項。 此外，為每個資料饋送建立一些計畫也是個不錯的策略。 這可讓購買者在尋找模型資料或傳送至目的地時，有不同的選擇。

[建立要選取的資料饋送](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)[!UICONTROL Plan Types]。

![](assets/plan_types.png)

## 計畫類型和使用案例選項 {#plan-types-use-cases}

<!-- c_feed_options.xml -->

這些設 [!UICONTROL Use Case] 定可讓賣家控制買家使用您資料的方式。

### 區段和重疊

使 **[!UICONTROL Segments and Overlap]** 用案例會建立計畫，讓購買者比較特徵與特 [徵重疊報表中的特徵資料](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)。 此外，購買者可將您的資料新增至區段，並與 [區段對特徵](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)[和區段對區段報表進行比較](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 。

每個資料饋送必須至少包含一個使 [!UICONTROL Segments and Overlap] 用案例。 如果動態消息本身或與其他使用案例結合時不包含使用案例， [!UICONTROL Segments and Overlap] 購買者就無法訂閱資料動態消息中的其他計畫。

重疊比較有助於購買者：

* **** 擴大受眾覆蓋：低重疊顯示您的特徵包含購買者之前所未見的使用者。 因此，購買者可能希望這些特徵將新使用者新增至其受眾區段。
* **** 增強現有受眾：高度重疊表明您的特徵包含的用戶與買家已經知道的用戶相似。 因此，購買者可能希望這些特徵有助於對已開發受眾進行有針對性的漸進改進。

此使用案例的定價如下：

* 單位：固定費用
* 價格：免費($0.00)

### 模型

使用 **[!UICONTROL Modeling]** 案例會建立一個計畫，讓買家透過演算法模型比較您的特 [徵與特徵](../../../features/algorithmic-models/understanding-models.md#understanding-models)。 購買者會檢視模型結果，在您的資料中尋找與自己擁有相似轉換屬性的新受眾。 此使用案例的定價如下：

* 單位：固定費用
* 價格：折扣或市價

### 啟用

使用 **[!UICONTROL Activation]** 案例可讓購買者將資料傳送 [至目的地](../../../features/destinations/destinations.md)。 在此使用案例中，購買者無法比較重疊報表或演算法模型中的資料。 此使用案例的定價如下：

* 單位： [!DNL CPM]
* 價格：市 [!DNL CPM] 場率

## 帳單和價格選項 {#billing}

帳單和價格選項可控制購買者為您的資料付款的方式。

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
   <td colname="col2"> <b><span class="uicontrol"> 「月繳型</span></b> 」是唯一選項。 帳單週期於每月十日結束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 單位</span></b> </td> 
   <td colname="col2">以CPM費率或固定費用向資料購買者收費。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 透過CPM定價，資料購買者必須自行報告使用情形。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">由於固定費用定價，資料購買者不會報告使用情形，因為他們收取固定費率。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 價格</span></b> </td>
   <td colname="col2"> 賣方以CPM費率或固定費用價格向買方收取的金額（以美元計）。 </td>
  </tr> 
 </tbody> 
</table>

## 計畫說明 {#plan-notes}

在欄位 **[!UICONTROL Additional Notes]** 中，請花一些時間來說明動態消息中的每個資料計畫。 簡短的簡短說明有助於購買者瞭解資料饋送中每個計畫的內容或目的。 購買者可在搜尋或評估新資料來源時，閱讀資料饋送和計畫說明。

## 管理私人資料饋送請求 {#manage-private-requests}

提供者工作流程，以管理來自購買者的私人饋送請求。

要複查、批准或拒絕採購員請求，請轉至 [!UICONTROL My Shared Data] 和：

<!-- t_private_feed_workflows.xml -->

1. 按一下私人資料饋送的名稱。
2. 按一 **[!UICONTROL Access Requests]** 下以檢閱想要存取您資料饋送的所有購買者。
3. 在每個 [!UICONTROL Allow Access] 請求方塊的區段中，按一下核取標籤以核准請求，或按X以拒絕存取。
4. 在確認彈出式視窗中確認或取消您選取的動作。

## 資料提供者的折扣 {#discounts}

在中 [!UICONTROL Audience Marketplace]，折扣可讓您降低個別訂閱者的資料饋送發佈價格。 您可以為已提交訂閱要求的訂閱者或已要求資料饋送詳細資訊的訂閱者提供折扣。 折扣適用於 [!DNL CPM] 固定費率饋送。 當您想要為新客戶提供訂閱獎勵或獎勵客戶忠誠度時，折扣會很有幫助。

## 將折扣套用至資料饋送 {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

若要折扣動態消息，請在折扣欄位中新增折扣金額%，並確認您的變更。 資料提供者可從下列其中一種方式，將資料饋送 [!UICONTROL Audience Marketplace] 折扣在：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在這些範例中，賣家已將資料饋送的折扣加 [!UICONTROL Software Audience] 入10%。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 檢閱折扣動態消息 {#review-discounted-feeds}

資料供應商可在中查看其所有訂閱者和折扣動態消息 **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**。

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)

