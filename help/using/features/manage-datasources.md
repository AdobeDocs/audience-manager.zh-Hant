---
description: 若要建立新資料來源，請至「觀眾資料>資料來源>新增」，並完成此處說明之每個章節的步驟。 建立資料來源需要管理員權限。
keywords: 資料源；管理資料源；觀眾管理資料源
seo-description: 若要建立新資料來源，請至「觀眾資料>資料來源>新增」，並完成此處說明之每個章節的步驟。 建立資料來源需要管理員權限。
seo-title: 建立資料來源
solution: Audience Manager
title: 管理資料來源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

若要建立新的資料來源，請前往並 **[!UICONTROL Audience Data > Data Sources > Add New]** 完成此處說明之每個章節的步驟。 建立資料來源需要管理員權限。

<!-- create-datasource.xml -->

>[!TIP]
>
>如需這 [些不同控制項的說明](../features/datasources-list-and-settings.md#settings-menu-options) ，請參閱資料來源設定和功能表選項。

## 資料來源詳細資料 {#details}

要完成該部 [!UICONTROL Data Source Details] 分：

1. 命名資料來源。
1. *（選擇性）* ，說明資料來源。 簡明的說明可協助您定義資料來源的角色或用途。
1. 提供整合程式碼。 一般而言，整合代碼是選用的。 當您想要：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用 [Experience Cloud ID服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)。
   * 使用描述 [檔合併規則](../features/profile-merge-rules/merge-rules-start.md)。

1. 選擇 **[!UICONTROL ID Type]**。 ID類型選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立時需要 [!UICONTROL Profile Merge Rule])。 請注意，對於某些客戶，此選項會公開 **[!UICONTROL ID Definition]** 選項。

1. Choose an **[!UICONTROL ID Definition]** option. 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 資料匯出控制 {#export-controls}

[「資料匯出控制](../features/data-export-controls.md) 」是可套用至資料來源和目的地的選用分類規則。 當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您未使用，請略過本節 [!UICONTROL Data Export Controls]。

## Data Source Settings {#settings}

這些設定會決定資料來源的識別、使用和共用方式。 您也可以啟用傳入資料檔案的錯誤報告。 要完成該部 [!UICONTROL Data Source Settings] 分：

1. 選取核 [!UICONTROL Data Source Setting] 取方塊，將選項套用至您的資料來源。
2. Click **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)


## 刪除資料來源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除您不再需要的資料來源。

>[!NOTE]
>
>請注意下列限制：
>
>* 您無法刪除作 [用中對象或資料來源同步特徵](../features/traits/client-activity-synced-audience-traits.md)。
>* 對於使用Adobe Analytics的客戶：Audience manager不允許您刪除從報表套裝自動建立的資 [!DNL Analytics] 料來源。 使用核 [心服務](https://marketing.adobe.com/resources/help/en_US/mcloud/) ，取消對應這些資料來源。


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. 選取一或多個資料來源旁的核取方塊。
如果您有 [!UICONTROL Search] 長清單，可使用方塊來尋找所需的資料來源。
1. 按一 ![](assets/icon_trash.png)下，然後確認刪除。