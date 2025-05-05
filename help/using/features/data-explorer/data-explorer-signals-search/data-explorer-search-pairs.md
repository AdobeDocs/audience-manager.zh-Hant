---
description: 根據其各自的索引鍵值配對，搜尋一或多個訊號。
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 按索引鍵值配對搜尋訊號
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 依索引鍵值配對搜尋訊號 {#search-signals-by-key-value-pairs}

根據其各自的索引鍵值配對，搜尋一或多個訊號。
若要搜尋多個訊號，請按一下![新增](assets/icon_add.png)按鈕。 輸入您要搜尋的索引鍵值配對，然後使用下列篩選器來縮小結果的範圍。

* **訊號狀態**：搜尋特徵中包含的訊號、未使用的訊號，或兩者皆搜尋。
* **檢視**&#x200B;的記錄：選取搜尋接收訊號的時間間隔。
* **最小計數**：只顯示所選間隔內具有指定最小總計數的訊號。

>[!IMPORTANT]
>
>為了提供簡化的使用者體驗，機碼值組搜尋結果會根據資料抽樣。 請參閱[資料取樣和錯誤率](/help/using/reporting/report-sampling.md)，以瞭解[!DNL Audience Manager]如何使用資料取樣以及比較索引鍵值搜尋和一般搜尋時為何會出現細微結果變異的詳細資訊。

使用多個索引鍵值配對搜尋訊號時，[!DNL Audience Manager]會使用邏輯&#x200B;**AND**&#x200B;運運算元連結該配對。 例如，假設您使用下列索引鍵值配對來執行搜尋：

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

此搜尋只會傳回符合相同呼叫上所有三個篩選條件的結果： `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`。

![](assets/signals-search.png)

## 從訊號搜尋排除的訊號 {#excluded-signals}

[!UICONTROL Signals Search]未出現Audience Manager所使用且以`d_`和`h_`首碼為前置詞的關鍵變數。 如需詳細資訊，請參閱索引鍵變數[&#128279;](../../traits/trait-variable-prefixes.md)的前置詞要求。

## 區分大小寫與搜尋自動完成 {#case-insensitivity}

索引鍵和值搜尋欄位區分大小寫。 關鍵搜尋欄位包含自動完成的建議。

![](assets/signal-search-suggestions.png)

假設[!DNL Audience Manager]收到下列訊號：

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

當您在索引鍵搜尋欄位中輸入`product`時，您會收到`productCategory`和`product`的自動完成建議。

同樣地，當您搜尋`product == PHONE`時，[!UICONTROL Data Explorer]只會傳回`product == PHONE`的結果。

回填特徵實現也區分大小寫。 包含具有索引鍵值配對`PRODUCT == SMARTPHONE`之訊號的特徵不符合具有索引鍵值配對`product == smartphone`之訊號的資格。
