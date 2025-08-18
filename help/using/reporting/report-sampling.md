---
description: 用於某些報表的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: 選定Audience Manager報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 選定Audience Manager報表中的資料取樣和錯誤率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

用於某些報表的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## 資料取樣比例 {#data-sampling-ratio}

有些[!DNL Audience Manager]報告會根據可用資料總量的取樣集來顯示結果。 抽樣資料比率為1:54。 對於使用取樣資料的報表，這表示您的結果以54筆記錄每組1筆記錄為基礎。

這些報表使用統計抽樣資料，因為它們需要大量運算能力才能產生結果。 取樣有助於在減少的運算需求、維持系統效能以及提供精確的結果之間取得平衡。

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

產生重疊資料的報表中可能會發生錯誤。 錯誤定義為記錄中符合以下條件的百分比：

* 本來不應該納入報表，但還是被新增了。
* 應該包含在報表中，但卻被排除在外。

請注意，我們的測試和模型顯示錯誤率&#x200B;*會減少*，與資料集中的記錄數成反比。 含有大量記錄的資料集所產生的錯誤會比含有少量記錄的資料集少。 讓我們以更定量的方式檢視此判斷提示。 如下表所示，對於一組記錄，95%的報告結果將低於特定錯誤率。

| 記錄數 | 錯誤率 |
|--- |--- |
| 500 - 1,000 | 95%的錯誤率低於42%。 |
| 1,000 - 1,500 | 95%的錯誤率低於34%。 |
| 10,000 - 50,000 | 95%的錯誤率低於14%。 |
| 50,000 | 95%的錯誤率低於6%。 |
| 100,000 | 95%的錯誤率低於4%。 |
| 500,000 （或更多） | 95%的錯誤率低於2%。 |

## 使用Minhash取樣方法 {#minhash}

Audience Manager以[Minhash](https://en.wikipedia.org/wiki/MinHash)取樣方法為基礎，在One Permentation雜湊資料草圖上，使用新方法計算特徵和區段估計值。 此新方法產生的變異數低於積木相似度的標準估計器。 請參閱下節，瞭解使用此方法的報表。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用取樣資料的報表 {#reports-using-sampled-data}

使用統計抽樣資料和Minhash抽樣方法的[!DNL Audience Manager]報表包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計抽樣 | Minhash取樣方法 |
|--- |--- |
| [可定址的受眾](../features/addressable-audiences.md)資料（客戶和區段層級資料）。 | [重疊報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特徵對特徵、區段對特徵、區段對區段） |
| [的](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)總裝置[!UICONTROL Profile Merge Rule]量度。 | [特徵建議](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md)在[!UICONTROL Search]索引標籤和任何[!UICONTROL Saved Searches]中使用抽樣資料 | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
