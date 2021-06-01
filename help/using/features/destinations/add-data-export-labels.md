---
description: 資料匯出標籤可與您在資料來源上設定的匯出控制項搭配使用。 「資料匯出標籤」無法將限制特徵新增至區段，也無法將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新或現有的Cookie或URL目的地。
seo-description: 資料匯出標籤可與您在資料來源上設定的匯出控制項搭配使用。 「資料匯出標籤」無法將限制特徵新增至區段，也無法將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新或現有的Cookie或URL目的地。
seo-title: 將資料匯出控制項新增至目的地
solution: Audience Manager
title: 將資料匯出控制項新增至目的地
feature: 資料匯出控制
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---

# 將資料導出標籤添加到目標{#add-data-export-labels}

[!DNL Data Export Labels] 與您在資 [!DNL Export Controls] 料來源上設定的搭配使用。[!DNL Data Export Labels] 無法將限制特徵新增至區段，也無法將區段資料傳送至目的地。您可以將多個導出標籤設定為新的或現有的[!DNL cookie]或[!DNL URL]目標。

>[!NOTE]
>
>若要新增匯出標籤，您需要管理員權限&#x200B;*或*&#x200B;來建立或編輯目的地的足夠權限。

<!-- t_export_labels.xml -->

要將導出標籤添加到目標：

1. 按一下 **[!UICONTROL Audience Data]**:
   * 若為新目的地：按一下&#x200B;**[!UICONTROL Create New Destination]**。 先完成[!UICONTROL Basic Information]區段，再選取資料匯出標籤。 如需詳細資訊，請參閱[建立Cookie目的地](../../features/destinations/create-cookie-destination.md)或[建立URL目的地](../../features/destinations/create-url-destination.md) 。
   * 針對現有目的地：使用[!DNL Search]框查找目標或滾動清單，然後按一下目標名稱以開啟它。
1. 選擇 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊留空。 匯出標籤包含下列選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非您在資料來源上設定[符合匯出控制](../../features/data-export-controls.md)，否則匯出限制將無法運作。
1. 按一下 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)

