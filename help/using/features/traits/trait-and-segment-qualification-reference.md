---
description: 特徵限定或特徵實現在Audience Manager中會根據特徵類型的不同而有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
keywords: 特徵限定、特徵實現、獨特特徵實現、UTR、總特徵人口、TTP
seo-description: 特徵限定或特徵實現在Audience Manager中會根據特徵類型的不同而有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
seo-title: 特徵資格參考
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 特徵
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# 特徵和區段資格參考資料 {#trait-qualification-reference}

特徵限定或特徵實現在Audience Manager中會根據特徵類型的不同而有不同的處理方式。 如需特徵類型資格的詳細資訊，請參閱[依特徵類型劃分的特徵資格](#trait-type)。

此外，如需區段資格的詳細資訊，請參閱[即時區段人口與總區段人口](#real-time-segment)。



## 依特徵類型劃分的特徵限定{#trait-type}

| 特徵類型 | 資格標準 |
|---|---|
| 規則型特徵 | 特徵資格會即時發生，因為使用者在瀏覽器中符合特徵資格。 在您[在UI中建立特徵](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)後約4小時，您的使用者將開始符合規則型特徵的資格。 規則型特徵可讓您使用[時近和頻率](../segments/recency-and-frequency.md)控制項來設定廣告頻率上限和其他使用案例。 |
| 已登錄特徵 | 特徵限定在處理傳入檔案後發生，即傳入檔案是[導入到Audience Manager](../../faq/faq-inbound-data-ingestion.md)，即特徵限定發生時。 在建立已登入特徵後，您應等待約4小時，再上傳傳入檔案以進行處理。 對於已登入的特徵，使用者設定檔的資格上限為1。 |
| 演算法特徵 | 對於演算法特徵，使用者設定檔的最大資格數為1。 |
| 資料夾特徵 | 資料夾特徵會匯總其所含特徵的特徵資格。 閱讀[資料夾特徵：關於](about-folder-traits.md)以取得詳細資訊。 |
| 作用中受眾特徵與資料來源同步特徵 | [!UICONTROL Active Audience]特徵包含您的Audience Manager帳戶中管理的所有設備。 [!UICONTROL Data Source Synced Traits] 追蹤與資料來源相關聯的所有使用者。閱讀更多有關[作用中讀者特徵與資料來源同步特徵](client-activity-synced-audience-traits.md)的資訊。 |

## 獨特特徵實現與特徵總數{#unique-trait-realizations}

![獨特性實現](assets/trait-graph.png)

視您希望圖表顯示的結果類型（依[!UICONTROL Device ID]或[!UICONTROL Cross-Device ID]篩選）而定，量度有不同的含義：

按[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是匿名裝置訪客在不同時間範圍內將特徵新增至其描述檔的數目。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其個人資料上具有此特徵的數目。

按[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是已驗證的訪客在不同時間範圍內將特徵新增至其描述檔的數量。
* [!UICONTROL Total Trait Population] 是已驗證訪客在其個人資料上具有此特徵的數量。

用這種方式來考慮數字。 在上述影像中，從[特徵詳細資料](../../features/traits/trait-details-page.md)檢視中，90,173代表昨天瀏覽您屬性的作用中裝置數。 [!UICONTROL Total Trait Population] 55,757代表目前符合此特徵資格的使用者數量。 [!UICONTROL Total Trait Population]圖表旨在顯示可用於分段／定位的使用者總數。 通常，使用者會在120天內保留某個特徵的一部分。

由於我們運行兩個不同的計算作業來計算這兩個種群，因此[!UICONTROL Total Trait Population]總是比[!UICONTROL Unique Trait Realizations]落後24小時。 在上圖中，2月5日的[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]大約為90,300。 90,400個描述檔會在次日新增至[!UICONTROL Total Trait Population]。

為了進一步將重點推回原點，如果您目前遇到10,000位訪客尖峰，他們會出現在明天的[!UICONTROL Unique Trait Realizations]中，但只會在24小時後出現在[!UICONTROL Total Trait Population]中。

特徵實現的任何變化都反映在群體族群中。

## 即時區段人口與總區段人口{#real-time-segment}

![獨特性實現](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]會計算在選定時間間隔內符合選定段並已到達您屬性的設備數。

[!UICONTROL Total Segment Population]會計算在選定時間範圍內符合選定段條件的設備數。 [!UICONTROL 1 Day]報表代表最新的區段人口計數。

用這種方式來考慮數字。 在上述影像中，從[區段詳細資訊](../../features/segments/segment-summary-view.md)檢視中，9,993代表昨天瀏覽您屬性並符合區段資格的作用中裝置數目。 699,532的[!UICONTROL Total Segment Population]代表目前符合此區段資格的裝置總數。 [!UICONTROL Total Segment Population]圖表旨在顯示可用於分段／定位的裝置總數。

由於我們運行兩個不同的計算作業來計算這兩個種群，因此[!UICONTROL Total Segment Population]總是比[!UICONTROL Real-time Segment Population]落後24小時。 在上圖中，您可以看到2月2日的8,116 [!UICONTROL Real-time Segment Population]和[!UICONTROL Total Segment Population] 742,000。 8,116個描述檔會在次日新增至[!UICONTROL Total Segment Population]。

為了進一步將重點推回原點，如果您目前遇到10,000位訪客尖峰，他們會出現在明天的[!UICONTROL Real-time Segment Population]中，但只會在24小時後出現在[!UICONTROL Total Segment Population]中。

## 特徵限定限制{#trait-qualification-limit}

我們會針對每個使用者描述檔強制實施150,000個特徵資格限制，不論是已驗證的描述檔([DPUUID](../../reference/ids-in-aam.md))或裝置ID([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對於[!DNL Audience Manager]的特定實例是唯一的，但UUID會跨[!DNL Audience Manager]平台共用。 對於[!UICONTROL UUID]s，我們在儲存特徵資格時會實施公平政策。 演算法可確保[!UICONTROL UUID]描述檔的平均份數可用於[!DNL Audience Manager]的每個例項。
