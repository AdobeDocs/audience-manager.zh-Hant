---
description: 資料匯出標籤可與您在資料來源上設定的「匯出控制」搭配運作。「資料匯出標籤」可防止您將受限制的特性新增至區段，以及將區段資料傳送至目的地。您可以將多個匯出標籤設定為新的或現有的Cookie或URL目的地。
seo-description: 資料匯出標籤可與您在資料來源上設定的「匯出控制」搭配運作。「資料匯出標籤」可防止您將受限制的特性新增至區段，以及將區段資料傳送至目的地。您可以將多個匯出標籤設定為新的或現有的Cookie或URL目的地。
seo-title: 將資料匯出控制新增至目的地
solution: Audience Manager
title: 將資料匯出控制新增至目的地
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---



# 將資料匯出標籤新增至目的地 {#add-data-export-labels}

[!DNL Data Export Labels] 與 [!DNL Export Controls] 您在資料來源上設定的作業相同。[!DNL Data Export Labels] 防止您將受限制的特性新增至區段，以及將區段資料傳送至目的地。您可以將多個匯出標籤設定為新或現有 [!DNL cookie][!DNL URL] 或目的地。

>[!NOTE]
>
>若要新增匯出標籤，您需要管理員權限 *或* 足夠權限來建立或編輯目的地。

<!-- t_export_labels.xml -->

若要將匯出標籤新增至目的地：

1. Click **[!UICONTROL Audience Data]**:
   * 對於新目的地：按一 **[!UICONTROL Create New Destination]**&#x200B;下。請先完成 [!UICONTROL Basic Information] 區段，然後再選擇資料匯出標籤。如需詳細資訊，請參閱 [建立Cookie目的地](../../features/destinations/manage-destinations.md#create-cookie-destination) 或 [建立URL目的地](../../features/destinations/manage-destinations.md#configure-url-destination) 。
   * 對於現有目的地：使用 [!DNL Search] 方塊尋找目的地或捲動清單，然後按一下目的地名稱以開啓它。
1. 選擇 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊保留空白。匯出標籤包含下列選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >除非您對資料來源設定 [相符的匯出控制](../../features/data-export-controls.md) ，否則匯出限制將無法運作。
1. Click **[!UICONTROL Save]**.

>[!MORE_贊_ this]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)