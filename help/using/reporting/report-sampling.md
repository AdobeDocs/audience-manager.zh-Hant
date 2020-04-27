---
description: 摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: 摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-title: 選取Audience Manager報表中的資料取樣和錯誤率
solution: Audience Manager
title: 選取Audience Manager報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: 6dca5c8bc338a670050123a94808795705450c3a

---


# 選取Audience Manager報表中的資料取樣和錯誤率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## 資料取樣率與最低需求 {#data-sampling-ratio}

有些 [!DNL Audience Manager] 報表會根據可用資料總量的取樣集來顯示結果。 採樣資料比為1:54。 對於使用取樣資料的報表，這表示您的結果是以每54個記錄集中的1個記錄為基礎。

這些報表使用取樣資料，因為它們需要大量的運算能力才能產生結果。 採樣有助於在減少的計算需求、維持系統效能和提供精確結果之間取得平衡。

使用取樣的報表會在不符合最低獨特訪客需求時排除特徵和區段。 這些最低要求如下：

* 特徵：在14天 [內實現](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) 28,000個獨特特徵。
* 區段：在14天的期間內有70,000名即時使用者。

## 錯誤率 {#error-rates}

產生重疊資料的報表中可能會發生錯誤。 錯誤定義為：

* 不應包含在報表中，但已加入。
* 本應已納入報告，但未列入。

請務必注意，我們的測試和模型顯示錯誤率會 *與資料集中* 記錄數成反比降低。 具有大量記錄的資料集產生的錯誤比具有少量記錄的資料集少。 讓我們以更為定量的方式來看一下這一論斷。 如下表所示，若是一組記錄，95%的報表結果將低於特定錯誤率。

| 記錄數 | 錯誤率 |
|--- |--- |
| 500 - 1,000 | 95%的錯誤率低於42%。 |
| 1,000 - 1,500 | 95%的錯誤率為34%。 |
| 10,000 - 50,000 | 95%的錯誤率低於14%。 |
| 50,000 | 95%的錯誤率低於6%。 |
| 100,000 | 95%的錯誤率低於4%。 |
| 500,000（或以上） | 95%的錯誤率低於2%。 |

## 使用取樣資料的報表 {#reports-using-sampled-data}

使用 [!DNL Audience Manager] 取樣資料的報表包括：

* [重疊報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特徵對特徵、區段對特徵和區段對區段）。
* [可定址的觀眾](../features/addressable-audiences.md) （客戶和區段層級資料）。
* 「 [裝置總](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 計」量度 [!UICONTROL Profile Merge Rule]。
* [資料總管](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) (Data Explorer)在標籤和任何頁籤 [!UICONTROL Search] 中使用取樣資料 [!UICONTROL Saved Searches]。