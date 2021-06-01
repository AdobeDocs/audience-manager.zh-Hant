---
description: 特徵資格（或特徵實現）在Audience Manager中會根據特徵類型而有所不同。 請參閱下表以取得特徵資格的詳細資訊。
keywords: 特徵資格、特徵實現、獨特特徵實現、UTR、特徵總母體、TTP
seo-description: 特徵資格（或特徵實現）在Audience Manager中會根據特徵類型而有所不同。 請參閱下表以取得特徵資格的詳細資訊。
seo-title: 特徵資格參考
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 特徵
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# 特徵和區段資格參考資料 {#trait-qualification-reference}

特徵資格（或特徵實現）在Audience Manager中會根據特徵類型而有所不同。 如需特徵類型資格的詳細資訊，請參閱[依特徵類型的特徵資格](#trait-type)。

此外，如需區段資格的詳細資訊，請參閱[即時區段母體和總區段母體](#real-time-segment)。



## 依特徵類型列出的特徵資格{#trait-type}

| 特徵類型 | 資格標準 |
|---|---|
| 規則型特徵 | 特徵資格會即時發生，因為使用者在瀏覽器中符合特徵資格。 在您[在UI中建立特徵](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)後，約4小時，您的使用者就會開始符合規則型特徵的資格。 規則型特徵可讓您針對廣告頻率限定和其他使用案例使用[造訪間隔和頻率](../segments/recency-and-frequency.md)控制項。 |
| 已上線的特徵 | 特徵資格會在處理傳入檔案後發生，亦即，傳入檔案為[匯入至Audience Manager](../../faq/faq-inbound-data-ingestion.md)，即特徵資格發生時。 建立已上線的特徵後，您應等待約4小時，再上傳入站檔案以進行處理。 針對已上線的特徵，使用者設定檔的資格數上限為1。 |
| 演算法特徵 | 若為演算法特徵，使用者設定檔的資格數上限為1。 |
| 資料夾特徵 | 資料夾特徵會加總其所包含特徵的特徵資格。 閱讀[資料夾特徵：關於](about-folder-traits.md)以取得詳細資訊。 |
| 作用中受眾特徵與資料來源同步特徵 | [!UICONTROL Active Audience]特徵包含您的Audience Manager帳戶中管理的所有裝置。 [!UICONTROL Data Source Synced Traits] 追蹤與資料來源相關聯的所有使用者。深入閱讀[作用中受眾特徵和資料來源同步特徵](client-activity-synced-audience-traits.md)。 |

## 獨特特徵實現與特徵母體總數{#unique-trait-realizations}

![獨特特徵實現](assets/trait-graph.png)

根據您希望圖表顯示的結果類型（由[!UICONTROL Device ID]或[!UICONTROL Cross-Device ID]篩選），量度有不同的含義：

按[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內，將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其設定檔上具有此特徵的數量。

按[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內，將特徵新增至其設定檔的已驗證訪客數量。
* [!UICONTROL Total Trait Population] 是已驗證的訪客在其設定檔上具有此特徵的數量。

用這個方法來考慮數字。 在上圖中，從[特徵詳細資料](../../features/traits/trait-details-page.md)檢視中，90,173代表昨天造訪您屬性的作用中裝置數量。 55,757的[!UICONTROL Total Trait Population]代表目前符合此特徵資格的使用者人數。 [!UICONTROL Total Trait Population]圖表旨在顯示可用於細分/鎖定目標的使用者總數。 使用者通常會持續120天屬於特徵。

因為我們執行兩個不同的計算作業來計算兩個母體，所以[!UICONTROL Total Trait Population]總是比[!UICONTROL Unique Trait Realizations]滯後24小時。 在上圖中，您可以在2月5日看到大約90,400 [!UICONTROL Unique Trait Realizations]和大約90,300的[!UICONTROL Total Trait Population]。 90,400個設定檔會在次日新增至[!UICONTROL Total Trait Population]。

為了進一步將點放回原點，如果您目前遇到10,000位訪客尖峰，這些訪客會顯示在明天的[!UICONTROL Unique Trait Realizations]中，但只會在24小時後顯示在[!UICONTROL Total Trait Population]中。

特徵實現的任何變更都會反映在區段母體中。

## 即時區段母體和總區段母體{#real-time-segment}

![獨特特徵實現](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]會計算在所選時間間隔內符合所選區段資格且已到達您屬性的裝置數。

[!UICONTROL Total Segment Population]會計算選定時間範圍內符合選定段資格的設備數。 [!UICONTROL 1 Day]報表代表最新的區段母體計數。

用這個方法來考慮數字。 在上圖中，從[區段詳細資料](../../features/segments/segment-summary-view.md)檢視中，9,993代表昨天造訪您屬性且符合區段資格的作用中裝置數量。 699,532的[!UICONTROL Total Segment Population]代表目前符合此區段資格的裝置總數。 [!UICONTROL Total Segment Population]圖表旨在顯示可用於細分/鎖定目標的裝置總數。

因為我們執行兩個不同的計算作業來計算兩個母體，所以[!UICONTROL Total Segment Population]總是比[!UICONTROL Real-time Segment Population]滯後24小時。 在上圖中，您可以看到2月2日的8,116 [!UICONTROL Real-time Segment Population]和[!UICONTROL Total Segment Population](742,000)。 8,116個設定檔會在次日新增至[!UICONTROL Total Segment Population]。

為了進一步將點放回原點，如果您目前遇到10,000位訪客尖峰，這些訪客會顯示在明天的[!UICONTROL Real-time Segment Population]中，但只會在24小時後顯示在[!UICONTROL Total Segment Population]中。

## 特徵資格限制{#trait-qualification-limit}

我們會對每個使用者設定檔強制執行150,000個特徵資格限制，無論是已驗證的設定檔([DPUUID](../../reference/ids-in-aam.md))或裝置ID([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對於[!DNL Audience Manager]的特定例項是唯一的，但UUID會在[!DNL Audience Manager]平台間共用。 對於[!UICONTROL UUID]s，我們會在儲存特徵資格時實施公平政策。 演算法可確保[!UICONTROL UUID]設定檔的相等份額可供[!DNL Audience Manager]的每個例項使用。
