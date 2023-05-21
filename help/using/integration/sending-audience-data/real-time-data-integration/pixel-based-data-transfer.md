---
description: 簡單像素（可用於限定用戶特徵）執行即時資料傳輸。 Audience Manager介面允許客戶端基於自助服務建立任意數量的像素。 像素字串由簡單ID或鍵值對組成。
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: 以像素為基礎的資料傳輸
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 4%

---

# 以像素為基礎的資料傳輸 {#pixel-based-data-transfers}

簡單像素（可用於限定用戶特徵）執行即時資料傳輸。 Audience Manager介面允許客戶端基於自助服務建立任意數量的像素。 像素字串由簡單ID或鍵值對組成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要啟用入站資料傳輸，供應商和客戶端將：

1. 確定您希望供應商或合作夥伴激發哪些特徵。
1. 獲取特徵的像素。 在traits清單螢幕中，懸停在 **[!UICONTROL Actions]** 的 **[!UICONTROL Get trait URL]** 符號。
1. 提供 [!DNL URL] 供應商或合作夥伴。

## 範例

此基本事件調用將特性ID 1234發送到 [!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件調用中序列化特性ID以幫助減少 `HTTP` 頁面中的流量。 將附加特性ID附加到URL字串，如下例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
