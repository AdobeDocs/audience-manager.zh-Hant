---
description: 「資料匯出標籤」可與您在資料來源上設定的「匯出控制項」搭配使用。 資料匯出標籤可防止您將受限制的特徵新增至區段，也防止您將區段資料傳送至目的地。 您可以將多個匯出標籤設定到新的或現有的Cookie或URL目的地。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: 將資料匯出控制項新增至目的地
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# 將資料匯出標籤新增至目的地 {#add-data-export-labels}

[!DNL Data Export Labels]使用您在資料來源上設定的[!DNL Export Controls]。 [!DNL Data Export Labels]可防止您將受限制的特徵新增至區段，也防止您將區段資料傳送至目的地。 您可以將多個匯出標籤設定到新的或現有的[!DNL cookie]或[!DNL URL]目的地。

>[!NOTE]
>
>若要新增匯出標籤，您必須擁有系統管理員許可權&#x200B;*或*&#x200B;足夠的許可權，才能建立或編輯目的地。

<!-- t_export_labels.xml -->

若要將匯出標籤新增至目的地：

1. 按一下&#x200B;**[!UICONTROL Audience Data]**：

   * 針對新目的地：按一下&#x200B;**[!UICONTROL Create New Destination]**。 在您選取資料匯出標籤之前，請先完成[!UICONTROL Basic Information]區段。 如需詳細資訊，請參閱[建立Cookie目的地](../../features/destinations/create-cookie-destination.md)或[建立URL目的地](../../features/destinations/create-url-destination.md)。
   * 針對現有目的地：使用[!DNL Search]方塊來尋找您的目的地，或捲動清單並按一下目的地名稱以開啟該清單。

1. 選取[!DNL Data Export Label]。 如果您不想設定任何匯出限制，請將核取方塊保留空白。 匯出標籤包含以下選項：

   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非您在資料來源上設定符合匯出控制項[的](../../features/data-export-controls.md)，否則匯出限制將無法運作。

1. 按一下 **[!UICONTROL Save]**。

>[!MORELIKETHIS]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)
