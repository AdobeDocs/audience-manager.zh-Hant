---
description: 資料夾特性可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。
keywords: 區段大小估計器；sse
seo-description: 資料夾特性可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。
seo-title: 資料夾特性
solution: Audience Manager
title: 資料夾特性
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# 資料夾特性：關於關於 {#folder-traits-about}

[!UICONTROL Folder traits] 可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。

## 使用資料夾特性的優點 {#benefits}

A [!UICONTROL folder trait] 包含父資料夾中的所有特徵及其關聯的子資料夾。這可讓您在不同的檔案夾層級自動細分和定位使用者。例如，假設您的檔案夾結構如下：

`*` Electronics(parent)

`*` 筆記型電腦(兒童)

`*` 品牌(子系)

[!UICONTROL Folder traits] 可讓這些資料夾中的所有使用者自動建立 [!DNL Electronics][!UICONTROL Folder Trait] (根據父資料夾的名稱)。此外，此程序會在您向下移動檔案結構時重復。在此情況下，資料夾特性會擷取「筆記型電腦」和「品牌」檔案夾中所有使用者自動建立的筆記型電腦 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 可在區段運算式中選取。選取a [!UICONTROL folder trait] 相當於選取該資料夾內的所有特性及其與 [!UICONTROL OR] 群組的子檔案夾。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特徵實作-最近一次與頻度 {#folder-traits-realization}

資料夾特徵的頻率計數是資料夾及其子資料夾中特徵的實作總和。下圖顯示「A」、「B」和「C」，並在「汽車」資料夾中即時顯示。假設每個特徵都有下列實作：

* 特徵A：5
* 特徵B：1
* 特徵C：1

在這種情況下 [!DNL ]，汽車 [!UICONTROL Folder Trait] 有七個實作。

![](assets/folder_traits_rollup_border.png)

## 資料夾特徵報告 {#folder-traits-reporting}

[!UICONTROL Folder traits] 從其下方的資料夾結構中擷取所有使用者的特徵。如果您將特徵從資料夾移到另一個資料夾，變更將會像特徵規則變更一樣傳播至 [資料收集伺服器](../../reference/system-components/components-data-collection.md) 。下次報告執行中的報告更新會反映此變更，反映報告日期範圍(1、7、14、30、60、90)。前一天的舊報表編號不會變更。

## 角色存取控制(RBAC)權限 {#role-based-access-controls}

對於使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，具有適當 [!UICONTROL RBAC] 權限的使用者可以變更與此關聯的資料來源 [!UICONTROL folder trait]。使用者必須屬於屬於群組的群組：

* `READ``WRITE` 以及特徵資料來源的群組權限。
* `VIEW_ALL_TRAITS` 以及 `EDIT_ALL_TRAITS` 特徵資料來源的萬用字元權限。

瞭解如何在 [!UICONTROL RBAC][我們的管理文件中指派權限](../../features/administration/administration-overview.md#create-group)。

## 限制及其他考量事項 {#limits}

| 項目 | 說明 |
|---|---|
| 特徵類型 | [!UICONTROL Onboarded traits][!UICONTROL algorithmic traits] 並將大部份的實現貢獻給一個 [!UICONTROL folder trait]頻率。 |
| 在檔案夾之間移動特徵 | 將特徵從資料夾移動至另一個資料夾會將特徵從第一個檔案夾特徵中排除，並將其限定為第二 [!UICONTROL folder trait]個特徵。這表示如果您從資料夾刪除或移動特徵，則特徵的人口族群中的使用者將使用資料夾特徵作為區段運算式，將區段取消分段。<br> 將Adobe Analytics區段或報表套裝對應至Experience Cloud組織時，Audience Manager會自動建立新的對應區段和特性。您無法從Audience Manager編輯或變更這些特性的儲存位置。不過，您在對應的Adobe Analytics區段或報表套裝上執行的任何變更，都會反映在Audience Manager中。 |
| 系統變數 | [!UICONTROL Folder traits] 無法在使用 `d_sid` 參數的事件呼叫中實現。 |
| 報告 | [!UICONTROL Folder traits] 是autoc的特徵，不會出現 **[!UICONTROL Overlap Reports]**&#x200B;在其中。 |