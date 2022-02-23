---
description: 要建立新資料源，請轉至「受眾資料」>「資料源」>「添加新」，並完成此處介紹的每個部分的步驟。 建立資料源需要管理員權限。
keywords: 資料源；管理資料源；audience manager資料源
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 管理資料源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 2%

---

# 在頻道和解決方案間一致性地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 建立 [!UICONTROL Data Source] {#create-data-source}

建立新 [!UICONTROL data source]，轉到 **[!UICONTROL Audience Data > Data Sources > Add New]** 並完成此處介紹的每個部分的步驟。 建立 [!UICONTROL data source]。

<!-- create-datasource.xml -->

>[!TIP]
>
>請參閱 [資料源設定和菜單選項](../features/datasources-list-and-settings.md#settings-menu-options) 中。

## [!UICONTROL Data Source] 詳細資料 {#details}

完成 [!UICONTROL Data Source Details] 部分：

1. 命名 [!UICONTROL data source]。
1. *（可選）* 描述 [!UICONTROL data source]。 簡明的說明可幫助您定義 [!UICONTROL data source]。
1. 提供 [!UICONTROL integration code]。 通常， [!UICONTROL integration codes] 為可選項。 當您希望：

   * [建立跨設備資料源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
   * 使用 [配置檔案合併規則](../features/profile-merge-rules/merge-rules-start.md)。

1. 選擇 **[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立 [!UICONTROL Profile Merge Rule])。 請注意，對於某些客戶，此選擇將公開 **[!UICONTROL ID Definition]** 頁籤

1. 選擇 **[!UICONTROL ID Definition]** 的雙曲餘切值。 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[資料導出控制項](../features/data-export-controls.md) 是可應用於的可選分類規則 [!UICONTROL data source] 和 [!UICONTROL destination]。 它們阻止您向 [!UICONTROL destination] 當該操作違反資料隱私或使用協定時。 如果您不使用 [!UICONTROL Data Export Controls]。

## [!UICONTROL Data Source] 設定 {#settings}

這些設定確定 [!UICONTROL data source] 標識、使用和共用。 您還可以為入站資料檔案啟用錯誤報告。 完成 [!UICONTROL Data Source Settings] 部分：

1. 選擇 [!UICONTROL Data Source Setting] 選項 [!UICONTROL data source]。
2. 按一下 **[!UICONTROL Save]**.

## 刪除資料源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除 [!UICONTROL data source] 你不再需要的。

>[!NOTE]
>
>請注意以下限制：
>
>* 無法刪除 [活動受眾或資料源同步特性](../features/traits/client-activity-synced-audience-traits.md)。
>* 對於使用Adobe Analytics的客戶：Audience Manager不允許您刪除自動從 [!DNL Analytics] 報告套件。 使用 [核心服務](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) 取消映射這些資料源。


1. 按一下 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 選中一個或多個資料源旁邊的複選框。
您可以使用 [!UICONTROL Search] 框，以查找所需的資料源。
1. 按一下  ![](assets/icon_trash.png)，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料源設定和菜單選項](../features/datasources-list-and-settings.md#settings-menu-options)

