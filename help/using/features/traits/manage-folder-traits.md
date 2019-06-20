---
description: 建立、編輯和刪除資料夾特性。
keywords: 資料夾特徵；資料夾特性；資料夾特性；資料夾特徵
seo-description: 建立、編輯和刪除資料夾特性。
seo-title: 管理資料夾特性
solution: Audience Manager
title: 管理資料夾特性
uuid: 287ac280-bd58-4985-85bd-b6501 eb64 b7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

建立、編輯和刪除資料夾特性。

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. [!UICONTROL Trait Storage] 在視窗中，將滑鼠指標暫留在：

   * 「所有特徵」文字，以新增根層級資料夾。
   * 現有的父資料夾，可新增新的子資料夾。
   ![](assets/folder_traits_create.PNG)

1. 按一下 + 圖示可建立資料夾。請注意，您最多可以在分類法中建立 2.000 個資料夾。如需詳細資訊，請參閱[使用限制](../../features/administration/usage-limits.md)文件。
1. Name the folder and click **Save**. 例如，名為Electronics的檔案夾將擁有名為「Electronics Folder特徵」的檔案夾特徵。您可以檢視並在特徵控制面板中選取新資料夾特徵。
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. 按一下鉛筆以編輯特徵。

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]** 工作流程可讓您變更資料夾特性的資料來源。Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>您無法直接重新命名資料夾特徵。[重新命名其相關儲存資料夾](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) ，以變更資料夾特徵的名稱。

## Delete a Folder Trait {#delete-folder-trait}

刪除特徵所屬的儲存資料夾，刪除資料夾特徵。

<!-- delete-folder-trait.xml -->

1. **對象資料&gt;特徵** 以導覽 **至特徵** 控制面板。
1. [!UICONTROL Trait Storage] 在視窗中，將資料夾停留在其上並按一下X圖示以刪除資料夾。

   ![步驟結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果資料夾特徵用於區段運算式，您無法刪除該特徵。Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.