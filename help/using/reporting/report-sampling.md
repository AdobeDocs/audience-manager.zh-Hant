---
description: 部分報告使用的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: 部分報告使用的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-title: 選取Audience Manager報表中的資料取樣和錯誤率
solution: Audience Manager
title: 選取Audience Manager報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9 da-40f1-8774-54304457bb9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

部分報告使用的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. 取樣資料比例為1：54。對於使用取樣資料的報表，這表示您的結果是根據每組54記錄中的記錄。

這些報告會使用取樣的資料，因為他們需要大量的運算能力來產生結果。取樣可在降低計算需求、維護系統效能並提供精確結果之間取得平衡。

在不符合獨特訪客需求的情況下使用取樣排除特徵和區段的報表。這些最低需求如下：

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* 區段：70,000名即時使用者，為期14天。

## Error Rates {#error-rates}

產生重疊資料的報表中可能發生錯誤。錯誤定義為記錄的百分比：

* 不應包含在報表中，但仍可新增。
* 應包含在報表中，但已離開。

It&#39;s important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. 具有許多記錄的資料集會產生比設定少量記錄的設定少的錯誤。讓我們以更量化的方式來審視這項斷言。如下表所示，對於一組記錄，95%的報表結果會低於特定的錯誤率。

| 記錄數 | 錯誤率 |
|--- |--- |
| 500 - 1,000 | 95%處於42%的錯誤率。 |
| 1,000 - 1,500 | 95%處於34%的錯誤率。 |
| 10,000 - 50,000 | 95%的錯誤率低於14%。 |
| 50,000 | 95%低於6%。 |
| 100,000 | 95%低於4%。 |
| 500,000(或更多) | 95%低於2%。 |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [重疊報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (特徵對特徵、區段對特徵和區段對區段)。
* [可定址對象](../features/addressable-audiences.md) 資料(客戶和區段層級資料)。
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
