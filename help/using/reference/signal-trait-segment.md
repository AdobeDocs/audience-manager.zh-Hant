---
description: 了解區段的元件，以及用來設定對象資格標準的運算式。 您也可以找到有關如何傳輸資料的資訊。
landing-page-description: 了解區段的元件，以及用來設定對象資格標準的運算式。 您也可以找到有關如何傳輸資料的資訊。
short-description: 了解區段的元件，以及用來設定對象資格標準的運算式。 您也可以找到有關如何傳輸資料的資訊。
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 訊號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits]，和 [!UICONTROL Segments] {#signals-traits-and-segments}

說明 [!DNL Audience Manager] [!UICONTROL segment]，用來設定對象資格標準的運算式，以及在事件呼叫中如何傳輸資料。

## 組成與用途

[!DNL Audience Manager] 資料包含 [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]，以及相關資格規則。 資料元素和規則結合以建立 [!UICONTROL segments]. [!UICONTROL Segments] 將網站訪客組織到相關群組中。 下表定義 [!DNL Audience Manager] [!UICONTROL segment].

| 元素 | 包含 | 範例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是 [!DNL Audience Manager] 和表示為 [索引鍵值配對](../reference/key-value-pairs-explained.md).<br><br><ul><li>索引鍵是定義資料集的常數（例如性別、顏色、價格）。</li><li>值是與常數相關的變數（例如，男性/女性、綠色、100）。</li></ul>比較運算子連接鍵值對並設定它們之間的關係。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一或多個的組合 [!UICONTROL signals].<br><br> [!DNL Boolean] 運算式和比較運算子可讓您建立 [!UICONTROL trait] 資格規則。 <br><br>通過以下組合建立精確的資格要求： [!UICONTROL traits] 和 [!UICONTROL trait] 群組。 | 從可用 [!UICONTROL signals]，您可以建立 `High End Camera Browser` 規則表示為： `product=camera AND price>1000` |
| [!UICONTROL Segment] | 共用一組共同屬性且符合相關資格的使用者 [!UICONTROL traits]. [!DNL Boolean] 運算式，以及時近/頻率要求，可讓您建立 [!UICONTROL segment] 資格規則。<br><br> 通過以下組合建立精確的資格要求： [!UICONTROL trait] 和 [!UICONTROL segment] 規則。 | 從可用 [!UICONTROL traits] 和 [!UICONTROL signals]，您可以建立 [!UICONTROL segment] 規則表示為：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下圖來記住 [!UICONTROL signals], [!UICONTROL traits]，和 [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**建置 [!UICONTROL Traits] 和 [!UICONTROL Segment] 使用可視化工具和代碼編輯器的規則**

客戶端管理 [!UICONTROL traits] 和 [!UICONTROL segments] 可在 [!DNL Audience Manager] 使用者介面。 視覺化工具可讓您使用搜尋功能、快顯選項、下拉式功能表以及拖放功能來建立規則。 程式碼編輯器可讓進階使用者以程式設計方式開發受眾細分條件。

**事件呼叫傳送資料至[!DNL Audience Manager]**

事件呼叫會將資料從您的網站傳送至 [!DNL Audience Manager]. 呼叫包含 [!UICONTROL signal], [!UICONTROL trait]，和 [!UICONTROL segment] 中 [!DNL HTTP] 請求。 事件本身就是 `/event` 部分 [!DNL URL] 字串。 如下列範例所示，此程式只需要單一事件呼叫，即可將多個變數傳入 [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [區段：用途、構成和規則](../features/segments/segments-purpose.md)

