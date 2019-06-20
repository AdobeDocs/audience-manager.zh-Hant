---
description: 個別特徵的詳細資料頁面提供特徵名稱、ID、效能度量、定義特徵的運算式、定義為特徵的運算式，以及特徵稽核記錄檔。若要詳列這些詳細資訊，請前往「對象資料>特性」，然後按一下您要處理之特徵的名稱。
seo-description: 個別特徵的詳細資料頁面提供特徵名稱、ID、效能度量、定義特徵的運算式、定義為特徵的運算式，以及特徵稽核記錄檔。若要詳列這些詳細資訊，請前往「對象資料>特性」，然後按一下您要處理之特徵的名稱。
seo-title: 特徵詳細資料頁面
solution: Audience Manager
title: 特徵詳細資料頁面
uuid: 23301376-c1 cc-4778-b8 c4-9831f6739 db9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Trait Details Page {#trait-details-page}

個別特徵的詳細資料頁面提供特徵名稱、ID、效能度量、定義特徵的運算式、定義為特徵的運算式，以及特徵稽核記錄檔。To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## 基本資訊 {#basics}

[!UICONTROL Basic Information] 區段顯示您在建立特徵時完成的必填和選填欄位詳細資訊。這包括特徵類型、特徵ID、說明、資料來源和其他中繼資料等項目。這些詳細資料會依特徵類型(資料夾、已登錄或規則型)而有所不同。

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. 將游標停留在趨勢線上，以查看所選特徵的其他資料。

[!UICONTROL Unique Trait Realizations] 代表在指定時間範圍內將此特徵新增至其描述檔的獨特使用者計數。The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* 對於規則型特徵，特徵資格會即時發生，因為使用者可以在其瀏覽器中取得特徵。
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **獨特特徵實作**：在指定時間範圍內將此特徵新增至其描述檔的獨特使用者數。
* **特徵總數**：目前符合此特徵的獨特使用者人數。

![](assets/traitGraph.png)

## Trait Expression {#trait-expression}

[!UICONTROL Trait Expression] 本節顯示使用者必須符合特徵才能符合特徵的標準。[建立或編輯特徵](../../features/traits/about-trait-builder.md)時，會設定這些規則。

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

[!UICONTROL Segments with this Trait] 區段列出所選特徵所屬的所有區段。您可以按一下區段名稱，查看該區段的詳細資料。

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. 稽核記錄無法用於資料夾或演算法特性。

>[!NOTE]
>
>[!UICONTROL Not Available][!UICONTROL By User] 代表該使用者已刪除該帳戶。

![](assets/traitHistory.png)