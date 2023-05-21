---
description: 資料夾特徵允許您自動將駐留在同一資料夾和所有子資料夾中的特徵聚合到目標段中。
keywords: 段大小估計器；sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: 資料夾特徵關於
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# 資料夾特徵：關於 {#folder-traits-about}

[!UICONTROL Folder traits] 允許您自動將駐留在同一資料夾和所有子資料夾中的特徵聚合到目標段中。

## 使用資料夾特徵的好處 {#benefits}

A [!UICONTROL folder trait] 包含父資料夾及其關聯子資料夾中的所有特徵。 這樣，您就可以在不同資料夾級別自動劃分和定位用戶。 例如，假設您有這樣的資料夾結構：

`*` 電子（父）

    `*` 筆記型電腦（子）

        `*` 品牌（孫子）

[!UICONTROL Folder traits] 在自動建立的 [!DNL Electronics] [!UICONTROL Folder Trait] （基於父資料夾的名稱）。 而且，當您向下移動檔案結構時，此過程會重複。 在這種情況下，資料夾特徵將捕獲自動建立的筆記型電腦中「筆記型電腦和品牌」資料夾中的所有用戶 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 可在段表達式中選擇。 選擇 [!UICONTROL folder trait] 等效於選擇該資料夾及其子資料夾中的所有特徵 [!UICONTROL OR] 分組。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特徵實現 — 頻率和頻率 {#folder-traits-realization}

資料夾特徵的頻率計數是資料夾及其子資料夾中特徵的實現的總和。 下圖顯示了Automabile資料夾中的traits A、B和C。 請考慮每個特徵都具有以下實現：

* 特徵A:5
* 特徵B:1
* 特徵C:1

在這個例子中， [!DNL Automobile Folder Trait] 有7個實現。

![](assets/folder_traits_rollup_border.png)

## 資料夾特性報告 {#folder-traits-reporting}

[!UICONTROL Folder traits] 從下面資料夾結構中的traits捕獲所有用戶。 如果將特徵從資料夾移動到另一個資料夾，則更改會傳播到我們的 [資料收集伺服器](../../reference/system-components/components-data-collection.md) 就像性質規則改變一樣。 下次報告運行中的報告更新以反映報告日期範圍(1、7、14、30、60、90)內的這一變化。 以前天數的舊報告編號不會更改。

## 基於角色的訪問控制(RBAC)權限 {#role-based-access-controls}

對於使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])，您的用戶 [!UICONTROL RBAC] 權限可以更改與 [!UICONTROL folder trait]。 用戶必須屬於具有以下任一項的組：

* `READ` 和 `WRITE` 對特徵資料源的組權限。
* `VIEW_ALL_TRAITS` 和 `EDIT_ALL_TRAITS` 特徵資料源的通配符權限。

瞭解如何分配 [!UICONTROL RBAC] 權限 [管理文檔](../../features/administration/administration-overview.md#create-group)。

## 限制和其他注意事項 {#limits}

| 項目 | 說明 |
|---|---|
| 特徵類型 | [!UICONTROL Onboarded traits] 和 [!UICONTROL algorithmic traits] 最多為實現 [!UICONTROL folder trait]頻率。 |
| 在資料夾之間移動特徵 | 將一個特徵從資料夾移到另一個特徵將使該特徵從第一個資料夾特徵中消失，並將其限定為第二個 [!UICONTROL folder trait]。 這意味著，如果從資料夾中刪除或移動特徵，則特徵群體中的用戶將使用資料夾特徵作為段表達式從段中取消分段。 <br> 將Adobe Analytics段或報表套件映射到您的Experience Cloud組織時，Audience Manager會自動建立新的、相應的只讀段和特徵。 不能編輯或更改這些特徵的儲存位置(從Audience Manager)。 但是，您對映射的Adobe Analytics段或報表套件執行的任何更改都反映在Audience Manager中。 |
| 系統變數 | [!UICONTROL Folder traits] 在使用 `d_sid` 的下界。 |
| 報表 | [!UICONTROL Folder traits] 是自動計算的特徵，且不顯示在 **[!UICONTROL Overlap Reports]**。 |
