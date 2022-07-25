---
description: 根據各自的鍵值對搜索一個或多個信號。
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 按索引鍵值配對搜尋訊號
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# 按鍵值對搜索信號 {#search-signals-by-key-value-pairs}

根據各自的鍵值對搜索一個或多個信號。
要搜索多個信號，請按一下 ![添加](assets/icon_add.png) 按鈕 輸入要搜索的鍵值對，然後使用以下篩選器縮小結果範圍。

* **信號狀態**:搜索包含在特徵、未使用信號或兩者中的信號。
* **查看的記錄**:選擇搜索接收信號的時間間隔。
* **最小計數**:僅顯示在選定間隔內具有指定最小總計數的信號。

>[!IMPORTANT]
>
>為獲得簡化的用戶體驗，關鍵值對搜索結果基於資料採樣。 請參閱 [資料採樣和錯誤率](/help/using/reporting/report-sampling.md) 有關 [!DNL Audience Manager] 使用資料採樣，以及將key-value搜索與常規搜索進行比較時可能出現輕微結果變化的原因。

使用多個鍵值對搜索信號時， [!DNL Audience Manager] 使用邏輯 **和** 運算子。 例如，假設您正在使用以下鍵值對執行搜索：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜索將僅返回符合同一呼叫上所有三個篩選器的結果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 從信號搜索中排除的信號 {#excluded-signals}

Audience Manager使用的關鍵變數，以 `d_` 和 `h_` 前置詞不會由 [!UICONTROL Signals Search]。 請參閱 [鍵變數的前置詞要求](../../traits/trait-variable-prefixes.md) 的雙曲餘切值。

## 區分大小寫並自動完成搜索 {#case-insensitivity}

鍵和值搜索欄位區分大小寫。 鍵搜索欄位包括自動完成的建議。

![](assets/signal-search-suggestions.png)

假設 [!DNL Audience Manager] 接收到以下信號：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

輸入 `product` 在鍵搜索欄位中，您將收到自動完成的建議 `productCategory` 和 `product`。

同樣，當你搜索 `product == PHONE`。 [!UICONTROL Data Explorer] 僅返回結果 `product == PHONE`。

回填特性實現也區分大小寫。 包含帶鍵值對的信號的特徵 `PRODUCT == SMARTPHONE` 不用key-value對限定信號 `product == smartphone`。
