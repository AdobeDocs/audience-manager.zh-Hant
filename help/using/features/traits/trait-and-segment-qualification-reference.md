---
description: 特質鑑定或特質實現在Audience Manager中會因特質類型的不同而被區別對待。 有關特徵鑑定的詳細資訊，請參閱下表。
keywords: 特質鑑定、特質實現、獨特特質實現、UTR、總特質群體、TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 1%

---

# 特徵和區段資格參考資料 {#trait-qualification-reference}

特質鑑定或特質實現在Audience Manager中會因特質類型的不同而被區別對待。 請參閱 [按特質類型劃分的特質鑑定](#trait-type) 有關特徵類型資格的詳細資訊。

此外，請參見 [即時段人口和總段人口](#real-time-segment) 獲得有關分部資格的詳情。



## 按特質類型劃分的特質鑑定 {#trait-type}

| 特性類型 | 資格標準 |
|---|---|
| 基於規則的特徵 | 特徵鑑定是即時的，因為用戶在瀏覽器中符合某一特徵。 用戶將在您完成約4小時後開始符合基於規則的特性 [創造特質](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 的子菜單。 基於規則的特徵允許您使用 [頻率](../segments/recency-and-frequency.md) 用於廣告頻率封蓋和其它使用情形的控制項。 |
| 掛接的特徵 | 在處理入站檔案後發生特性限定，即入站檔案 [導入到Audience Manager](../../faq/faq-inbound-data-ingestion.md) 這就是特質鑑定的時候。 在建立已掛接的特性後，您應等待大約4小時，然後才上載入站檔案以進行處理。 對於已掛載的特徵，用戶配置檔案的最大資格數為1。 |
| 算法特徵 | 對於算法特徵，用戶配置檔案的最大限定數為1。 |
| 資料夾特徵 | 資料夾特徵總結了其所包含的特徵的特性限定。 閱讀 [資料夾特徵：關於](about-folder-traits.md) 的子菜單。 |
| 作用中受眾特徵與資料來源同步特徵 | 安 [!UICONTROL Active Audience] 特性包含您的Audience Manager帳戶中管理的所有設備。 [!UICONTROL Data Source Synced Traits] 跟蹤與資料源關聯的所有用戶。 閱讀有關 [活動受眾特徵和資料源同步特徵](client-activity-synced-audience-traits.md)。 |

## 獨特性實現與總特性群體 {#unique-trait-realizations}

![特徵實現](assets/trait-graph.png)

根據您希望圖形顯示的結果類型（篩選方式） [!UICONTROL Device ID] 或 [!UICONTROL Cross-Device ID])，度量的含義不同：

篩選結果時，按 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內將特性添加到其配置檔案的匿名設備訪問者的數量。
* [!UICONTROL Total Trait Population] 是您的匿名設備訪問者在他們的檔案中具有這個特徵的人數。

篩選結果時，按 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內，已驗證的訪問者數量，這些訪問者已將該特性添加到其個人資料中。
* [!UICONTROL Total Trait Population] 是你經過認證的訪問者在他們的檔案中有這個特點。

用這種方式來考慮數字。 在上圖中，從 [特性詳細資訊](../../features/traits/trait-details-page.md) view, 90,173表示昨天訪問您屬性的活動設備數。 的 [!UICONTROL Total Trait Population] 55,757個是目前符合這一特點的用戶數。 的 [!UICONTROL Total Trait Population] 該數字用於顯示可用於分割/目標的用戶總數。 通常，用戶在120天內仍將是某種特質的一部分。

因為我們運行兩個不同的計算作業來計算兩個種群， [!UICONTROL Total Trait Population] 總是落後 [!UICONTROL Unique Trait Realizations] 24小時。 在上圖中，你可以看到90,400 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 2月5日的價格為9.03萬美元。 90,400個配置檔案添加到 [!UICONTROL Total Trait Population] 第二天。

為了進一步把這個點開回家，如果你現在經歷了10,000人的激增，他們會在明天的遊客中出現 [!UICONTROL Unique Trait Realizations]但只會在24小時後 [!UICONTROL Total Trait Population]。

特質實現的任何變化都反映在部分群體中。

## 即時段人口和總段人口 {#real-time-segment}

![特徵實現](assets/segment-graph.png)

的 [!UICONTROL Real-time Segment Population] 在選定時間間隔內計算符合選定段條件並已達到您的屬性的設備數。

的 [!UICONTROL Total Segment Population] 計算選定時間範圍內符合選定段條件的設備數。 的 [!UICONTROL 1 Day] 報表表示最新段人口計數。

用這種方式來考慮數字。 在上圖中，從 [段詳細資訊](../../features/segments/segment-summary-view.md) view, 9,993表示昨天訪問了您的屬性並符合段條件的活動設備數。 的 [!UICONTROL Total Segment Population] 699,532台是目前符合此段資格的設備總數。 的 [!UICONTROL Total Segment Population] 圖表用於顯示可用於分割/目標的設備總數。

因為我們運行兩個不同的計算作業來計算兩個種群， [!UICONTROL Total Segment Population] 總是落後 [!UICONTROL Real-time Segment Population] 24小時。 在上圖中，你可以看到8,116 [!UICONTROL Real-time Segment Population] 和 [!UICONTROL Total Segment Population] 2月2日的74.2萬。 8,116個配置檔案添加到 [!UICONTROL Total Segment Population] 第二天。

為了進一步把這個點開回家，如果你現在經歷了10,000人的激增，他們會在明天的遊客中出現 [!UICONTROL Real-time Segment Population]但只會在24小時後 [!UICONTROL Total Segment Population]。

## 特質資格限制 {#trait-qualification-limit}

我們為每個用戶配置檔案強制限制150,000個特性資格，無論它是經過身份驗證的配置檔案([DPUUID](../../reference/ids-in-aam.md))或設備ID([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對於特定實例是唯一的 [!DNL Audience Manager],UUID在 [!DNL Audience Manager] 平台。 對於 [!UICONTROL UUID]s，我們在保存特質資格時實行公平政策。 一種算法確保 [!UICONTROL UUID] 配置檔案可用於每個實例 [!DNL Audience Manager]。
