---
description: 若要建立新資料來源，請前往「對象資料>資料來源>新增新功能」並完成此處所述的每個區段。需要管理員權限才能建立資料來源。
keywords: cdf；自訂資料饋送
seo-description: 若要建立新資料來源，請前往「對象資料>資料來源>新增新功能」並完成此處所述的每個區段。需要管理員權限才能建立資料來源。
seo-title: 建立資料來源
solution: Audience Manager
title: 建立資料來源
uuid: 4df65bcb-9ad9-4b72-a71 e-8918b43 d4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 需要管理員權限才能建立資料來源。

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 命名資料來源。
1. *(可選)* 說明資料來源。簡明扼要的說明可協助您定義資料來源的角色或目的。
1. 提供整合代碼。通常，整合代碼是選用的。當您想要：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. ID類型選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立a [!UICONTROL Profile Merge Rule])。Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 資料匯出控制 {#export-controls}

[「資料匯出控制」](../features/data-export-controls.md) 是可選的分類規則，您可套用至資料來源和目的地。當該動作違反資料隱私權或使用合約時，就無法將資料傳送至目的地。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

這些設定會決定如何識別、使用和共用資料來源。您也可以啓用傳入資料檔案的錯誤報告。To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Click **[!UICONTROL Save]**.

>[!MORE_贊_ this]
>
>* [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除不再需要的資料來源。

>[!NOTE]
>
>請注意下列限制：
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. 選取一或多個資料來源旁的核取方塊。
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.