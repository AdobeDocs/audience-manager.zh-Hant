---
description: 私人資料摘要選項可讓提供者限制購買者存取其資料。 資料提供者和購買者應先檢閱此資訊，再建立和訂閱私人資料摘要。
seo-description: 私人資料摘要選項可讓提供者限制購買者存取其資料。 資料提供者和購買者應先檢閱此資訊，再建立和訂閱私人資料摘要。
seo-title: 私人資料摘要
solution: Audience Manager
title: 私人資料摘要
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: 訪客交易市場
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# 私人資料摘要 {#private-data-feeds}

私人資料摘要選項可讓提供者限制購買者存取其資料。 資料提供者和購買者應先檢閱此資訊，再建立和訂閱私人資料摘要。

<!-- c_marketplace_privatefeed.xml -->

## 提供程式的專用資料饋送{#private-data-feeds-providers}

身為提供者，您的資料摘要可以是公開或私人的。 私人資料摘要可讓您限制購買者對您資料的存取，包括資料銷售者的名稱。 您可能想要建立私人資料摘要，以提供特別優惠、折扣，或在隱私權和存取控制很重要時提供。 透過私人資料摘要，您可以審核及核准購買者請求。 核准請求後，摘要看起來就像是提供給購買者的公開資料摘要。 您可以在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中檢視及管理所有摘要。 如下所示，此類型的摘要在狀態欄中標示為「私人」。

![](assets/my_shared_data.png)

### 管理摘要請求

按一下[!UICONTROL My Shared Data]中私人資料摘要的名稱，會前往包含數個索引標籤的頁面。 按一下標籤以管理您的私人資料摘要請求。

![](assets/shared_data_tabs.png)

下表定義了每個操作頁簽提供的角色或函式。

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 定位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前訂閱者</span></b> </p> </td> 
   <td colname="col2"> <p>列出已訂閱私人資料摘要的已核准買家。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 潛在訂閱者</span></b> </p> </td> 
   <td colname="col2"> <p>列出尚未訂閱私人資料摘要的已核准買家。 </p> <p>核准可讓購買者以公開的方式檢視資料摘要。 這可讓使用者在訂閱前檢閱及評估您的摘要。 您也可以為列為潛在訂閱者的買家提供資料饋送優惠。 購買者訂閱後，其設定檔會移至<b><span class="uicontrol">目前訂閱者</span></b>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 存取請求</span></b> </p> </td>
   <td colname="col2"> <p>列出私人資料摘要的新訂閱請求。 按一下此標籤可複查、批准或拒絕採購員請求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">已核准的購買者移至<b><span class="uicontrol">潛在訂閱者</span></b>。 </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">已拒絕的買家移至<b><span class="uicontrol">拒絕訪問</span></b>。 </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 詳細資料請求</span></b> </p> </td>
   <td colname="col2"> <p>列出尚未訂閱資料摘要，且已請求您摘要的詳細資訊的已核准買家。 </p> <p>核准可讓購買者以公開的方式檢視資料摘要。 這可讓使用者在訂閱前檢閱及評估您的摘要。 您也可以為要求存取權的買家提供資料饋送的折扣。 響應詳細資訊請求會從此頁簽中刪除購買者配置檔案。 如果尚未訂閱，則購買者配置檔案仍在<b><span class="uicontrol">潛在訂閱者</span></b>中。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 拒絕訪問</span></b> </p> </td> 
   <td colname="col2"> <p>列出私人資料摘要遭拒的訂閱請求。 </p> <p>要重新批准被拒絕的買家，請將<span class="wintitle">拒絕狀態</span>更改為<b><span class="uicontrol">允許</span></b>。 這會將購買者移至<b><span class="uicontrol">潛在訂閱者</span></b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 後續步驟

下列檔案可協助您開始使用私人資料摘要。

