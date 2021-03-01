---
description: 說明 Audience Manager 區段的元件、用來設定對象資格標準的運算式，以及在事件呼叫中如何傳輸資料。
landing-page-description: 說明區段的元件、用來設定對象資格標準的運算式，以及如何傳輸資料。
seo-title: 訊號、特徵和區段
solution: Audience Manager
title: 訊號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 參考
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---


# [!UICONTROL Signals]、 [!UICONTROL Traits]和  [!UICONTROL Segments] {#signals-traits-and-segments}

說明[!DNL Audience Manager] [!UICONTROL segment]的元件、用來設定觀眾資格標準的運算式，以及在事件呼叫中如何傳送資料。

## 構圖與用途

[!DNL Audience Manager] 資料由、 [!UICONTROL signals]、 [!UICONTROL traits]和相關 [!UICONTROL segments]的資格規則組成。資料元素和規則會結合以建立[!UICONTROL segments]。 [!UICONTROL Segments] 將網站訪客組織成相關群組。下表定義了[!DNL Audience Manager] [!UICONTROL segment]中的三個主要元件。

| 元素 | 由 | 範例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是中最小的資料單 [!DNL Audience Manager] 位，並表示 [為鍵值對](../reference/key-value-pairs-explained.md)。<br><br><ul><li>索引鍵是定義資料集（例如性別、顏色、價格）的常數。</li><li>該值是與常數相關的變數（例如，男性／女性、綠色、100）。</li></ul>比較運算子會加入鍵值對，並設定它們之間的關係。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一種或多種[!UICONTROL signals]的組合。<br><br> [!DNL Boolean] 運算式和比較運算子可讓您建立 [!UICONTROL trait] 資格規則。<br><br>結合群組，建立精確的資 [!UICONTROL traits] 格 [!UICONTROL trait] 要求。 | 從可用的[!UICONTROL signals]中，可以建立`High End Camera Browser`規則，表示為：`product=camera AND price>1000` |
| [!UICONTROL Segment] | 共用一組共同屬性並符合相關[!UICONTROL traits]資格的使用者。 [!DNL Boolean] 運算式，以及時近／頻率需求，可讓您建立 [!UICONTROL segment] 資格規則。<br><br> 結合規則與規則，建立精確的 [!UICONTROL trait] 資格 [!UICONTROL segment] 要求。 | 從可用的[!UICONTROL traits]和[!UICONTROL signals]中，可以建立一個[!UICONTROL segment]規則，表示為：`(product=camera AND type=digital SLR) OR (price>1000)` |

請使用下圖來記住[!UICONTROL signals]、[!UICONTROL traits]和[!UICONTROL segments]之間關係的心理注意事項。

![](assets/signals-traits-segments.png)

**使用 [!UICONTROL Traits] 視覺 [!UICONTROL Segment] 化工具和程式碼編輯器建立和規則**

用戶端在[!DNL Audience Manager]使用者介面中使用視覺化工具和程式碼編輯器來管理[!UICONTROL traits]和[!UICONTROL segments]。 視覺化工具可讓您使用搜尋功能、快顯選項、下拉式選單以及拖放功能來建立規則。 程式碼編輯器提供進階使用者程式設計方式，以開發受眾細分標準。

**事件呼叫傳送資料至[!DNL Audience Manager]**

事件呼叫會從您的網站傳送資料至[!DNL Audience Manager]。 此呼叫包含[!UICONTROL signal]、[!UICONTROL trait]和[!UICONTROL segment]資料。 [!DNL HTTP]事件本身是[!DNL URL]字串`/event`部分後的一切。 如以下範例所示，此程式只需要單一事件呼叫，即可將多個變數傳入[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [區段：用途、構成和規則](../features/segments/segments-purpose.md)

