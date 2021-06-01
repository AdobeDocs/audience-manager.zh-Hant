---
description: 根據個別的索引鍵值組，搜尋一或多個訊號。
seo-description: 根據個別的索引鍵值組，搜尋一或多個訊號。
seo-title: 按索引鍵值配對搜尋訊號
title: 按索引鍵值配對搜尋訊號
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# 按索引鍵值配對搜尋訊號 {#search-signals-by-key-value-pairs}

根據個別的索引鍵值組，搜尋一或多個訊號。
若要搜尋多個訊號，請按一下「![新增](assets/icon_add.png)」按鈕。 輸入您要搜尋的機碼值組，然後使用下列篩選器來縮小結果範圍。

* **信號狀態**:搜尋特徵、未使用的訊號或兩者中包含的訊號。
* **查看**&#x200B;的記錄：選擇搜索接收信號的時間間隔。
* **最小計數**:僅顯示所選間隔內具有指定最小總計的信號。

>[!IMPORTANT]
>
>為了簡化使用者體驗，索引鍵值配對搜尋結果是以資料取樣為基礎。 請參閱[資料取樣和錯誤率](/help/using/reporting/report-sampling.md)，以取得有關[!DNL Audience Manager]如何使用資料取樣的詳細資訊，以及在將索引鍵值搜尋與一般搜尋比較時，為何結果可能會出現微幅變化的原因。

使用多個鍵值對搜索信號時，[!DNL Audience Manager]使用邏輯&#x200B;**AND**&#x200B;運算子連結這些對。 例如，假設您使用下列索引鍵值配對執行搜尋：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜尋只會傳回在同一呼叫上符合所有三個篩選器的結果：`c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 從信號搜索{#excluded-signals}中排除的信號

由Audience Manager使用並以`d_`和`h_`前置詞為前置詞的關鍵變數不會以[!UICONTROL Signals Search]呈現。 如需詳細資訊，請參閱[關鍵變數的前置詞要求](../../traits/trait-variable-prefixes.md) 。

## 不區分大小寫並搜索自動完成{#case-insensitivity}

索引鍵和值搜尋欄位不區分大小寫。 索引鍵搜尋欄位包含自動完成的建議。

![](assets/signal-search-suggestions.png)

假設[!DNL Audience Manager]收到下列訊號：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

在索引鍵搜尋欄位中輸入`product`時，您會收到`productCategory`、`newProduct`、`PRODUCT`和`product`的自動完成建議。

同樣地，當您搜尋`product == phone`時， [!UICONTROL Data Explorer]會同時傳回`PRODUCT == phone`和`product == PHONE`的結果。
回填的特徵實現不區分大小寫。 包含鍵值對`PRODUCT == SMARTPHONE`之訊號的特徵也會以鍵值對`product == smartphone`來限定訊號。