* [建立公開或私人資料摘要](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [檢閱、核准或拒絕私人摘要請求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [購買者的私人資料摘要](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 購買者的私人資料饋送{#private-data-feeds-for-buyers}

私人資料饋送以購買者的身分，如同任何其他選件一樣出現在[Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)中。 但在此情況下，摘要清單不會顯示特徵、不重複使用者和使用者重疊的摘要資訊。 此外，資料賣方還可以選擇在[!UICONTROL Marketplace]清單的[!UICONTROL Provider]列中顯示或隱藏其名稱。 賣方核准您的訂閱請求後，私人摘要中的所有資料都可供您使用（其運作方式與公開摘要類似）。 以下的[!UICONTROL Marketplace]範例列出您作為購買者可使用的3種不同摘要類型。

![](assets/buyer_marketplace.png)

摘要類型包括：

此表格說明這些不同摘要類型如何顯示或隱藏資料。

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 摘要類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 公開</span></b> </p> </td> 
   <td colname="col2"> <p>提供者的名稱、特徵和不重複資料會顯示在清單中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 無品牌的私有</span></b> </p> </td> 
   <td colname="col2"> <p>提供者的名稱設為「私人賣家」，您就看不到特徵計數、唯一資料和特徵重疊資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 具有品牌的私有</span></b> </p> </td> 
   <td colname="col2"> <p>提供者的名稱會顯示在清單中，但您看不到特徵計數、唯一資料和特徵重疊資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 後續步驟

請參閱  [訂閱私人資料饋送](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 以要求存取權。

## 如何設定資料提供者與資料購買者的共用關係{#set-up-sharing-relationship}

### 步驟1 — 啟用 — 資料提供者與資料購買者

此程式的第一步需要Adobe諮詢或客戶服務的介入。 資料提供者和資料購買者應聯絡Adobe諮詢或客戶服務以要求啟用。

### 步驟2 — 資料提供者 — 建立新資料來源

在您的Audience Manager帳戶中，使用以下項目建立新的Cookie資料來源：

* **Audience Manager** ID作為傳入金鑰；
* 已勾選「**共用已啟用**」選項。

![](assets/create-datasource.png)

按一下&#x200B;**Save**&#x200B;後，會在&#x200B;**特徵儲存>第三方資料**&#x200B;中自動建立新的子資料夾。

![](assets/folder-structure.png)

### 步驟3 — 資料提供者 — 識別要共用的特徵

在此步驟中，您會識別要與合作夥伴共用的特徵。 您可以建立新特徵或編輯現有特徵。 無論如何，您都需要特徵：

* 與您在步驟2中建立的資料來源建立關聯。
* 儲存在新建立的子資料夾中，位於第三方資料下。

深入閱讀[建立特徵](/help/using/features/traits/create-onboarded-rule-based-traits.md)和[編輯特徵](/help/using/features/traits/manage-trait-rules.md#edit-trait)的相關資訊。

### 步驟4 — 資料提供者 — 建立資料摘要

接下來，建立資料摘要，與資料購買者共用您的特徵。 如需如何建立資料摘要的指示，請參閱[建立公開或私人資料摘要](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md)。

>[!IMPORTANT]
>
>在「設定」中，選取「私人」選項。 如果您將此欄位設為「公用」，任何Audience Marketplace客戶都可訂閱您的摘要。

![](assets/create-data-feed.png)

### 步驟5 — 資料購買者 — 請求存取

前往&#x200B;**Audience Marketplace> Marketplace**。 搜尋資料提供者在上一步驟中建立的資料摘要。 按一下「**請求訪問**」。 來自資料提供者端的指定聯絡人現在會收到電子郵件通知。 另請參閱[訂閱私人資料饋送](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

### 步驟6 — 資料提供者 — 授予存取權

前往「**Audience Marketplace>我的共用資料**」，並搜尋您在步驟4建立的摘要。 按一下進入新的存取請求，然後按一下「允許存取」**以核准請求。**&#x200B;另請參閱[審核、批准或拒絕私人摘要請求](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)。

### 步驟7 — 資料購買者 — 開啟訂閱

資料提供者授與資料摘要的存取權後，您就可以在&#x200B;**Audience Marketplace> Marketplace**&#x200B;中查看帳戶中的摘要。 查看詳細資訊，開啟「Subscription（訂閱）」按鈕，然後按一下「**Review &amp; Subscribe（查看和訂閱）」**。 如需在何處尋找第三方特徵的詳細資訊，請參閱[訂閱資料摘要的儲存](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee)。

請注意，這些特徵只能在資料提供者的帳戶中編輯。
