---
description: 資料導出標籤與在資料源上設定的導出控制項一起使用。 「資料導出標籤」阻止您向段添加受限制的特性，並阻止將段資料發送到目標。 可以將多個導出標籤設定為新的或現有的Cookie或URL目標。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: 將資料匯出控制項新增至目的地
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 6%

---

# 將資料導出標籤添加到目標 {#add-data-export-labels}

[!DNL Data Export Labels] 與 [!DNL Export Controls] 在資料源上設定。 [!DNL Data Export Labels] 阻止您向段添加受限特徵，並阻止將段資料發送到目標。 可以將多個導出標籤設定為新的或現有的 [!DNL cookie] 或 [!DNL URL] 目標。

>[!NOTE]
>
>要添加導出標籤，需要管理員權限 *或* 足夠的權限建立或編輯目標。

<!-- t_export_labels.xml -->

要將導出標籤添加到目標：

1. 按一下 **[!UICONTROL Audience Data]**:
   * 對於新目標：按一下 **[!UICONTROL Create New Destination]**。 完成 [!UICONTROL Basic Information] 頁籤。 請參閱 [建立Cookie目標](../../features/destinations/create-cookie-destination.md) 或 [建立URL目標](../../features/destinations/create-url-destination.md) 的雙曲餘切值。
   * 對於現有目標：使用 [!DNL Search] 框中，選擇「 CSV文本」。
1. 選擇 [!DNL Data Export Label]. 如果不想設定任何導出限制，請將複選框留空。 導出標籤包括以下選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非設定 [匹配導出控制](../../features/data-export-controls.md) 資料源。
1. 按一下 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)

