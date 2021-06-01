---
description: 用於某些報表的取樣方法的摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: 用於某些報表的取樣方法的摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-title: 所選 Audience Manager 報表中的資料取樣和錯誤率
solution: Audience Manager
title: 所選 Audience Manager 報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: 報表參考
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# 所選 Audience Manager 報表中的資料取樣和錯誤率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

用於某些報表的取樣方法的摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## 資料採樣率{#data-sampling-ratio}

有些[!DNL Audience Manager]報表會根據可用資料總量的取樣集來顯示結果。 採樣資料比為1:54。 對於使用取樣資料的報表，這表示您的結果是以每54筆記錄中的1筆記錄為基礎。

這些報表使用統計取樣資料，因為它們需要大量的運算能力才能產生結果。 抽樣有助於在減少的計算需求、維護系統效能和提供準確結果之間取得平衡。

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 錯誤率{#error-rates}

產生重疊資料的報表中可能會發生錯誤。 錯誤的定義是：

* 不應包含在報表中，但已新增。
* 本該包含在報表中，但未列入。

請務必注意，我們的測試和模型顯示錯誤率&#x200B;*以與資料集中記錄數相反的比例減少*。 具有大量記錄的資料集產生的錯誤比具有少量記錄的資料集少。 讓我們用更定量的方式來看看這個論斷。 如下表所示，若有一組記錄，95%的報表結果將低於特定錯誤率。

| 記錄數 | 錯誤率 |
|--- |--- |
| 500 - 1,000 | 95%的錯誤率低於42%。 |
| 1,000 - 1,500 | 95%的錯誤率低於34%。 |
| 1~5萬 | 95%的錯誤率低於14%。 |
| 50,000 | 95%的錯誤率低於6%。 |
| 十萬 | 95%的錯誤率低於4%。 |
| 500,000（或更多） | 95%的錯誤率低於2%。 |

## 使用Minhash取樣方法 {#minhash}

基於[Minhash](https://en.wikipedia.org/wiki/MinHash)採樣方法，Audience Manager在單置換哈希資料草圖上使用新的方法來計算特徵和段估計。 這種新方法產生的方差比標準估計的Jaccard相似性要小。 請參閱下節，了解使用此方法的報表。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用取樣資料{#reports-using-sampled-data}的報表

[!DNL Audience Manager]使用統計取樣資料和Minhash取樣方法的報表包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計抽樣 | Minhash抽樣方法 |
|--- |--- |
| [可定](../features/addressable-audiences.md) 址對象資料（客戶和區段層級資料）。 | [重疊報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特徵對特徵、區段對特徵和區段對區段） |
| [!UICONTROL Profile Merge Rule]的[總裝置](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)量度。 | [特徵建議](/help/using/features/segments/trait-recommendations.md) |
| [資料探](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 索器會刪除索引標籤中的 [!UICONTROL Search] 取樣資料，以及  [!UICONTROL Saved Searches] | [Audience MarketplaceRecommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
