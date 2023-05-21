---
description: 私有資料饋送是允許提供方限制買方訪問其資料的選項。 資料提供商和購買者應在建立和訂閱私有資料源之前查看此資訊。
seo-description: A private data feed is an option that lets providers limit buyer access to their data. Data providers and buyers should review this information before creating and subscribing to private data feeds.
seo-title: Private Data Feeds
solution: Audience Manager
title: 私人資料摘要
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 1%

---

# 私人資料摘要 {#private-data-feeds}

私有資料饋送是允許提供方限制買方訪問其資料的選項。 資料提供商和購買者應在建立和訂閱私有資料源之前查看此資訊。

<!-- c_marketplace_privatefeed.xml -->

## 提供程式的專用資料源 {#private-data-feeds-providers}

作為提供程式，您的資料源可以是公共的或私有的。 私有資料饋送允許您限制買方訪問您的資料，包括資料銷售方的名稱。 您可能希望建立專用資料源以提供特殊交易、折扣，或在隱私和訪問控制重要時。 使用私有資料源，您可以複查和批准採購員請求。 在您批准請求後，該源看起來就像是向買方提供的公共資料源。 您可以在中查看和管理所有源 **[!UICONTROL Audience Marketplace > My Shared Data]**。 如下所示，此類型的源在狀態列中標籤為「專用」。

![](assets/my_shared_data.png)

### 管理源請求

按一下來自的專用資料源的名稱 [!UICONTROL My Shared Data] 將您帶到包含多個頁籤的頁面。 按一下頁籤以管理您的專用資料饋送請求。

![](assets/shared_data_tabs.png)

下表定義了每個操作頁籤提供的角色或函式。

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 定位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 當前訂閱者</span></b> </p> </td> 
   <td colname="col2"> <p>列出已訂閱私人資料源的已批准買家。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 潛在訂戶</span></b> </p> </td> 
   <td colname="col2"> <p>列出尚未訂閱私人資料源的已批准買家。 </p> <p>審批允許買家查看資料源，就像它是公開的。 這使他們有機會在訂閱之前查看和評估您的訂閱源。 您還可以為列為潛在訂閱者的買家提供資料源折扣。 一旦買家訂購，他們的個人資料將移到 <b><span class="uicontrol"> 當前訂閱者</span></b>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 訪問請求</span></b> </p> </td>
   <td colname="col2"> <p>列出專用資料饋送的新訂閱請求。 按一下此標籤可複查、批准或拒絕採購員請求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">批准的採購員移至 <b><span class="uicontrol"> 潛在訂戶</span></b>。 </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">已拒絕的採購員移至 <b><span class="uicontrol"> 拒絕訪問</span></b>。 </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 詳細資訊請求</span></b> </p> </td>
   <td colname="col2"> <p>列出尚未訂閱資料源且已請求有關您的源的詳細資訊的已批准買家。 </p> <p>審批允許買家查看資料源，就像它是公開的。 這使他們有機會在訂閱之前查看和評估您的訂閱源。 您還可以為請求訪問的買家提供資料源折扣。 響應詳細資訊請求將採購員配置檔案從此標籤中刪除。 如果他們尚未訂閱，則採購員配置檔案仍在 <b><span class="uicontrol"> 潛在訂戶</span></b>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 拒絕訪問</span></b> </p> </td> 
   <td colname="col2"> <p>列出拒絕的專用資料饋送訂閱請求。 </p> <p>要重新批准被拒絕的買家，請更改 <span class="wintitle"> 拒絕狀態</span> 至 <b><span class="uicontrol"> 允許</span></b>。 這會將買方移至 <b><span class="uicontrol"> 潛在訂戶</span></b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 後續步驟

以下文檔可幫助您開始使用專用資料源。

