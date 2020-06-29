---
description: 資料夾特徵可讓您自動將位於相同資料夾和所有子資料夾中的特徵匯總至可定位的區段。
keywords: segment size estimator;sse
seo-description: 資料夾特徵可讓您自動將位於相同資料夾和所有子資料夾中的特徵匯總至可定位的區段。
seo-title: 資料夾特徵關於
solution: Audience Manager
title: 資料夾特徵關於
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# 資料夾特徵：關於 {#folder-traits-about}

[!UICONTROL Folder traits] 可讓您自動將位於相同資料夾和所有子資料夾中的特徵匯總至可定位的區段。

## 使用資料夾特徵的優點 {#benefits}

A包 [!UICONTROL folder trait] 含父資料夾及其關聯子資料夾中的所有特徵。 這可讓您自動將不同資料夾層級的使用者分段並鎖定目標。 例如，假設您有如下的資料夾結構：

`*` 電子（父）

    `*` 筆記型電腦（子）

        `*` 品牌（孫子）

[!UICONTROL Folder traits] 在自動建立的檔案夾中(根據父檔案夾的名 [!DNL Electronics] 稱) [!UICONTROL Folder Trait] 限定這些檔案夾中的所有使用者。 此外，當您向下移動檔案結構時，此程式會重複執行。 在這種情況下，資料夾特徵會捕獲自動建立的筆記型電腦中「筆記型電腦」和「品牌」資料夾中的所有用戶 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 可在段表達式中選擇。 選取 [!UICONTROL folder trait] 等同於選取該資料夾及其具有群組的子資料夾中的所有 [!UICONTROL OR] 特徵。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特性實現——時近與頻率 {#folder-traits-realization}

資料夾特徵的頻率計數是資料夾及其子資料夾中特徵的實現總和。 下圖顯示Automobile資料夾中的特徵A、B和C。 請考慮每個特徵都有下列實現：

* 特徵A: 5
* 特徵B: 1
* 特徵C: 1

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
| 在資料夾之間移動特徵 | 將特徵從資料夾移至另一個資料夾，將會使該特徵與第一個資料夾特徵不符，並使其符合第二個資料夾特徵 [!UICONTROL folder trait]。 這表示如果您從資料夾刪除或移動特徵，則使用資料夾特徵做為區段運算式，將不會將特徵人口族群中的使用者與區段分割。 <br> 將Adobe Analytics區段或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀區段和特徵。 您無法從Audience Manager編輯或變更這些特徵的儲存位置。 不過，您對對應的Adobe Analytics區段或報表套裝執行的任何變更都會反映在Audience Manager中。 |
| 系統變數 | [!UICONTROL Folder traits] 無法在使用參數的事件呼叫中 `d_sid` 實現。 |
| 報表 | [!UICONTROL Folder traits] 是自動計算的特徵，不會出現在中 **[!UICONTROL Overlap Reports]**。 |