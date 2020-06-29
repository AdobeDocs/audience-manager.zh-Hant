---
description: 簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓客戶建立自助服務的任意數目像素。 像素字串由簡單ID或金鑰值對組成。
seo-description: 簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓客戶建立自助服務的任意數目像素。 像素字串由簡單ID或金鑰值對組成。
seo-title: 以像素為基礎的資料傳輸
solution: Audience Manager
title: 以像素為基礎的資料傳輸
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# 以像素為基礎的資料傳輸 {#pixel-based-data-transfers}

簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓客戶建立自助服務的任意數目像素。 像素字串由簡單ID或金鑰值對組成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要啟用入站資料傳輸，供應商和客戶端將：

1. 確定您希望供應商或合作夥伴觸發哪些特徵。
1. 取得特徵的像素。 在特徵清單畫面中，將滑鼠指標暫留在 **[!UICONTROL Actions]** 欄上，然後按一下所 **[!UICONTROL Get trait URL]** 要特徵的符號。
1. 提供給 [!DNL URL] 供應商或合作夥伴。

## 範例

此基本事件呼叫會傳送特徵ID 1234至 [!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件呼叫中序列化特徵ID，以協 `HTTP` 助減少頁面流量。 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
