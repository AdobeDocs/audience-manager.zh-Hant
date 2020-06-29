---
description: 特徵資格或特徵實現在Audience Manager中會根據特徵類型有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 特徵資格或特徵實現在Audience Manager中會根據特徵類型有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
seo-title: 特徵資格參考
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# 特徵和區段資格參考資料 {#trait-qualification-reference}

特徵資格或特徵實現在Audience Manager中會根據特徵類型有不同的處理方式。 如需特 [徵類型資格的詳細資訊，請參閱](#trait-type) 「依特徵類型的特徵資格」。

此外，如需區 [段資格的詳細資訊，請參閱即時區段人口與總區段人口](#real-time-segment) 。



## 依特徵類型區分特徵限定 {#trait-type}

| 特徵類型 | 資格標準 |
|---|---|
| 規則型特徵 | 特徵資格會即時發生，因為使用者在瀏覽器中符合特徵資格。 在您在UI中建立特徵後大約4小時，您的使用者就 [會開始符合規則](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 。 規則型特徵可讓您使用時 [近和頻率控制](../segments/recency-and-frequency.md) ，來設定廣告頻率上限和其他使用案例。 |
| 已登錄特徵 | 特徵限定會在處理傳入檔案後發生，即傳入檔案會匯 [入Audience Manager](../../faq/faq-inbound-data-ingestion.md) ，也就是特徵限定發生時。 在建立已登入特徵後，您應等待約4小時，再上傳傳入檔案以進行處理。 對於已登入的特徵，使用者設定檔的資格上限為1。 |
| 演算法特徵 | 對於演算法特徵，使用者設定檔的最大資格數為1。 |
| 資料夾特徵 | 資料夾特徵會匯總其所含特徵的特徵資格。 閱讀資 [料夾特徵： 關於](about-folder-traits.md) ，以取得詳細資訊。 |
| 作用中受眾特徵與資料來源同步特徵 | 特 [!UICONTROL Active Audience] 徵包含您Audience Manager帳戶中管理的所有裝置。 [!UICONTROL Data Source Synced Traits] 追蹤與資料來源相關聯的所有使用者。 閱讀更多有關「 [作用中受眾特徵」和「資料來源同步特徵」的資訊](client-activity-synced-audience-traits.md)。 |

## 獨特性實現與特性總量 {#unique-trait-realizations}

![獨特性實現](assets/trait-graph.png)

視您希望圖形顯示的結果類型（依或篩選）而定，量度有 [!UICONTROL Device ID] 不同 [!UICONTROL Cross-Device ID]的含義：

篩選結果時，依 [!UICONTROL Device ID]據：

* [!UICONTROL Unique Trait Realizations] 是匿名裝置訪客在不同時間範圍內將特徵新增至其描述檔的數目。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其個人資料上具有此特徵的數目。

篩選結果時，依 [!UICONTROL Cross-Device ID]據：

* [!UICONTROL Unique Trait Realizations] 是已驗證的訪客在不同時間範圍內將特徵新增至其描述檔的數量。
* [!UICONTROL Total Trait Population] 是已驗證訪客在其個人資料上具有此特徵的數量。

用這種方式來考慮數字。 在上述影像中，從「特 [徵詳細資料](../../features/traits/trait-details-page.md) 」檢視中，90,173代表昨天瀏覽您屬性的作用中裝置數。 55, [!UICONTROL Total Trait Population] 757代表目前符合此特徵資格的使用者數量。 此 [!UICONTROL Total Trait Population] 圖旨在顯示可用於分段／定位的使用者總數。 通常，使用者會在120天內保留某個特徵的一部分。

因為我們運行兩個不同的計算工作來計算這兩個人口族群， [!UICONTROL Total Trait Population] 因此總是落後 [!UICONTROL Unique Trait Realizations] 24小時。 在上圖中，2月5日 [!UICONTROL Unique Trait Realizations] 的 [!UICONTROL Total Trait Population] 人數為90,400 90,400個設定檔會在下 [!UICONTROL Total Trait Population] 一天新增。

為了進一步推動重點，如果您目前體驗到10,000名訪客的尖峰，他們會出現在明天的 [!UICONTROL Unique Trait Realizations]，但只會在24小時後出現在 [!UICONTROL Total Trait Population]。

特徵實現的任何變化都反映在群體族群中。

## 即時區段人口與總區段人口 {#real-time-segment}

![獨特性實現](assets/segment-graph.png)

計算 [!UICONTROL Real-time Segment Population] 在所選時間間隔內符合所選區段且已到達您屬性的設備數。

計 [!UICONTROL Total Segment Population] 算所選時間範圍內符合所選區段的裝置數。 報 [!UICONTROL 1 Day] 表代表最新的區段人口計數。

用這種方式來考慮數字。 在上述影像中，從「區段詳 [細資訊](../../features/segments/segment-summary-view.md) 」檢視中，9,993代表昨天瀏覽您屬性並符合區段資格的作用中裝置數。 699, [!UICONTROL Total Segment Population] 532台代表目前符合此區段資格的裝置總數。 此 [!UICONTROL Total Segment Population] 圖旨在顯示可用於分段／定位的裝置總數。

因為我們運行兩個不同的計算工作來計算這兩個人口族群， [!UICONTROL Total Segment Population] 因此總是落後 [!UICONTROL Real-time Segment Population] 24小時。 在上圖中，您可以看到2月2日 [!UICONTROL Real-time Segment Population] 的8116 [!UICONTROL Total Segment Population] 和742000。 8,116個描述檔會在 [!UICONTROL Total Segment Population] 第二天新增。

為了進一步推動重點，如果您目前體驗到10,000名訪客的尖峰，他們會出現在明天的 [!UICONTROL Real-time Segment Population]，但只會在24小時後出現在 [!UICONTROL Total Segment Population]。

## 特徵資格限制 {#trait-qualification-limit}

我們會針對每個使用者描述檔強制實施150,000個特徵資格限制，不論是已驗證的描述檔([DPUUID](../../reference/ids-in-aam.md))或裝置ID([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對於特定例項是唯一的， [!DNL Audience Manager]但UUID會在平台間共 [!DNL Audience Manager] 用。 因 [!UICONTROL UUID]此，我們在儲存特徵資格時，實行公平政策。 演算法可確保每個例項 [!UICONTROL UUID] 都能有相同的描述檔份額 [!DNL Audience Manager]。

