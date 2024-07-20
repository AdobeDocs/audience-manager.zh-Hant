---
description: 簡單畫素（可用來讓使用者符合特徵資格）會執行即時資料傳輸。 Audience Manager介面可讓使用者端根據自助方式建立任意數量的畫素。 畫素字串由簡單ID或索引鍵值配對組成。
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: 以畫素為基礎的資料傳輸
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# 以畫素為基礎的資料傳輸 {#pixel-based-data-transfers}

簡單畫素（可用來讓使用者符合特徵資格）會執行即時資料傳輸。 Audience Manager介面可讓使用者端根據自助方式建立任意數量的畫素。 畫素字串由簡單ID或索引鍵值配對組成。

<!-- c_rt_inbound_pixel_transfers.xml -->

若要啟用傳入資料傳輸，供應商和使用者端會：

1. 決定您希望廠商或合作夥伴引發哪些特徵。
1. 取得特徵的畫素。 在特徵清單畫面中，將游標暫留在&#x200B;**[!UICONTROL Actions]**&#x200B;欄上，然後按一下所需特徵的&#x200B;**[!UICONTROL Get trait URL]**&#x200B;符號。
1. 將[!DNL URL]提供給廠商或合作夥伴。

## 範例

這個基本事件呼叫會將特徵ID 1234傳送至[!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件呼叫中序列化特徵ID，以協助減少來自頁面的`HTTP`流量。 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
