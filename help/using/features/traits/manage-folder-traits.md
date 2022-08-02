---
description: 建立、編輯和刪除資料夾特徵。
keywords: 資料夾特性；資料夾特性；資料夾特性；資料夾特性
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: 管理資料夾特徵
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# 管理資料夾特徵 {#manage-folder-traits}

建立、編輯和刪除資料夾特徵。

## 建立資料夾特性 {#create-folder-trait}

A [!UICONTROL folder trait] 在分類中建立新資料夾時自動建立。

<!-- create-folder-trait.xml -->

1. 轉到 **[!UICONTROL Audience Data > Traits]** 導航至 **性狀** 控制項欄。
1. 在 [!UICONTROL Trait Storage] 窗口，懸停於：

   * 「所有Traits」文本可添加新的根級資料夾。
   * 要添加新的從屬資料夾的現有父資料夾。

   ![](assets/folder_traits_create.PNG)

1. 按一下 + 圖示可建立資料夾。請注意，在分類中最多可以建立2000個資料夾。 如需詳細資訊，請參閱[使用限制](../../features/administration/usage-limits.md)文件。
1. 命名資料夾並按一下 **保存**。 例如，名為「電子」(Electronics)的資料夾將具有名為「電子資料夾特性」的資料夾特性。 您可以在traits操控板中查看和選擇新資料夾特性。
1. 新資料夾特性將自動分配給 [!DNL Audience Manager] 生成的資料源。 您的用戶 [!UICONTROL Role-Based Access Control] ([!DNL RBAC])權限可以更改編輯資料夾特性工作流中的資料源。 請參閱 [編輯資料夾特性](../../features/traits/manage-folder-traits.md#edit-folder-trait)。

## 編輯資料夾特性 {#edit-folder-trait}

介紹如何編輯 [!UICONTROL folder trait]。

<!-- edit-folder-trait.xml -->

1. 在 [!UICONTROL Traits] 操控板，懸停在 **[!UICONTROL Actions]** 的子菜單。
1. 按一下鉛筆編輯特徵。

   ![](assets/folder_traits_edit_border.png)

1. 的 **[!UICONTROL Edit]** 工作流允許您更改資料夾特徵的資料源。 選擇所需的資料源，然後按一下 **[!UICONTROL Save]**。 資料源按數字排序 [!DNL DPID]的下界。

   如果您的公司使用 [!UICONTROL Role-Based Access Rights (RBAC)]您或您的用戶需要 [訪問權限](../../features/traits/about-folder-traits.md#role-based-access-controls) 來指定資料源。

>[!NOTE]
>
>不能直接更名資料夾特性。 [更名其關聯的儲存資料夾](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 以更改資料夾特性的名稱。

## 刪除資料夾特性 {#delete-folder-trait}

通過刪除該特性所屬的儲存資料夾來刪除資料夾特性。

<!-- delete-folder-trait.xml -->

1. **受眾資料>特徵** 導航至 **性狀** 控制項欄。
1. 在 [!UICONTROL Trait Storage] 的子菜單。

   ![步驟結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果資料夾特性用於段表達式，則不能刪除它。 導航到 [特徵觀](../../features/traits/trait-details-page.md) 查看哪些段使用資料夾特性。 然後，按一下段名稱以開啟 [段摘要視圖](../../features/segments/segment-summary-view.md)，允許您從段表達式中刪除traits。
