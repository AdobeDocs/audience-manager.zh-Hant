---
description: 資料夾特性可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。
keywords: 區段大小估計器；sse
seo-description: 資料夾特性可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。
seo-title: 資料夾特性
solution: Audience Manager
title: 資料夾特性
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] 可讓您自動將位於相同資料夾內的特性與所有子資料夾整合至可搜尋的區段中。

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. 這可讓您在不同的檔案夾層級自動細分和定位使用者。例如，假設您的檔案夾結構如下：

`*` Electronics(parent)

`*` 筆記型電腦(兒童)

`*` 品牌(子系)

[!UICONTROL Folder traits] 可讓這些資料夾中的所有使用者自動建立 [!DNL Electronics][!UICONTROL Folder Trait] (根據父資料夾的名稱)。此外，此程序會在您向下移動檔案結構時重復。In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] 可在區段運算式中選取。Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

資料夾特徵的頻率計數是資料夾及其子資料夾中特徵的實作總和。下圖顯示「A」、「B」和「C」，並在「汽車」資料夾中即時顯示。假設每個特徵都有下列實作：

* 特徵A：5
* 特徵B：1
* 特徵C：1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] 從其下方的資料夾結構中擷取所有使用者的特徵。If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. 下次報告執行中的報告更新可反映報告日期範圍(1、7、14、30、60、90、終身)之間的此變更。前一天的舊報表編號不會變更。

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. 使用者必須屬於屬於群組的群組：

* `READ``WRITE` 以及特徵資料來源的群組權限。
* `VIEW_ALL_TRAITS` 以及 `EDIT_ALL_TRAITS` 特徵資料來源的萬用字元權限。

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| 項目 | 說明 |
|---|---|
| 特徵類型 | [!UICONTROL Onboarded traits][!UICONTROL algorithmic traits] 並將大部份的實現貢獻給一個 [!UICONTROL folder trait]頻率。 |
| 在檔案夾之間移動特徵 | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. 這表示如果您從資料夾刪除或移動特徵，則特徵的人口族群中的使用者將使用資料夾特徵作為區段運算式，將區段取消分段。 |
| 系統變數 | [!UICONTROL Folder traits] 無法在使用 `d_sid` 參數的事件呼叫中實現。 |
| 報告 | [!UICONTROL Folder traits] 是autoc的特徵，不會出現 **[!UICONTROL Overlap Reports]** 在其中。 |