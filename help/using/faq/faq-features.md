---
description: 常見產品與功能相關問題與問題。
keywords: audience manager cookies
seo-description: 常見產品與功能相關問題與問題。
seo-title: 產品功能與功能常見問答集
solution: Audience Manager
title: 產品功能與功能常見問答集
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 2b70b651a626c2b5667edb58c8c6068152a9d770
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 1%

---


# 產品功能與功能常見問答集{#product-features-and-functions-faq}

常見產品與功能相關問題與問題。

 

<!-- 

faq_features_functions.xml

 -->

**什麼是組織ID，我要如何找到它？**

此 *`Organization ID`* 為唯一ID，可識別您的組織 [!DNL Audience Manager] 與 [!DNL Adobe Experience Cloud]。 它包含區分大小寫的24個字元英數字串，後面接著 [!UICONTROL @AdobeOrg]。

例如， *`Organization ID`* 如下所示： `1FD6776A524453CC0A490D44@AdobeOrg`.

Audience Manager *`Organization ID`* 的 [DIL](../dil/dil-overview.md) API、 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)，以及其他解決方案都使 [!DNL Experience Cloud] 用。 具有管理員權限的使用者可以 *`Organization ID`* 在上找到 [!DNL Adobe Admin Console]。 請參閱「管 [理——使用者管理」常見問答](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)。

 

**我可以大量建立特徵或目標嗎？**

是。請參 [閱大量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支 *援工具* 。 [!DNL Audience Manager]為了方便和禮節而提供。 若是大量變更，建議您改 [用Audience Manager API](../api/api.md) 。

 

**當執行大量ID匯出至目標時，會遺失部分客戶ID。 Why does that happen?**

當裝置ID([AAM UUID](../reference/ids-in-aam.md))連結至多個CRM ID([DPUUID](../reference/ids-in-aam.md))時，只會匯出最新的對應。 這就是為什麼您可能會看到匯出的裝置ID數量低於預期。

 

**可[!DNL Audience Manager]以減少對協力廠商標籤或像素的需求，並改善頁面載入時間嗎？**

如果 [!DNL Audience Manager] 已與您的協力廠商資料合作夥伴整合，您可以使用伺服器對伺服器ID呼叫來取代其像素和標籤 [!DNL Audience Manager]。 在這種情況下， [!DNL Audience Manager] 當我們第一次看到使用者時，會觸發單一ID呼叫，並將該資訊與您的第三方合作夥伴同步。 如此，您就不需要從每個頁面呼叫多個像素。 減少像素呼叫可改善頁面載入時間。

 

**我已訂閱資料饋送。 資料儲存在哪裡？**

您的資料饋送和饋送中包含的所有特徵會顯示為子檔案夾和特徵 [!DNL Audience Manager]。 前往並展 **[!UICONTROL Audience Data > Traits]** 開資料夾以檢 [!UICONTROL 3rd-Party Data] 視您的特徵，或使用此資料建立區段和模型。

 

**什麼是[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager使 [!UICONTROL Tag Insertion Manager] 用(TIM)來建立和管理 [!UICONTROL data collection code (DIL)]。 This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**演算法模型與特徵建議之間有何差異？ 我何時應使用每個？**

**演算法模型**

演算法模型不僅會找出最具影響力的特徵，還會根據這些特徵對使用者進行評分，並為每位使用者指派個別的分數。 然後您建立演算法特徵，以鎖定您的使用者。 在「特徵產生器」中，您可以透過精確和觸及控制項，指定哪些使用者擁有您要定位的具影響力特徵。

演算法模型可讓您選擇不同精確度等級的使用者，並在Audience Lab中測試哪一組使用者轉換效果較佳。 請參閱Audience Lab中比較模 [型的詳細使用案例](../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在演算模型中，模型每8天執行一次，並重新整理符合演算法特徵的使用者。

**特徵建議**

「特徵建議」是取得與您在區段中使用之特徵類似之其他特徵見解的快速方式。

您應在下列情況下使用特徵建議：

* 在建立細分時，您需要快速洞察；
* 您使用區段做為簡短的促銷活動，或想要快速抑制轉換的觀眾；
* 您正嘗試將觸及面最大化。

 

**Adobe Analytics和Audience Manager區段之間有何差異？**

是的，請閱讀 [Analytics和Audience Manager中的瞭解區段](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) ，以深入瞭解差異。
