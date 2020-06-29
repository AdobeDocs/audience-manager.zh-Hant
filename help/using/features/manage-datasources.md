---
description: 若要建立新資料來源，請至「觀眾資料>資料來源>新增」，並完成此處說明之每個章節的步驟。 建立資料來源需要管理員權限。
keywords: data sources;manage data source;audience manager data source
seo-description: 若要建立新資料來源，請至「觀眾資料>資料來源>新增」，並完成此處說明之每個章節的步驟。 建立資料來源需要管理員權限。
seo-title: 建立資料來源
solution: Audience Manager
title: 管理資料來源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# 在頻道和解決方案間一致性地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 建立 [!UICONTROL Data Source] {#create-data-source}

若要建立新 [!UICONTROL data source]的區段，請 **[!UICONTROL Audience Data > Data Sources > Add New]** 前往並完成此處說明的每個區段步驟。 需要有管理員權限才能建立 [!UICONTROL data source]。

<!-- create-datasource.xml -->

>[!TIP]
>
>如需這 [些不同控制項的說明](../features/datasources-list-and-settings.md#settings-menu-options) ，請參閱資料來源設定和功能表選項。

## [!UICONTROL Data Source] 詳細資料 {#details}

要完成該部 [!UICONTROL Data Source Details] 分：

1. 命名 [!UICONTROL data source]。
1. *（可選）* ，請說明 [!UICONTROL data source]。 簡明的說明可協助您定義角色或目的 [!UICONTROL data source]。
1. 提供 [!UICONTROL integration code]。 通常為 [!UICONTROL integration codes] 可選。 當您想要：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * Use the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html).
   * 使用描述 [檔合併規則](../features/profile-merge-rules/merge-rules-start.md)。

1. 選擇 **[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立時需要 [!UICONTROL Profile Merge Rule])。 請注意，對於某些客戶，此選項會公開 **[!UICONTROL ID Definition]** 選項。

1. Choose an **[!UICONTROL ID Definition]** option. 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[「資料匯出控制](../features/data-export-controls.md) 」是可套用至和的選用分類 [!UICONTROL data source] 規則 [!UICONTROL destination]。 當該動作違反資料隱私或使 [!UICONTROL destination] 用合約時，您無法傳送資料至。 如果您未使用，請略過本節 [!UICONTROL Data Export Controls]。

## [!UICONTROL Data Source] 設定 {#settings}

這些設定會決定 [!UICONTROL data source] 如何識別、使用和共用。 您也可以啟用傳入資料檔案的錯誤報告。 要完成該部 [!UICONTROL Data Source Settings] 分：

1. 選取核 [!UICONTROL Data Source Setting] 取方塊，將選項套用至您的 [!UICONTROL data source]。
2. 按一下 **[!UICONTROL Save]**.

## 刪除資料來源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除 [!UICONTROL data source] 您不再需要的項目。

>[!NOTE]
>
>請注意下列限制：
>
>* 您無法刪除作 [用中對象或資料來源同步特徵](../features/traits/client-activity-synced-audience-traits.md)。
>* 對於使用Adobe Analytics的客戶： Audience Manager不允許您刪除從報表套裝自動建立的資 [!DNL Analytics] 料來源。 使用核 [心服務](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) ，取消對應這些資料來源。


1. 按一下 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 選取一或多個資料來源旁的核取方塊。
如果您有 [!UICONTROL Search] 長清單，可使用方塊來尋找所需的資料來源。
1. 按一 ![](assets/icon_trash.png)下，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)