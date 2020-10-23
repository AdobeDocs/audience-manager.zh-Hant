---
description: 摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: 摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-title: 所選 Audience Manager 報表中的資料取樣和錯誤率
solution: Audience Manager
title: 所選 Audience Manager 報表中的資料取樣和錯誤率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 7%

---


# 所選 Audience Manager 報表中的資料取樣和錯誤率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

摘要說明用於某些報表的取樣方法、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## 資料取樣率 {#data-sampling-ratio}

有些 [!DNL Audience Manager] 報表會根據可用資料總量的取樣集來顯示結果。 採樣資料比為1:54。 對於使用取樣資料的報表，這表示您的結果是以每54個記錄集中的1個記錄為基礎。

這些報表使用統計取樣資料，因為它們需要大量的運算能力才能產生結果。 採樣有助於在減少的計算需求、維持系統效能和提供精確結果之間取得平衡。

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

## 使用Minhash抽樣方法 {#minhash}

基於 [Minhash](https://en.wikipedia.org/wiki/MinHash) 採樣方法，Audience Manager在單置換散列資料草圖上使用一種新方法來計算特徵和分段估計。 該方法比標準Jaccard相似估計方法的方差小。 請參閱以下章節，瞭解使用此方法的報表。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用取樣資料的報表 {#reports-using-sampled-data}

使用 [!DNL Audience Manager] 統計取樣資料和Minhash取樣方法的報表包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計抽樣 | Minhash抽樣方法 |
|--- |--- |
| [可定址的觀眾](../features/addressable-audiences.md) （客戶和區段層級資料）。 | [重疊報表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特徵對特徵、區段對特徵和區段對區段） |
| 「 [裝置總](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 計」量度 [!UICONTROL Profile Merge Rule]。 | [特徵建議](/help/using/features/segments/trait-recommendations.md) |
| [資料總管](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) (Data Explorer)使用標籤中的取樣資 [!UICONTROL Search] 料，以及任何 [!UICONTROL Saved Searches] | [Audience Marketplace建議](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
