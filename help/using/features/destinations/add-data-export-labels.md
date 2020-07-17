---
description: 「資料匯出標籤」可與您在資料來源上設定的「匯出控制項」搭配使用。 「資料匯出標籤」可防止您新增受限制特徵至區段，以及傳送區段資料至目標。 您可以將多個匯出標籤設為新或現有的Cookie或URL目標。
seo-description: 「資料匯出標籤」可與您在資料來源上設定的「匯出控制項」搭配使用。 「資料匯出標籤」可防止您新增受限制特徵至區段，以及傳送區段資料至目標。 您可以將多個匯出標籤設為新或現有的Cookie或URL目標。
seo-title: 將資料匯出控制項新增至目的地
solution: Audience Manager
title: 將資料匯出控制項新增至目的地
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] 與您在資 [!DNL Export Controls] 料來源上設定的搭配使用。 [!DNL Data Export Labels] 防止您新增受限制特徵至區段，以及傳送區段資料至目標。 您可以將多個匯出標籤設為新的或現有的 [!DNL cookie] 或目 [!DNL URL] 標。

>[!NOTE]
>
>若要新增匯出標籤，您需要管理員權 *限* ，或具備足夠的權限才能建立或編輯目標。

<!-- t_export_labels.xml -->

要將導出標籤添加到目標：

1. 按一下 **[!UICONTROL Audience Data]**:
   * 對於新目標： 按一 **[!UICONTROL Create New Destination]**&#x200B;下。 在選擇 [!UICONTROL Basic Information] 資料匯出標籤之前，請完成章節。 如需 [詳細資訊，請參閱](../../features/destinations/create-cookie-destination.md)[建立Cookie目標或建立URL目標](../../features/destinations/create-url-destination.md) 。
   * 對於現有目標： 使用方 [!DNL Search] 塊尋找您的目標，或捲動清單，然後按一下目標名稱以開啟它。
1. 選擇 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊留空。 匯出標籤包含下列選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非您對資料來源設定相符的 [匯出控制](../../features/data-export-controls.md) ，否則匯出限制無法運作。
1. 按一下 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)