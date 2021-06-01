---
description: 資料夾特徵可讓您自動將位於相同資料夾中的特徵和所有子資料夾匯總至可定位的區段。
keywords: 區段大小估算程式；sse
seo-description: 資料夾特徵可讓您自動將位於相同資料夾中的特徵和所有子資料夾匯總至可定位的區段。
seo-title: 資料夾特徵關於
solution: Audience Manager
title: 資料夾特徵關於
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: 特徵
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# 資料夾特徵：關於 {#folder-traits-about}

[!UICONTROL Folder traits] 可讓您自動將位於相同資料夾和所有子資料夾中的特徵匯總至可定位的區段。

## 使用資料夾特徵的優點 {#benefits}

[!UICONTROL folder trait]包含父資料夾及其關聯子資料夾中的所有特徵。 這可讓您自動劃分不同資料夾層級的使用者，並鎖定其為目標。 例如，假設您有如下的資料夾結構：

`*` 電子產品（父項）

    `*`筆記型電腦（子）

        `*`品牌（孫子）

[!UICONTROL Folder traits] 在自動建立的(根據父資料夾的名 [!DNL Electronics] [!UICONTROL Folder Trait] 稱)中限定這些資料夾中的所有用戶。而且，當您向下移動檔案結構時，此過程會重複。 在這種情況下，資料夾特徵將捕獲自動建立的筆記型電腦[!UICONTROL Folder Trait]中的筆記型電腦和品牌資料夾中的所有用戶。

[!UICONTROL Folder traits] 可在區段運算式中選取。選擇[!UICONTROL folder trait]等同於選擇該資料夾及其具有[!UICONTROL OR]分組的子資料夾中的所有特徵。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特徵實現 — 造訪間隔和頻率{#folder-traits-realization}

資料夾特徵的頻率計數是其資料夾中特徵及其子資料夾中實現的總數。 下圖顯示特徵A、B和C，這些特徵會顯示在Automil資料夾中。 請考慮每個特徵都有下列實現：

* 特徵A:5
* 特徵B:3
* 特徵C:3

在此案例中，[!DNL Automobile Folder Trait]有7個實現。

![](assets/folder_traits_rollup_border.png)

## 資料夾特徵報告{#folder-traits-reporting}

[!UICONTROL Folder traits] 從下方資料夾結構的特徵中擷取所有使用者。如果您將特徵從資料夾移至另一個資料夾，變更會像特徵規則變更一樣傳播至[資料收集伺服器](../../reference/system-components/components-data-collection.md)。 下次報表執行時會更新報表，以反映報表日期範圍(1、7、14、30、60、90)中的此變更。 前幾天的舊報表數字不會變更。

## 角色型存取控制(RBAC)權限{#role-based-access-controls}

對於使用[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])的公司，具有適當[!UICONTROL RBAC]權限的使用者可以變更與[!UICONTROL folder trait]相關聯的資料來源。 使用者必須屬於具有下列其中一項的群組：

* `READ` 和特 `WRITE` 徵資料來源的群組權限。
* `VIEW_ALL_TRAITS` 和特 `EDIT_ALL_TRAITS` 徵資料來源的萬用字元權限。

在[管理檔案](../../features/administration/administration-overview.md#create-group)中了解如何指派[!UICONTROL RBAC]權限。

## 限制和其他考量 {#limits}

| 項目 | 說明 |
|---|---|
| 特徵類型 | [!UICONTROL Onboarded traits] 並 [!UICONTROL algorithmic traits] 且最多為頻率貢獻1 [!UICONTROL folder trait]個實現。 |
| 在資料夾之間移動特徵 | 將特徵從資料夾移至另一個資料夾會取消該特徵從第一個資料夾特徵的資格，並使其符合第二個[!UICONTROL folder trait]的資格。 這表示如果您刪除或移動資料夾中的特徵，則使用資料夾特徵作為區段運算式時，特徵母體中的使用者將會從區段中取消分段。 <br> 將Adobe Analytics區段或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立新的對應唯讀區段和特徵。您無法編輯或變更這些特徵的儲存位置，不能從Audience Manager。 不過，您對映的Adobe Analytics區段或報表套裝所執行的任何變更都會反映在Audience Manager中。 |
| 系統變數 | [!UICONTROL Folder traits] 無法在事件呼叫中使用參數 `d_sid` 實現。 |
| 報表 | [!UICONTROL Folder traits] 是自動計算的特徵，不會出現在 **[!UICONTROL Overlap Reports]**&#x200B;中。 |
