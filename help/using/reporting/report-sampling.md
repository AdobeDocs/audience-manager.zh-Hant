---
description: 對一些報告使用的抽樣方法、抽樣誤差率以及根據抽樣資料返回資訊的報告清單進行總結。
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: 所選 Audience Manager 報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 6%

---

# 所選 Audience Manager 報表中的資料取樣和錯誤率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

對一些報告使用的抽樣方法、抽樣誤差率以及根據抽樣資料返回資訊的報告清單進行總結。

## 資料採樣率 {#data-sampling-ratio}

部分 [!DNL Audience Manager] 報告根據可用資料總量的抽樣集顯示結果。 採樣資料比為1:54。 對於使用採樣資料的報告，這意味著您的結果基於每54條記錄中的1條記錄。

這些報告使用統計抽樣資料，因為它們需要巨大的計算能力來生成結果。 採樣有助於在減少的計算需求、維護系統效能和提供準確結果之間達到平衡。

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 錯誤率 {#error-rates}

在生成重疊資料的報告中可能出錯。 錯誤定義為以下記錄的百分比：

* 不應該包括在報告中，但還是應該添加。
* 本該寫在報告裡，但沒寫。

必須注意的是，我們的test和模型顯示了錯誤率 *減少* 與資料集中記錄數成反比。 具有大量記錄的資料集生成的錯誤少於具有少量記錄的資料集。 讓我們從更為定量的角度來看待這個論斷。 如下表所示，對於一組記錄，95%的報告結果將低於特定錯誤率。

| 記錄數 | 錯誤率 |
|--- |--- |
| 500 - 1,000 | 95%的錯誤率低於42%。 |
| 1,000 - 1,500 | 95%的錯誤率低於34%。 |
| 10,000 - 50,000 | 95%的錯誤率低於14%。 |
| 50,000 | 95%的錯誤率低於6%。 |
| 100,000 | 95%的錯誤率低於4%。 |
| 50萬（或更多） | 95%的錯誤率低於2%。 |

## 使用Minhash抽樣方法 {#minhash}

基於 [明哈什](https://en.wikipedia.org/wiki/MinHash) 採樣方法，Audience Manager採用一種新的方法在單置換散列資料草圖上計算特徵和分段估計。 該方法比Jaccard相似度標準估計器的方差小。 有關使用此方法的報告，請參見下節。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用採樣資料的報告 {#reports-using-sampled-data}

的 [!DNL Audience Manager] 使用統計採樣資料和Minhash採樣方法的報告包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計抽樣 | Minhash採樣方法 |
|--- |--- |
| [可定址的受眾](../features/addressable-audiences.md) 資料（客戶和段級資料）。 | [重疊報告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特性到特性、段到特性、段到片段） |
| 的 [設備總數](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 度量 [!UICONTROL Profile Merge Rule]。 | [特徵建議](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 使用採樣資料 [!UICONTROL Search] 頁籤 [!UICONTROL Saved Searches] | [Audience MarketplaceRecommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
