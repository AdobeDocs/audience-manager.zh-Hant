---
description: 根據一或多個信號各自的鍵值對來搜索這些信號。
seo-description: 根據一或多個信號各自的鍵值對來搜索這些信號。
seo-title: 按索引鍵值配對搜尋訊號
title: 按索引鍵值配對搜尋訊號
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# 按索引鍵值配對搜尋訊號 {#search-signals-by-key-value-pairs}

根據一或多個信號各自的鍵值對來搜索這些信號。
要搜索多個信號，請按一下![添加](assets/icon_add.png)按鈕。 輸入要搜尋的索引鍵值配對，然後使用下列篩選器縮小結果範圍。

* **信號狀態**:搜索特徵中包含的信號、未使用的信號或兩者。
* **查看以下記錄**:選擇搜索接收信號的時間間隔。
* **最小計數**:僅顯示在選定間隔內具有指定最小總計的信號。

>[!IMPORTANT]
>
>為簡化使用體驗，索引鍵值配對搜尋結果是以資料取樣為基礎。 請參閱[資料取樣和錯誤率](/help/using/reporting/report-sampling.md)，以取得有關[!DNL Audience Manager]如何使用資料取樣，以及為何在比較索引鍵值搜尋與一般搜尋時會出現輕微結果差異的詳細資訊。

當使用多個鍵值對搜索信號時，[!DNL Audience Manager]使用邏輯&#x200B;**AND**&#x200B;運算子連結該對。 例如，假設您使用下列鍵值配對執行搜尋：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜尋只會傳回符合相同呼叫所有三個篩選條件的結果：`c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 信號搜索中排除的信號{#excluded-signals}

Audience Manager使用並加上`d_`和`h_`前置詞的關鍵變數不會由[!UICONTROL Signals Search]呈現。 如需詳細資訊，請參閱[關鍵變數的首碼需求](../../traits/trait-variable-prefixes.md)。

## 大小寫不敏感和搜索自動完成{#case-insensitivity}

索引鍵和值搜尋欄位不區分大小寫。 關鍵搜尋欄位包含自動完成的建議。

![](assets/signal-search-suggestions.png)

假設[!DNL Audience Manager]收到下列信號：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在鍵搜索欄位中輸入`product`時，您會收到自動完成的`productCategory`、`newProduct`、`PRODUCT`和`product`建議。

同樣地，在搜索`product == phone`時，[!UICONTROL Data Explorer]返回`PRODUCT == phone`和`product == PHONE`的結果。
回填的特徵實現不區分大小寫。 包含具有鍵值對`PRODUCT == SMARTPHONE`的信號的特徵也使具有鍵值對`product == smartphone`的信號保持條件。