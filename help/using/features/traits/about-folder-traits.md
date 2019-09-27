---
description: 資料夾特徵可讓您自動將位於相同資料夾和所有子資料夾中的特徵匯總至可定位的區段。
keywords: segment size estimator;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Folder Traits  About
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.

## Benefits of Using Folder Traits {#benefits}

A  contains all the traits in a parent folder and its associated child folders. [!UICONTROL folder trait]This lets you automatically segment and target your users at different folder levels. For example, let's say you have a folder structure like this:

`*` 電子（父）

    筆`*` 記型電腦（子）

        品`*` 牌（孫子）

[!UICONTROL Folder traits] 在自動建立的檔案夾中(根據父檔案夾的名 [!DNL Electronics] 稱) [!UICONTROL Folder Trait] 限定這些檔案夾中的所有使用者。 此外，當您向下移動檔案結構時，此程式會重複執行。 在這種情況下，資料夾特徵會捕獲自動建立的筆記型電腦中「筆記型電腦」和「品牌」資料夾中的所有用戶 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 可在段表達式中選擇。 選取 [!UICONTROL folder trait] 等同於選取該資料夾及其具有群組的子資料夾中的所有 [!UICONTROL OR] 特徵。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特性實現——時近與頻率 {#folder-traits-realization}

資料夾特徵的頻率計數是資料夾及其子資料夾中特徵的實現總和。 下圖顯示Automobile資料夾中的特徵A、B和C。 Consider that each of the traits have the following realizations:

* 特徵A:5
* 特徵B:1
* 特徵C:1

在本例中，有 [!DNL Automobile Folder Trait] 7個實現。

![](assets/folder_traits_rollup_border.png)

## 資料夾特徵報表 {#folder-traits-reporting}

[!UICONTROL Folder traits] 從下方資料夾結構中的特徵擷取所有使用者。 如果您將特徵從資料夾移至另一個資料夾，變更會像特徵規則變更 [一樣傳播](../../reference/system-components/components-data-collection.md) ，到我們的資料收集伺服器。 下次報告執行中的報告更新會反映報告日期範圍(1、7、14、30、60、90)中的此變更。 舊報告數字不會變更。

## 基於角色的訪問控制(RBAC)權限 {#role-based-access-controls}

對於使用( [!UICONTROL Role-Based Access Controls] )[!UICONTROL RBAC]的公司，您具有適當權限的 [!UICONTROL RBAC] 使用者可以變更與關聯的資料來源 [!UICONTROL folder trait]。 用戶必須屬於具有以下任一項的組：

* `READ` 和特 `WRITE` 徵資料來源的群組權限。
* `VIEW_ALL_TRAITS` 和特 `EDIT_ALL_TRAITS` 徵資料來源的萬用字元權限。

在我們的管理檔案 [!UICONTROL RBAC] 中瞭解如何指 [派權限](../../features/administration/administration-overview.md#create-group)。

## 限制和其他考量事項 {#limits}

| 項目 | 說明 |
|---|---|
| 特徵類型 | [!UICONTROL Onboarded traits] 並 [!UICONTROL algorithmic traits] 且為頻率貢獻最多1 [!UICONTROL folder trait]個實現。 |
| Moving traits between folders | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second . [!UICONTROL folder trait]這表示如果您從資料夾刪除或移動特徵，則使用資料夾特徵做為區段運算式，將不會將特徵人口族群中的使用者與區段分割。 <br> When mapping Adobe Analytics segments or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only segments and traits. You cannot edit or change the storage location of these traits from Audience Manager. However, any change that you perform on your mapped Adobe Analytics segments or report suites reflects in Audience Manager. |
| System variables | [!UICONTROL Folder traits] cannot be realized in event calls using the  parameter.`d_sid` |
| 報告 | [!UICONTROL Folder traits] are autocalculated traits and do not appear in .**[!UICONTROL Overlap Reports]** |