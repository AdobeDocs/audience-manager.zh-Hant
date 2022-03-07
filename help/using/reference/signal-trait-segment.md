---
description: 了解區段的元件，以及用來設定對象資格標準的運算式。您也可以找到有關如何傳輸資料的資訊。
landing-page-description: 了解區段的元件，以及用來設定對象資格標準的運算式。您也可以找到有關如何傳輸資料的資訊。
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 訊號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 16%

---

# [!UICONTROL Signals]。 [!UICONTROL Traits], [!UICONTROL Segments] {#signals-traits-and-segments}

描述 [!DNL Audience Manager] [!UICONTROL segment]、用於設定受眾資格標準的表達式，以及在事件呼叫中如何傳輸資料。

## 構成和用途

[!DNL Audience Manager] 資料 [!UICONTROL signals]。 [!UICONTROL traits]。 [!UICONTROL segments]及相關資格規則。 資料元素和規則組合以建立 [!UICONTROL segments]。 [!UICONTROL Segments] 將站點訪問者組織到相關組。 下表定義了 [!DNL Audience Manager] [!UICONTROL segment]。

| 元素 | 由 | 範例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是 [!DNL Audience Manager] 表示為 [鍵值對](../reference/key-value-pairs-explained.md)。<br><br><ul><li>關鍵是定義資料集（如性別、顏色、價格）的常數。</li><li>該值是與常數（例如，男性/女性，綠色，100）相關的變數。</li></ul>比較運算子將連接鍵值對並設定它們之間的關係。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一個或多個的組合 [!UICONTROL signals]。<br><br> [!DNL Boolean] 表達式和比較運算子允許您建立 [!UICONTROL trait] 資格規則。 <br><br>使用組合建立精確的資格要求 [!UICONTROL traits] 和 [!UICONTROL trait] 組。 | 從可用 [!UICONTROL signals]，您可以建立 `High End Camera Browser` 規則表示為： `product=camera AND price>1000` |
| [!UICONTROL Segment] | 共用一組公用屬性並符合相關資格的用戶 [!UICONTROL traits]。 [!DNL Boolean] 表達式，以及頻率/頻率要求，允許您建立 [!UICONTROL segment] 資格規則。<br><br> 使用組合建立精確的資格要求 [!UICONTROL trait] 和 [!UICONTROL segment] 規則。 | 從可用 [!UICONTROL traits] 和 [!UICONTROL signals]，您可以建立 [!UICONTROL segment] 規則表示為：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下圖，在心理上記下 [!UICONTROL signals]。 [!UICONTROL traits], [!UICONTROL segments]。

![](assets/signals-traits-segments.png)

**生成 [!UICONTROL Traits] 和 [!UICONTROL Segment] 使用可視工具和代碼編輯器的規則**

客戶端管理 [!UICONTROL traits] 和 [!UICONTROL segments] 使用可視工具和代碼編輯器 [!DNL Audience Manager] 用戶介面。 視覺工具允許您使用搜索功能、彈出式選項、下拉菜單以及拖放功能建立規則。 代碼編輯器為高級用戶提供了以寫程式方式制定受眾分割標準的方法。

**事件調用將資料發送到[!DNL Audience Manager]**

事件呼叫將資料從您的網站發送到 [!DNL Audience Manager]。 調用包含 [!UICONTROL signal]。 [!UICONTROL trait], [!UICONTROL segment] 資料 [!DNL HTTP] 請求。 事件本身就是 `/event` 部分 [!DNL URL] 的下界。 如下例所示，此過程只需要一次事件調用即可將多個變數傳遞給 [!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [區段：用途、構成和規則](../features/segments/segments-purpose.md)

