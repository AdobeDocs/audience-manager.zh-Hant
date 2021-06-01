---
description: 說明 Audience Manager 區段的元件、用來設定對象資格標準的運算式，以及在事件呼叫中如何傳輸資料。
landing-page-description: 說明區段的元件、用來設定對象資格標準的運算式，以及如何傳輸資料。
seo-title: 訊號、特徵和區段
solution: Audience Manager
title: 訊號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 參考
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals]、  [!UICONTROL Traits]和  [!UICONTROL Segments] {#signals-traits-and-segments}

說明[!DNL Audience Manager] [!UICONTROL segment]的元件、用於設定對象資格標準的運算式，以及在事件呼叫中如何傳輸資料。

## 組成與用途

[!DNL Audience Manager] 資料包 [!UICONTROL signals]含、  [!UICONTROL traits]、  [!UICONTROL segments]以及相關的資格規則。資料元素和規則會結合以建立[!UICONTROL segments]。 [!UICONTROL Segments] 將網站訪客組織到相關群組中。下表定義[!DNL Audience Manager] [!UICONTROL segment]中的三個主要元件。

| 元素 | 包含 | 範例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是中最小的資料單 [!DNL Audience Manager] 位，以索引鍵 [值配對表示](../reference/key-value-pairs-explained.md)。<br><br><ul><li>索引鍵是定義資料集的常數（例如性別、顏色、價格）。</li><li>值是與常數相關的變數（例如，男性/女性、綠色、100）。</li></ul>比較運算子連接鍵值對並設定它們之間的關係。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一個或多個[!UICONTROL signals]的組合。<br><br> [!DNL Boolean] 運算式和比較運算子可讓您建立 [!UICONTROL trait] 資格規則。<br><br>使用和組的組合建立精確的資 [!UICONTROL traits] 格 [!UICONTROL trait] 要求。 | 從可用的[!UICONTROL signals]中，您可以建立以下表示的`High End Camera Browser`規則：`product=camera AND price>1000` |
| [!UICONTROL Segment] | 共用一組共同屬性且符合相關[!UICONTROL traits]資格的使用者。 [!DNL Boolean] 運算式，以及時近/頻度需求，可讓您建立資 [!UICONTROL segment] 格規則。<br><br> 結合和規則，建立精確的資 [!UICONTROL trait] 格 [!UICONTROL segment] 要求。 | 從可用的[!UICONTROL traits]和[!UICONTROL signals]中，您可以建立以下表示的[!UICONTROL segment]規則：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下圖保留[!UICONTROL signals]、[!UICONTROL traits]和[!UICONTROL segments]之間關係的心理注釋。

![](assets/signals-traits-segments.png)

**使用 [!UICONTROL Traits] 視覺 [!UICONTROL Segment] 工具和程式碼編輯器建立和規則**

用戶端透過[!DNL Audience Manager]使用者介面中的視覺工具和程式碼編輯器管理[!UICONTROL traits]和[!UICONTROL segments]。 視覺化工具可讓您使用搜尋功能、快顯選項、下拉式功能表以及拖放功能來建立規則。 程式碼編輯器可讓進階使用者以程式設計方式開發受眾細分條件。

**事件呼叫傳送資料至[!DNL Audience Manager]**

事件呼叫會將資料從您的網站傳送至[!DNL Audience Manager]。 呼叫包含[!DNL HTTP]請求中的[!UICONTROL signal]、[!UICONTROL trait]和[!UICONTROL segment]資料。 事件本身是[!DNL URL]字串的`/event`部分之後的所有內容。 如以下範例所示，此程式只需要單一事件呼叫，即可將多個變數傳入[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [區段：用途、構成和規則](../features/segments/segments-purpose.md)

