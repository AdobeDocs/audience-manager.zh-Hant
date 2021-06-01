---
description: 建立、編輯和刪除資料夾特徵。
keywords: 資料夾特徵；資料夾特徵；資料夾特徵；資料夾特徵
seo-description: 建立、編輯和刪除資料夾特徵。
seo-title: 管理資料夾特徵
solution: Audience Manager
title: 管理資料夾特徵
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: 特徵
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 9%

---

# 管理資料夾特徵 {#manage-folder-traits}

建立、編輯和刪除資料夾特徵。

## 建立資料夾特徵{#create-folder-trait}

在分類法中建立新資料夾時，會自動建立[!UICONTROL folder trait]。

<!-- create-folder-trait.xml -->

1. 前往&#x200B;**[!UICONTROL Audience Data > Traits]**&#x200B;導覽至&#x200B;**Traits**&#x200B;控制面板。
1. 在[!UICONTROL Trait Storage]視窗中，暫留在：

   * 新增根層級資料夾的「所有特徵」文字。
   * 一個現有父資料夾，用於添加新的子資料夾。

   ![](assets/folder_traits_create.PNG)

1. 按一下 + 圖示可建立資料夾。請注意，您最多可以在分類法中建立 2.000 個資料夾。如需詳細資訊，請參閱[使用限制](../../features/administration/usage-limits.md)文件。
1. 為資料夾命名，然後按一下&#x200B;**Save**。 例如，名為Electronics的資料夾將具有名為「Electronics資料夾特徵」的資料夾特徵。 您可以在特徵控制面板中檢視並選取新資料夾特徵。
1. 新資料夾特徵會自動指派給[!DNL Audience Manager]產生的資料來源。 具有適當[!UICONTROL Role-Based Access Control]([!DNL RBAC])權限的使用者可以在編輯資料夾特徵工作流程中變更資料來源。 請參閱[編輯資料夾特徵](../../features/traits/manage-folder-traits.md#edit-folder-trait)。

## 編輯資料夾特徵{#edit-folder-trait}

說明如何編輯[!UICONTROL folder trait]。

<!-- edit-folder-trait.xml -->

1. 在[!UICONTROL Traits]控制面板中，將滑鼠移至您要編輯之資料夾特徵的&#x200B;**[!UICONTROL Actions]**&#x200B;欄上。
1. 按一下鉛筆即可編輯特徵。

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]**&#x200B;工作流程可讓您變更資料夾特徵的資料來源。 選擇所需的資料源，然後按一下&#x200B;**[!UICONTROL Save]**。 在下拉式方塊中，以[!DNL DPID]依數值排序資料來源。

   如果您的公司使用[!UICONTROL Role-Based Access Rights (RBAC)]，則您或您的使用者需要特徵資料來源的[存取權限](../../features/traits/about-folder-traits.md#role-based-access-controls)。

>[!NOTE]
>
>您無法直接重新命名資料夾特徵。 [重新命名其相關](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 的儲存資料夾，以變更資料夾特徵的名稱。

## 刪除資料夾特徵{#delete-folder-trait}

刪除特徵所屬的儲存資料夾，以刪除資料夾特徵。

<!-- delete-folder-trait.xml -->

1. **對象資料>** 特徵，導覽至 **** Traitsdashboard。
1. 在[!UICONTROL Trait Storage]視窗中，將游標移至資料夾並按一下X圖示以刪除資料夾。

   ![步驟結果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果資料夾特徵用於區段運算式，則無法將其刪除。 導覽至[特徵檢視](../../features/traits/trait-details-page.md)區段，查看哪些區段使用資料夾特徵。 然後，按一下區段名稱以開啟[區段摘要檢視](../../features/segments/segment-summary-view.md)，讓您從區段運算式中移除特徵。
