---
description: 特徵資格或特徵實現在Audience Manager中的處理方式會因特徵型別而異。 請參閱下表以瞭解特徵資格的詳細資訊。
keywords: 特徵資格、特徵實現、不重複特徵實現、UTR、總特徵人口、TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# 特徵和區段資格參考 {#trait-qualification-reference}

特徵資格或特徵實現在Audience Manager中的處理方式會因特徵型別而異。 如需特徵型別資格的詳細資訊，請參閱[依特徵型別的特徵資格](#trait-type)。

此外，如需區段資格的詳細資訊，請參閱[即時區段母體及總區段母體](#real-time-segment)。



## 依特徵型別區分的特徵資格 {#trait-type}

| 特徵型別 | 資格條件 |
|---|---|
| 規則型特徵 | 特徵資格會即時進行，因為使用者在其瀏覽器中符合某個特徵的資格。 在您[在UI中建立特徵](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)後，您的使用者將開始符合規則型特徵的資格，時間約為4小時。 規則型特徵可讓您針對廣告頻率上限與其他使用案例使用[造訪間隔和頻率](../segments/recency-and-frequency.md)控制項。 |
| 已上線的特徵 | 特徵資格會在處理傳入檔案之後進行，亦即傳入檔案是[匯入Audience Manager](../../faq/faq-inbound-data-ingestion.md)，而且特徵資格會在這個時間進行。 建立已上線的特徵後，您應等待約4小時再上傳傳入檔案以供處理。 針對已上線的特徵，使用者設定檔的資格數上限為1。 |
| 演演算法特徵 | 對於演演算法特徵，使用者設定檔的資格數上限為1。 |
| 資料夾特徵 | 資料夾特徵可概括其所包含特徵的特質資格。 閱讀[資料夾特徵：關於](about-folder-traits.md)以取得詳細資訊。 |
| 作用中受眾特徵與資料Source同步特徵 | [!UICONTROL Active Audience]特徵包含您Audience Manager帳戶中受管理的所有裝置。 [!UICONTROL Data Source Synced Traits]會追蹤與資料來源相關聯的所有使用者。 深入瞭解[作用中對象特徵和Source同步特徵資料](client-activity-synced-audience-traits.md)。 |

## 不重複特徵實現和特徵總人口數 {#unique-trait-realizations}

![唯一特徵實現](assets/trait-graph.png)

根據您要圖表顯示的結果型別（以[!UICONTROL Device ID]或[!UICONTROL Cross-Device ID]篩選），量度有不同的意義：

依[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations]是在不同時間範圍內將特徵新增至設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Population]是您的匿名裝置訪客在其設定檔中擁有此特徵的數目。

依[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations]是經過驗證的訪客數，這些訪客在不同的時間範圍內將特徵新增至其設定檔。
* [!UICONTROL Total Trait Population]是您的已驗證訪客在其設定檔中擁有此特徵的數量。

以這種方式看待數字。 在上圖中，從[特徵詳細資料](../../features/traits/trait-details-page.md)檢視，90,173代表昨天造訪您屬性的作用中裝置數。 55,757的[!UICONTROL Total Trait Population]代表目前符合此特徵的使用者數量。 [!UICONTROL Total Trait Population]圖是用來顯示可用於細分/目標定位的使用者總數。 通常使用者會保留某個特徵的120天。

因為我們執行兩個不同的運算工作來計算這兩個母體，[!UICONTROL Total Trait Population]總是會比[!UICONTROL Unique Trait Realizations]落後24小時。 在上圖中，您可以在2月5日看到約90,400個[!UICONTROL Unique Trait Realizations]和約90,300個的[!UICONTROL Total Trait Population]。 這90,400個設定檔已於次日新增至[!UICONTROL Total Trait Population]。

若要進一步將點數匯入，如果您目前體驗10,000位訪客的尖峰，他們會在明天的[!UICONTROL Unique Trait Realizations]中出現，但只會在稍後24小時的[!UICONTROL Total Trait Population]中出現。

特徵實現的任何變更都會反映在區段人口中。

## 即時區段母體與總區段母體 {#real-time-segment}

![唯一特徵實現](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]會計算在選取的時間間隔內，符合選取區段資格且已達到您屬性的裝置數量。

[!UICONTROL Total Segment Population]會計算所選時間範圍內符合所選區段資格的裝置數。 [!UICONTROL 1 Day]報表代表最新的區段母體計數。

以這種方式看待數字。 在上圖中，從[區段詳細資料](../../features/segments/segment-summary-view.md)檢視，9,993代表昨天造訪您屬性且符合區段資格的使用中裝置數。 699,532的[!UICONTROL Total Segment Population]代表目前符合此區段資格的裝置總數。 [!UICONTROL Total Segment Population]圖是用來顯示可用於分段/鎖定目標的裝置總數。

因為我們執行兩個不同的運算工作來計算這兩個母體，[!UICONTROL Total Segment Population]總是會比[!UICONTROL Real-time Segment Population]落後24小時。 在上圖中，您可以在2月2日看到8,116 [!UICONTROL Real-time Segment Population]和742,000的[!UICONTROL Total Segment Population]。 這8,116個設定檔會在第二天新增到[!UICONTROL Total Segment Population]。

若要進一步將點數匯入，如果您目前體驗10,000位訪客的尖峰，他們會在明天的[!UICONTROL Real-time Segment Population]中出現，但只會在稍後24小時的[!UICONTROL Total Segment Population]中出現。

## 特徵資格限制 {#trait-qualification-limit}

我們針對每個使用者設定檔強制執行150,000個特徵資格的限制，不論是已驗證的設定檔([DPUUID](../../reference/ids-in-aam.md))或裝置ID ([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID是[!DNL Audience Manager]的特定執行個體所獨有的，但UUID會在[!DNL Audience Manager]平台之間共用。 對於[!UICONTROL UUID]，我們在儲存特徵資格時強制實行公平原則。 演演算法可確保對[!DNL Audience Manager]的每個執行個體都提供[!UICONTROL UUID]設定檔的同等共用。
