---
description: 若要建立新資料來源，請前往「對象資料>資料來源>新增」 ，並完成此處所述每個區段的步驟。 需要管理員許可權才能建立資料來源。
keywords: 資料來源；管理資料來源；audience manager資料來源
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 管理資料來源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# 管理[!UICONTROL Data Sources] {#manage-data-sources}

## 建立[!UICONTROL Data Source] {#create-data-source}

若要建立新的[!UICONTROL data source]，請前往&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;並完成此處所述每個區段的步驟。 建立[!UICONTROL data source]需要系統管理員許可權。

<!-- create-datasource.xml -->

>[!TIP]
>
>如需這些不同控制項的說明，請參閱[資料Source設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)。

## [!UICONTROL Data Source]詳細資料 {#details}

若要完成[!UICONTROL Data Source Details]區段：

1. 為[!UICONTROL data source]命名。
1. *（選擇性）*&#x200B;說明[!UICONTROL data source]。 簡潔的說明可協助您定義[!UICONTROL data source]的角色或用途。
1. 提供[!UICONTROL integration code]。 一般而言，[!UICONTROL integration codes]是選用專案。 當您想要：

   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
   * 使用[設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md)。

1. 選擇&#x200B;**[!UICONTROL ID Type]**。 [!UICONTROL ID Type]選項包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** （建立[!UICONTROL Profile Merge Rule]的必要專案）。 請注意，對於某些客戶，此選項會公開&#x200B;**[!UICONTROL ID Definition]**&#x200B;選項。

   >[!NOTE]
   >
   >對於已布建以進行Audience Manager和Experience Platform的每個組織，即使您沒有在兩個應用程式之間設定區段共用，當您建立跨裝置資料來源時，會在Experience Platform中建立相對應的[身分名稱空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces)。

1. 選擇&#x200B;**[!UICONTROL ID Definition]**&#x200B;選項。 選項包括:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[資料匯出控制項](../features/data-export-controls.md)是選擇性分類規則，可套用至[!UICONTROL data source]和[!UICONTROL destination]。 當動作違反資料隱私權或使用合約時，這些動作會使您無法將資料傳送至[!UICONTROL destination]。 如果您不使用[!UICONTROL Data Export Controls]，請略過此章節。

## [!UICONTROL Data Source]設定 {#settings}

這些設定決定如何識別、使用和共用[!UICONTROL data source]。 您也可以啟用傳入資料檔案的錯誤報告。 若要完成[!UICONTROL Data Source Settings]區段：

1. 選取[!UICONTROL Data Source Setting]核取方塊以套用選項至您的[!UICONTROL data source]。
2. 按一下 **[!UICONTROL Save]**。

## 刪除資料Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

刪除您不再需要的[!UICONTROL data source]。

>[!NOTE]
>
>請注意下列限制：
>
>* 您無法刪除[作用中對象或資料Source同步特徵](../features/traits/client-activity-synced-audience-traits.md)。
>* 對於使用Adobe Analytics的客戶：Audience Manager不允許您刪除從[!DNL Analytics]報表套裝自動建立的資料來源。 使用[核心服務](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html)來取消這些資料來源的對應。

1. 按一下&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**。
1. 選取一或多個資料來源旁的核取方塊。
如果您有長清單，可以使用[!UICONTROL Search]方塊來找出所需的資料來源。
1. 按一下![](assets/icon_trash.png)，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料Source設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)
