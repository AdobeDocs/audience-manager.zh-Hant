---
description: 簡單像素（可用來授與使用者特徵的資格）會執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數量的像素。 像素字串包含簡單ID或機碼值組。
seo-description: 簡單像素（可用來授與使用者特徵的資格）會執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數量的像素。 像素字串包含簡單ID或機碼值組。
seo-title: 以像素為基礎的資料傳輸
solution: Audience Manager
title: 以像素為基礎的資料傳輸
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: 傳入資料傳輸
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 5%

---

# 以像素為基礎的資料傳輸 {#pixel-based-data-transfers}

簡單像素（可用來授與使用者特徵的資格）會執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數量的像素。 像素字串包含簡單ID或機碼值組。

<!-- c_rt_inbound_pixel_transfers.xml -->

要啟用傳入資料傳輸，供應商和客戶端將：

1. 決定您希望供應商或合作夥伴觸發哪些特徵。
1. 取得特徵的像素。 在特徵清單畫面中，將滑鼠指標暫留在&#x200B;**[!UICONTROL Actions]**&#x200B;欄上，然後按一下所需特徵的&#x200B;**[!UICONTROL Get trait URL]**&#x200B;符號。
1. 將[!DNL URL]提供給供應商或合作夥伴。

## 範例

此基本事件呼叫會將特徵ID 1234傳送至[!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以序列化事件呼叫中的特徵ID，以協助減少頁面的`HTTP`流量。 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
