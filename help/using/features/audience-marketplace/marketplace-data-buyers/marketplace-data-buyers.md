---
description: 要從Audience Manager內購買第三方資料的資料購買者的概述和工作流
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: 適用於資料購買者的 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] 用於資料購買者 {#audience-marketplace-for-data-buyers}

要從內部購買第三方資料的資料購買者的概述和工作流 [!DNL Audience Manager]。

>[!NOTE]
>[基於角色的權限](../../../reporting/reports-dashboard.md) 控制訪問 [!UICONTROL Audience Marketplace] 功能。
>
>* 管理員可以建立資料源、管理訂閱者和訂閱資料源。
>* 用戶只能搜索和查看源。


## 的 [!UICONTROL Marketplace]:關於 {#about-marketplace}

的 [!UICONTROL Marketplace] 是 [!DNL Audience Manager] 用於列出可訂閱的資料源的資料購買者的功能。 它列出了平價， [!DNL CPM]和專用資料源。 這些源由使用 [!DNL Audience Manager] 銷售資料。

在 [!UICONTROL Marketplace]，報告工具使您能夠跟蹤訂閱源的使用情況和 [!UICONTROL traits] 以及訂閱資料源中的資料。 最後， [!UICONTROL Audience Marketplace]。 [!DNL Adobe] 支付發票和費用(儘管您在訂閱 [!DNL CPM] 進紙)。 這些功能使您能夠找到有效的資料源，而不浪費查找資料提供程式的時間。

>[!TIP]
>
>使用 **[Adobe受眾查找器](https://www.adobe-audience-finder.com/)** 查找可訂閱的高質量資料源。 然後，回到 [!DNL Audience Manager] 用戶介面或使用 [Audience Marketplace採購員API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) 訂閱您找到的源。

![買方市場概述](assets/buyer-marketplace-overview.png)

的 [!UICONTROL Marketplace] 清單包含您可以排序和搜索以查找適合您的資料源的資訊。 中的項 [!UICONTROL Marketplace] 採購員清單包括：

* **[!UICONTROL Search]**:按名稱或文本說明查找資料源。
* **[!UICONTROL Similar Traits]**:顯示類似項的數量 [!UICONTROL traits] 從資料饋送。 在輸入 [!UICONTROL trait] 或 [!UICONTROL segment] 在 **[!UICONTROL Similarity To]** 的子菜單。
* **[!UICONTROL Name]**:資料饋送的名稱。
* **[!UICONTROL Description]**:有關資料饋送內容的資訊。
* **[!UICONTROL Provider]**:資料提供程式的名稱。
* **[!UICONTROL Traits]**:數 [!UICONTROL traits] 的下界。
* **[!UICONTROL 30 Day Provider Unique Users]**:過去30天內看到的唯一用戶數。
* **[!UICONTROL 30 Day Overlapped Uniques]**:您帳戶中與提供商帳戶中的用戶重疊的用戶數。
* **[!UICONTROL Feed Overlap]**:以百分比顯示的30天重疊的單位值，計算如下：資料購買者30天重疊單位/資料購買者30天單位)x 100。
* **[!UICONTROL Private Feeds]**:請參閱 [專用資料源](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:您與資料提供程式之間的訂閱數。

 

要輕鬆找到滿足您需要的最佳資料源，請使用位於 [!UICONTROL Marketplace] 頁：

* **[!UICONTROL Similarity To]**:根據與A的相似性篩選資料饋送 [!UICONTROL trait] 或 [!UICONTROL segment] 你選擇的。 輸入 [!UICONTROL trait] 或要比較的段，可使用 [!UICONTROL trait] 或 [!UICONTROL segment] ID或他們各自的名字。
* **[!UICONTROL Similarity Cutoff]**:拖動滑塊以根據資料源的相似程度篩選資料源 [!UICONTROL traits] 已選定 [!UICONTROL trait] 或 [!UICONTROL segment]。 瞭解有關 [!UICONTROL trait] 相似性分數，請參閱 [特質相似性分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:根據您的訂閱狀態篩選資料源。
* **[!UICONTROL Plan Use Case]**:根據支援的使用情形篩選資料源： **[!UICONTROL Activation]**。 **[!UICONTROL Segments and Overlap]**, **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**:根據定價類型篩選資料饋送。

## 查找相似 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 給了您查找 [!UICONTROL traits] 從各種資料源中，根據它們與現有資料源的相似性 [!UICONTROL traits] 或段。 下面是如何做到的：

1. 轉到 **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用 **[!UICONTROL Similarity To]** 選擇器，以在基於的篩選之間進行選擇 [!UICONTROL trait] 或 [!UICONTROL segment]。 可以根據 [!UICONTROL trait]/[!UICONTROL segment] ID或名稱。 搜索框根據您的輸入自動顯示相關建議。
3. 確定要篩選的特性或段後，在建議清單中按一下它。
4. 要縮小結果範圍，請使用 **[!UICONTROL Similarity Cutoff]** 滑塊從不太相似的位置移動 [!UICONTROL traits]更相似。

過濾完成後，您將在結果頁中看到新列： **[!UICONTROL Similar Traits]**。 此列顯示類似的數 [!UICONTROL traits] 從每個符合篩選條件的資料饋送到您篩選的源。

要查看類似特徵的完整清單，請按一下 **[!UICONTROL Similar Traits]** 的雙曲餘切值。

>[!NOTE]
>
> Audience Marketplace顯示前500個類似項 [!UICONTROL trait] 結果。

觀看以下視頻，瞭解如何查找類似內容的全面概述 [!UICONTROL traits]。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 私人資料摘要 {#private-data-feeds}

在 [!UICONTROL Marketplace] 清單，有時提供商的名稱和 [!UICONTROL trait] 資料被標籤為私有。 這表示 [私有資料源](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私有資料饋送允許賣家限制買家訪問其資料。 當賣家提供特別優惠、折扣，或者隱私和訪問控制對他們很重要時，他們可以私下提供飼料。 作為買方，如果您想訪問私人訂閱源，則必須向賣方發送訂閱請求。 請參閱 [訂閱專用資料源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 的雙曲餘切值。

>[!MORELIKETHIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