* [建立公共或專用資料源](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [審閱、批准或拒絕私有源請求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [採購員專用資料源](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 採購員專用資料源 {#private-data-feeds-for-buyers}

作為採購員，私有資料源顯示在 [市場](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) 和其他任何提議一樣。 但是，在這種情況下，源清單不顯示特徵、唯一用戶和用戶重疊的摘要資訊。 此外，資料銷售者可以選擇在 [!UICONTROL Provider] 列 [!UICONTROL Marketplace] 清單框。 賣方批准您的訂閱請求後，您就可以使用私有訂閱源中的所有資料（它就像公共訂閱源一樣工作）。 的 [!UICONTROL Marketplace] 下面的示例列出了作為採購員可供您使用的3種不同的進貨類型。

![](assets/buyer_marketplace.png)

源類型包括：

該表說明了這些不同的饋送類型如何顯示或隱藏資料。

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 摘要類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 公共</span></b> </p> </td> 
   <td colname="col2"> <p>提供程式的名稱、特性和唯一資料將顯示在清單中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 無品牌的私有</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名稱設定為「私人銷售商」，您看不到特性計數、唯一資料和特性重疊資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 具有品牌的私有</span></b> </p> </td> 
   <td colname="col2"> <p>提供程式的名稱顯示在清單中，但您看不到特徵計數、唯一資料和特徵重疊資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 後續步驟

請參閱 [訂閱專用資料源](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 請求訪問。

## 如何建立資料提供者與資料購買者的共用關係 {#set-up-sharing-relationship}

### 步驟1 — 支援 — 資料提供商和資料購買者

該流程的第一步需要Adobe咨詢或客戶服務部門的干預。 資料提供商和資料購買者應聯繫Adobe咨詢或客戶服務部門以請求支援。

### 步驟2 — 資料提供程式 — 建立新資料源

在您的Audience Manager帳戶中，使用以下項建立新Cookie資料源：

* **Audience ManagerID** 作為入站密鑰；
* 的 **已啟用共用** 選項。

![](assets/create-datasource.png)

按一下後 **保存**，在中自動建立新子資料夾 **Traits儲存>第三方資料**。

![](assets/folder-structure.png)

### 步驟3 — 資料提供程式 — 確定共用的特徵

在此步驟中，您將確定要與合作夥伴共用的特徵。 您可以建立新特徵或編輯現有特徵。 無論如何，你需要這些特徵：

* 要與作為步驟2一部分建立的資料源關聯。
* 要儲存在新建立的子資料夾中，位於第三方資料下。

閱讀有關 [創造性狀](/help/using/features/traits/create-onboarded-rule-based-traits.md) 和 [編輯特性](/help/using/features/traits/manage-trait-rules.md#edit-trait)。

### 步驟4 — 資料提供程式 — 建立資料饋送

接下來，建立一個資料饋送，以與資料購買者共用您的特性。 請參閱 [建立公共或專用資料源](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) 有關如何建立資料饋送的說明。

>[!IMPORTANT]
>
>在設定中，選擇專用選項。 如果將此欄位設定為「公用」，則任何Audience Marketplace客戶都可以訂閱您的訂閱源。

![](assets/create-data-feed.png)

### 步驟5 — 資料採購員 — 請求訪問

轉到 **Audience Marketplace>市場**。 搜索資料提供程式在上一步中建立的資料饋送。 按一下 **請求訪問**。 資料提供方的指定聯繫人現在將收到電子郵件通知。 另請參見 [訂閱專用資料源](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

### 步驟6 — 資料提供程式 — 授予訪問權限

轉到 **Audience Marketplace>我的共用資料** 並搜索在步驟4中建立的源。 按一下新訪問請求，然後按一下 **允許訪問** 以批准請求。 另請參見 [審閱、批准或拒絕私有源請求](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)。

### 步驟7 — 資料購買者 — 開啟訂閱

在資料提供程式授予對資料源的訪問權後，您可以在中查看帳戶中的源 **Audience Marketplace>市場**。 查看詳細資訊，開啟「訂閱」按鈕，然後按一下 **審閱和訂閱**。 請參閱 [訂閱資料源的儲存](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) 關於在哪裡找到第三方特徵的資訊。

請注意，這些特徵只能在資料提供程式的帳戶中編輯。
