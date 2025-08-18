---
description: 了解區段的元件，以及用來設定客群資格鑑定標準的運算式。您也可以找到有關如何傳輸資料的資訊。
landing-page-description: 了解區段的元件，以及用來設定客群資格鑑定標準的運算式。您也可以找到有關如何傳輸資料的資訊。
short-description: 了解區段的元件，以及用來設定客群資格鑑定標準的運算式。您也可以找到有關如何傳輸資料的資訊。
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 訊號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals]、[!UICONTROL Traits]和[!UICONTROL Segments] {#signals-traits-and-segments}

說明[!DNL Audience Manager] [!UICONTROL segment]的元件、用來設定對象資格標準的運算式，以及在事件呼叫中如何傳輸資料。

## 構成與用途

[!DNL Audience Manager]資料包含[!UICONTROL signals]、[!UICONTROL traits]、[!UICONTROL segments]和相關資格規則。 資料元素和規則結合以建立[!UICONTROL segments]。 [!UICONTROL Segments]將網站訪客組織到相關群組中。 下表定義了[!DNL Audience Manager] [!UICONTROL segment]中的三個主要元件。

| 元素 | 包含 | 範例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals]是[!DNL Audience Manager]中最小的資料單位，以[索引鍵值配對](../reference/key-value-pairs-explained.md).<br><br>表示<ul><li>索引鍵是定義資料集的常數（例如性別、顏色、價格）。</li><li>值是與常數相關的變數（例如，男性/女性、綠色、100）。</li></ul>比較運運算元聯結機碼值組並設定它們之間的關係。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一或多個[!UICONTROL signals].<br><br>的組合 [!DNL Boolean]運算式和比較運運算元可讓您建立[!UICONTROL trait]資格規則。 <br><br>使用[!UICONTROL traits]和[!UICONTROL trait]群組的組合來建立精確的資格要求。 | 您可以從可用的[!UICONTROL signals]建立表示為`High End Camera Browser`的`product=camera AND price>1000`規則 |
| [!UICONTROL Segment] | 共用一組通用屬性並符合相關[!UICONTROL traits]資格的使用者。 [!DNL Boolean]運算式以及時近/頻率要求可讓您建立[!UICONTROL segment]資格規則。<br><br>使用[!UICONTROL trait]與[!UICONTROL segment]規則的組合來建立精確的資格要求。 | 從可用的[!UICONTROL traits]和[!UICONTROL signals]，您可以建立以[!UICONTROL segment]表示的`(product=camera AND type=digital SLR) OR (price>1000)`規則 |

使用下圖來保留[!UICONTROL signals]、[!UICONTROL traits]與[!UICONTROL segments]之間關係的心智註記。

![](assets/signals-traits-segments.png)

使用視覺化工具和程式碼編輯器&#x200B;**建置[!UICONTROL Traits]和[!UICONTROL Segment]規則**

使用者端使用[!UICONTROL traits]使用者介面中的視覺化工具和程式碼編輯器來管理[!UICONTROL segments]和[!DNL Audience Manager]。 視覺化工具可讓您使用搜尋功能、彈出式選項、下拉式選單及拖放功能來建立規則。 程式碼編輯器為進階使用者提供以程式設計方式開發受眾細分標準的方法。

**事件呼叫傳送資料給[!DNL Audience Manager]**

事件呼叫會將資料從您的網站傳送至[!DNL Audience Manager]。 呼叫在[!UICONTROL signal]要求中包含[!UICONTROL trait]、[!UICONTROL segment]和[!DNL HTTP]資料。 事件本身是`/event`字串的[!DNL URL]部分之後的所有內容。 如下列範例所示，此程式只需要單一事件呼叫，即可將多個變數傳入[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [區段：用途、構成和規則](../features/segments/segments-purpose.md)
