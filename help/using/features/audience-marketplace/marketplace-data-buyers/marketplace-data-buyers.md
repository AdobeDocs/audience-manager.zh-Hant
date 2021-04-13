---
description: 想要從Audience Manager內購買第三方資料的資料購買者的概述和工作流程
seo-description: 想要從Audience Manager內購買第三方資料的資料購買者的概述和工作流程
seo-title: 適用於資料購買者的 Audience Marketplace
solution: Audience Manager
title: 適用於資料購買者的 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: 訪客交易市場
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] 適用於資料購買者  {#audience-marketplace-for-data-buyers}

想要從[!DNL Audience Manager]內購買第三方資料的資料購買者的概述和工作流程。

>[!NOTE]
>[基於角色的權限](../../../reporting/reports-dashboard.md)控制對[!UICONTROL Audience Marketplace]功能的訪問。
>
>* 管理員可以建立資料饋送、管理訂閱者，以及訂閱資料饋送。
>* 使用者只能搜尋和檢視動態消息。


## [!UICONTROL Marketplace]:關於{#about-marketplace}

[!UICONTROL Marketplace]是[!DNL Audience Manager]功能，適用於列出您可訂閱之資料饋送的資料購買者。 它列出固定速率、[!DNL CPM]和私人資料饋送。 這些饋送是由使用[!DNL Audience Manager]來銷售資料的第三方廠商提供。

在[!UICONTROL Marketplace]中，報告工具可讓您追蹤動態消息的使用情況，以及[!UICONTROL traits]與已訂閱資料動態消息中的重疊。 最後，使用[!UICONTROL Audience Marketplace]時，[!DNL Adobe]會處理髮票和費用付款（雖然您訂閱[!DNL CPM]摘要時必須自行報告使用情況）。 這些功能可讓您找到有效的資料來源，而不浪費時間尋找資料供應商。

>[!TIP]
>
>使用&#x200B;**[AdobeAudience Finder](https://www.adobe-audience-finder.com/)**&#x200B;尋找可訂閱的高品質資料饋送。 然後，返回[!DNL Audience Manager]使用者介面，或使用[Audience Marketplace購買者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)訂閱您找到的動態消息。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace]清單包含您可排序和搜尋的資訊，以尋找適合您的資料饋送。 [!UICONTROL Marketplace]採購員清單中的項目包括：

* **[!UICONTROL Search]**:依名稱或文字說明尋找資料饋送。
* **[!UICONTROL Similar Traits]**:顯示資料饋送中 [!UICONTROL traits] 的類似數目。在&#x200B;**[!UICONTROL Similarity To]**&#x200B;區段中輸入[!UICONTROL trait]或[!UICONTROL segment]以篩選依據後，會顯示此欄。
* **[!UICONTROL Name]**:資料饋送的名稱。
* **[!UICONTROL Description]**:資料饋送內容的相關資訊。
* **[!UICONTROL Provider]**:資料提供者的名稱。
* **[!UICONTROL Traits]**:資料饋送 [!UICONTROL traits] 中的數目。
* **[!UICONTROL 30 Day Provider Unique Users]**:過去30天內檢視的獨特使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]**:您帳戶中與提供者帳戶中的使用者重疊的使用者人數。
* **[!UICONTROL Feed Overlap]**:30天重疊的獨特值（以百分比顯示），計算為：資料購買者30天重疊獨特客戶／資料購買者30天獨特客戶)x 100。
* **[!UICONTROL Private Feeds]**:請參 [閱私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:您與資料提供者的訂閱數。

 

若要輕鬆找到符合您需求的最佳資料饋送，請使用[!UICONTROL Marketplace]頁面左側的下列篩選條件：

* **[!UICONTROL Similarity To]**:根據資料饋送的相似性來篩選 [!UICONTROL trait] 資 [!UICONTROL segment] 料饋送。在輸入[!UICONTROL trait]或區段以進行比較時，您可以使用[!UICONTROL trait]或[!UICONTROL segment] ID，或其各自的名稱。
* **[!UICONTROL Similarity Cutoff]**:拖曳滑桿以根據資料饋送與您選取或的 [!UICONTROL traits] 相似程度來篩選 [!UICONTROL trait] 資料 [!UICONTROL segment]。若要進一步瞭解[!UICONTROL trait]相似性分數，請參閱[特徵相似性分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:根據您的訂閱狀態篩選資料饋送。
* **[!UICONTROL Plan Use Case]**:根據支援的使用案例篩選資料饋送： **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**:根據資料饋送的定價類型篩選資料饋送。

## 查找類似[!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 提供您從各種資料 [!UICONTROL traits] 饋送中尋找的選項，根據資料饋送與現有或區 [!UICONTROL traits] 段的相似性。以下是如何做到的：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用&#x200B;**[!UICONTROL Similarity To]**&#x200B;選擇器，在基於[!UICONTROL trait]或[!UICONTROL segment]的篩選中進行選擇。 您可以根據[!UICONTROL trait]/[!UICONTROL segment] ID或名稱進行篩選。 搜尋方塊會根據您的輸入自動顯示相關建議。
3. 在您識別要篩選依據的特徵或區段後，在建議清單中按一下它。
4. 若要縮小結果範圍，請使用&#x200B;**[!UICONTROL Similarity Cutoff]**&#x200B;滑桿，從較不相似的[!UICONTROL traits]移至較相似的。

篩選完成後，您會在結果頁面中看到新欄：**[!UICONTROL Similar Traits]**。 此欄顯示符合篩選條件之每個資料饋送中與您篩選依據的[!UICONTROL traits]類似數目。

若要查看類似特徵的完整清單，請按一下&#x200B;**[!UICONTROL Similar Traits]**&#x200B;列中的數字。

>[!NOTE]
>
> Audience Marketplace會顯示資料饋送的前500個類似[!UICONTROL trait]結果。

觀看以下影片，以取得如何尋找類似[!UICONTROL traits]的完整概觀。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 私人資料摘要 {#private-data-feeds}

在[!UICONTROL Marketplace]清單中，有時提供方的名稱和[!UICONTROL trait]資料會標籤為專用。 這表示[私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人資料饋送可讓賣家限制買家存取其資料。 當賣家提供特殊優惠、折扣或隱私權和存取控制對他們很重要時，就可以私下提供餵送。 身為買家，如果您想要存取私人動態消息，您必須傳送訂閱要求給賣方。 如需詳細資訊，請參閱[訂閱私人資料饋送](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

>[!MORELIKETHIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

