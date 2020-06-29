---
description: 建立、編輯和刪除資料夾特徵。
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: 建立、編輯和刪除資料夾特徵。
seo-title: 管理資料夾特徵
solution: Audience Manager
title: 管理資料夾特徵
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 9%

---


# 管理資料夾特徵 {#manage-folder-traits}

建立、編輯和刪除資料夾特徵。

## 建立資料夾特徵 {#create-folder-trait}

在分 [!UICONTROL folder trait] 類中建立新資料夾時，將自動建立。

<!-- create-folder-trait.xml -->

1. 前往導 **[!UICONTROL Audience Data > Traits]** 覽至「特徵」 **控制面板** 。
1. 在視窗 [!UICONTROL Trait Storage] 中，將滑鼠暫留在：

   * 「所有特徵」文字，以新增根層級資料夾。
   * 一個現有的父資料夾，用於添加新的子資料夾。
   ![](assets/folder_traits_create.PNG)

1. 按一下 + 圖示可建立資料夾。請注意，您最多可以在分類法中建立 2.000 個資料夾。如需詳細資訊，請參閱[使用限制](../../features/administration/usage-limits.md)文件。
1. 命名資料夾，然後按一下「 **儲存**」。 例如，名為Electronics的檔案夾會有名為&#39;Electronics Folder Trait&#39;的檔案夾特徵。 您可以在特徵儀表板中檢視並選取新的資料夾特徵。
1. 新資料夾特徵會自動指派給產生的 [!DNL Audience Manager] 資料來源。 具有適當[!UICONCONTROL基於角色的訪問控制([!DNL RBAC])]權限的用戶可以更改編輯資料夾特徵工作流中的資料源。 請參閱 [編輯資料夾特徵](../../features/traits/manage-folder-traits.md#edit-folder-trait)。

## 編輯資料夾特徵 {#edit-folder-trait}

說明如何編輯 [!UICONTROL folder trait]。

<!-- edit-folder-trait.xml -->

1. 在控制 [!UICONTROL Traits] 面板中，將滑鼠指標暫 **[!UICONTROL Actions]** 留在您要編輯的檔案夾特徵的欄上。
1. 按一下鉛筆以編輯特徵。

   ![](assets/folder_traits_edit_border.png)

1. 工作流 **[!UICONTROL Edit]** 程可讓您變更資料夾特徵的資料來源。 選取您想要的資料來源，然後按一下 **[!UICONTROL Save]**。 在下拉式方塊中，以數 [!DNL DPID]字方式排序資料來源。

   如果您的公司使 [!UICONTROL Role-Based Access Rights (RBAC)]用，您或您的使用者需要特 [徵資料來源的存](../../features/traits/about-folder-traits.md#role-based-access-controls) 取權。

>[!NOTE]
>
>您無法直接重新命名資料夾特徵。 [重新命名其關聯的儲存資料夾](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) ，以變更資料夾特徵的名稱。

## 刪除資料夾特徵 {#delete-folder-trait}

刪除特徵所屬的儲存資料夾，以刪除該特徵。

<!-- delete-folder-trait.xml -->

1. **讀者資料>特徵** ，以導覽至「特 **徵** 」控制面板。
1. 在視窗 [!UICONTROL Trait Storage] 中，將滑鼠指標暫留在資料夾上並按一下X圖示，以刪除資料夾。

   ![步驟結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果資料夾特徵用於區段運算式，則無法刪除該特徵。 導覽至特徵 [檢視區](../../features/traits/trait-details-page.md) ，以查看哪些區段使用資料夾特徵。 然後，按一下區段名稱以開啟區段摘 [要檢視](../../features/segments/segment-summary-view.md)，讓您從區段運算式中移除特徵。