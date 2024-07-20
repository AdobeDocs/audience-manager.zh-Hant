---
description: 想要從Audience Manager內購買第三方資料的資料購買者總覽和工作流程
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: 適用於資料購買者的Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 1%

---

# 資料購買者適用的[!UICONTROL Audience Marketplace] {#audience-marketplace-for-data-buyers}

想要從[!DNL Audience Manager]內購買第三方資料的資料購買者之概觀和工作流程。

>[!NOTE]
>[角色型許可權](../../../reporting/reports-dashboard.md)控制對[!UICONTROL Audience Marketplace]功能的存取。
>
>* 管理員可以建立資料摘要、管理訂閱者，以及訂閱資料摘要。
>* 使用者只能搜尋和檢視摘要。

## [!UICONTROL Marketplace]：關於 {#about-marketplace}

[!UICONTROL Marketplace]是[!DNL Audience Manager]功能，適用於列出您可訂閱之資料摘要的資料購買者。 它列出統一費率、[!DNL CPM]和私人資料摘要。 這些摘要是由使用[!DNL Audience Manager]銷售資料的協力廠商所提供。

在[!UICONTROL Marketplace]中，報告工具可讓您追蹤摘要使用情形，以及[!UICONTROL traits]和已訂閱資料摘要中的專案之間的重疊。 最後，透過[!UICONTROL Audience Marketplace]，[!DNL Adobe]會處理發票和費用付款（不過您在訂閱[!DNL CPM]摘要時，必須自行報告使用狀況）。 這些功能可讓您找到有效的資料來源，而不會浪費時間尋找資料提供者。

>[!TIP]
>
>使用&#x200B;**[AdobeAudience Finder](https://www.adobe-audience-finder.com/)**&#x200B;尋找您可以訂閱的高品質資料摘要。 接著，返回[!DNL Audience Manager]使用者介面或使用[Audience Marketplace購買者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)來訂閱您找到的摘要。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace]清單包含您可以排序和搜尋的資訊，以尋找適合您的資料摘要。 [!UICONTROL Marketplace]購買者清單中的專案包括：

* **[!UICONTROL Search]**：依名稱或文字說明尋找資料摘要。
* **[!UICONTROL Similar Traits]**：顯示資料摘要中類似[!UICONTROL traits]的數字。 當您在&#x200B;**[!UICONTROL Similarity To]**&#x200B;區段中輸入[!UICONTROL trait]或[!UICONTROL segment]以篩選依據後，此欄會顯示出來。
* **[!UICONTROL Name]**：資料摘要的名稱。
* **[!UICONTROL Description]**：資料摘要內容的相關資訊。
* **[!UICONTROL Provider]**：資料提供者的名稱。
* **[!UICONTROL Traits]**：資料摘要中的[!UICONTROL traits]數目。
* **[!UICONTROL 30 Day Provider Unique Users]**：過去30天內檢視的不重複使用者數目。
* **[!UICONTROL 30 Day Overlapped Uniques]**：您的帳戶中與提供者帳戶中的使用者重疊的使用者數目。
* **[!UICONTROL Feed Overlap]**： 30天重疊不重複值，以百分比顯示，計算為：資料購買者30天重疊不重複/資料購買者30天不重複) x 100。
* **[!UICONTROL Private Feeds]**：請參閱[私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**：您與資料提供者之間的訂閱數目。

 

若要輕鬆尋找符合您需求的最佳資料摘要，請使用[!UICONTROL Marketplace]頁面左側的下列篩選器：

* **[!UICONTROL Similarity To]**：根據資料摘要與您所選[!UICONTROL trait]或[!UICONTROL segment]的相似性來篩選資料摘要。 輸入[!UICONTROL trait]或區段進行比較時，您可以使用[!UICONTROL trait]或[!UICONTROL segment] ID，或它們的個別名稱。
* **[!UICONTROL Similarity Cutoff]**：拖曳滑桿以根據資料摘要的[!UICONTROL traits]與您選取的[!UICONTROL trait]或[!UICONTROL segment]的相似性來篩選資料摘要。 若要深入瞭解[!UICONTROL trait]相似度分數，請參閱[特徵相似度分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**：根據您的訂閱狀態篩選資料摘要。
* **[!UICONTROL Plan Use Case]**：根據資料摘要的支援使用案例來篩選資料摘要： **[!UICONTROL Activation]**、**[!UICONTROL Segments and Overlap]**&#x200B;和&#x200B;**[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**：根據資料摘要的定價型別篩選資料摘要。

## 正在尋找類似的[!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace]可讓您選擇根據與您現有[!UICONTROL traits]或區段的相似度，從各種資料摘要中尋找[!UICONTROL traits]。 以下是其操作方式：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用&#x200B;**[!UICONTROL Similarity To]**&#x200B;選擇器來根據[!UICONTROL trait]或[!UICONTROL segment]選擇篩選。 您可以根據[!UICONTROL trait]/[!UICONTROL segment] ID或名稱進行篩選。 搜尋方塊會根據您的輸入自動顯示相關建議。
3. 一旦識別出您要篩選的特徵或區段，請在建議清單中按一下該特徵或區段。
4. 若要縮小結果範圍，請使用&#x200B;**[!UICONTROL Similarity Cutoff]**&#x200B;滑桿從較不相似的[!UICONTROL traits]移至較相似的。

篩選完成後，您會在結果頁面中看到新欄： **[!UICONTROL Similar Traits]**。 此欄顯示符合篩選條件的每個資料摘要中，與篩選依據的類似[!UICONTROL traits]數目。

若要檢視類似特徵的完整清單，請按一下&#x200B;**[!UICONTROL Similar Traits]**&#x200B;欄中的數字。

>[!NOTE]
>
> Audience Marketplace會顯示來自所有資料摘要的前500個類似[!UICONTROL trait]個結果。

觀看以下影片，瞭解如何尋找類似[!UICONTROL traits]的完整概觀。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 私人資料摘要 {#private-data-feeds}

在[!UICONTROL Marketplace]清單中，有時提供者的名稱和[!UICONTROL trait]資料會標示為私人。 這表示[私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人資料摘要可讓賣家限制買家存取其資料。 當賣家提供特別優惠、折扣，或當隱私權和存取控制對他們來說很重要時，就可以將摘要設為私人。 如果您想要存取私人摘要，身為購買者，您必須傳送訂閱要求給賣家。 如需詳細資訊，請參閱[訂閱私人資料摘要](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

>[!MORELIKETHIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* 資料購買者[折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
