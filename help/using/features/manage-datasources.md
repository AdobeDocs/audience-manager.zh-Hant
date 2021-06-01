---
description: 若要建立新資料來源，請前往「對象資料>資料來源>新增」，並完成此處所述每個區段的步驟。 建立資料源需要管理員權限。
keywords: 資料來源；管理資料來源；audience manager資料來源
seo-description: 若要建立新資料來源，請前往「對象資料>資料來源>新增」，並完成此處所述每個區段的步驟。 建立資料源需要管理員權限。
seo-title: 建立資料來源
solution: Audience Manager
title: 管理資料來源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: 資料來源
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 6%

---

# 在頻道和解決方案間一致性地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 建立 [!UICONTROL Data Source] {#create-data-source}

若要建立新的[!UICONTROL data source]，請前往&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;並完成此處所述各節的步驟。 建立[!UICONTROL data source]需要管理員權限。

<!-- create-datasource.xml -->

>[!TIP]
>
>有關這些不同控制項的說明，請參閱[資料源設定和菜單選項](../features/datasources-list-and-settings.md#settings-menu-options)。

## [!UICONTROL Data Source] 詳細資料 {#details}

要完成[!UICONTROL Data Source Details]部分：

1. 將[!UICONTROL data source]命名為。
1. *（選用）* 說明 [!UICONTROL data source]。簡潔的說明可協助您定義[!UICONTROL data source]的角色或用途。
1. 提供[!UICONTROL integration code]。 通常[!UICONTROL integration codes]為選用。 當您想：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)。
   * 使用[設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md)。

1. 選擇&#x200B;**[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (建立時需要 [!UICONTROL Profile Merge Rule])。請注意，對於某些客戶，此選項會顯示&#x200B;**[!UICONTROL ID Definition]**&#x200B;選項。

1. 選擇&#x200B;**[!UICONTROL ID Definition]**&#x200B;選項。 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[資料匯](../features/data-export-controls.md) 出控制是可套用至和的選用分 [!UICONTROL data source] 類規 [!UICONTROL destination]則。當動作違反資料隱私權或使用合約時，這會防止您將資料傳送至[!UICONTROL destination]。 如果不使用[!UICONTROL Data Export Controls]，請跳過此部分。

## [!UICONTROL Data Source] 設定 {#settings}

這些設定決定如何識別、使用和共用[!UICONTROL data source]。 您也可以啟用傳入資料檔案的錯誤報告。 要完成[!UICONTROL Data Source Settings]部分：

1. 選取[!UICONTROL Data Source Setting]核取方塊，將選項套用至您的[!UICONTROL data source]。
2. 按一下 **[!UICONTROL Save]**.

## 刪除資料源{#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除您不再需要的[!UICONTROL data source]。

>[!NOTE]
>
>請注意下列限制：
>
>* 您無法刪除[作用中對象或資料來源同步特徵](../features/traits/client-activity-synced-audience-traits.md)。
>* 使用Adobe Analytics的客戶：Audience Manager不允許您刪除從[!DNL Analytics]報表套裝自動建立的資料來源。 使用[核心服務](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html)取消映射這些資料源。


1. 按一下 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 選取一或多個資料來源旁的核取方塊。
如果您有長清單，可以使用[!UICONTROL Search]方塊來找出所需的資料來源。
1. 按一下![](assets/icon_trash.png)，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料來源設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)

