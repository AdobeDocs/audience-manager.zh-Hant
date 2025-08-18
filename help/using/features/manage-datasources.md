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
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
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

若要完成[!UICONTROL Data Source Details]區段，請填寫下列欄位：

1. **[!UICONTROL Name]**：提供資料來源的名稱。
1. **[!UICONTROL Description]** （選擇性）：輸入資料來源的說明，協助您定義資料來源的角色或用途。
1. **[!UICONTROL Integration Code]** （選用）：輸入整合代碼。 當您想要：
   * [建立跨裝置資料來源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)。
   * 使用[設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md)。
1. **[!UICONTROL Namespace]** （唯讀）：此欄位是唯讀的，會在您儲存資料來源時自動產生。 如果您想要將區段從Audience Manager匯出至Experience Platform，您必須在Experience Platform中建立對應的[身分名稱空間](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant#manage-namespaces)，使用自動產生的值做為Experience Platform中的名稱空間[身分符號](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces#components-of-a-namespace)。
1. **[!UICONTROL ID Type]**：選取此資料來源將包含的ID型別：
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** （建立[!UICONTROL Profile Merge Rule]的必要專案）。 請注意，對於某些客戶，此選項會公開&#x200B;**[!UICONTROL ID Definition]**&#x200B;選項。
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
>* 對於使用Adobe Analytics的客戶： Audience Manager不允許您刪除從[!DNL Analytics]報表套裝自動建立的資料來源。 使用[核心服務](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/services/customer-attributes/attributes)來取消這些資料來源的對應。

1. 按一下&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**。
1. 選取一或多個資料來源旁的核取方塊。
如果您有長清單，可以使用[!UICONTROL Search]方塊來找出所需的資料來源。
1. 按一下![](assets/icon_trash.png)，然後確認刪除。


>[!MORELIKETHIS]
>
>* [資料Source設定和功能表選項](../features/datasources-list-and-settings.md#settings-menu-options)
