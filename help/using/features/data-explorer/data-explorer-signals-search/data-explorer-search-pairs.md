---
description: 根據其各自的索引鍵值配對，搜尋一或多個訊號。
seo-description: 根據其各自的索引鍵值配對，搜尋一或多個訊號。
seo-title: 依關鍵值配對的搜尋訊號
title: 依關鍵值配對的搜尋訊號
uuid: 2a38d0d4-4a2e-4ca5-b9 ec-af9 d4963 d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

根據其各自的索引鍵值配對，搜尋一或多個訊號。
To search for more than one signal, click the ![Add](assets/icon_add.png) button. 輸入您要搜尋的索引鍵值配對，然後使用下列篩選條件縮小結果。

* **訊號狀態**：搜尋特徵、未使用訊號或兩者所包含的訊號。
* **檢視** 下列項目的記錄：選擇要搜尋接收訊號的時間間隔。
* **最低計數**：僅顯示在選定間隔內指定的最小總計數的訊號。

>[!IMPORTANT]
>
>為簡化使用者體驗，關鍵值配對搜尋結果是以資料取樣為基礎。See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. 例如，假設您使用下列索引鍵值配對進行搜尋：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

索引鍵和值搜尋欄位不區分大小寫。關鍵搜尋欄位包含自動完成的建議。

![](assets/signal-search-suggestions.png)

Let&#39;s say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
回填特徵實作不區分大小寫。A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.