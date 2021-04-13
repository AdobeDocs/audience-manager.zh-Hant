---
description: 簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數目的像素。 像素字串由簡單ID或金鑰值對組成。
seo-description: 簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數目的像素。 像素字串由簡單ID或金鑰值對組成。
seo-title: 以像素為基礎的資料傳輸
solution: Audience Manager
title: 以像素為基礎的資料傳輸
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: 傳入資料傳輸
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 5%

---

# 以像素為基礎的資料傳輸 {#pixel-based-data-transfers}

簡單像素（可用來限定使用者特徵）執行即時資料傳輸。 Audience Manager介面可讓用戶端自助建立任意數目的像素。 像素字串由簡單ID或金鑰值對組成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要啟用入站資料傳輸，供應商和客戶端將：

1. 確定您希望供應商或合作夥伴觸發哪些特徵。
1. 取得特徵的像素。 在特徵清單畫面中，將滑鼠指標暫留在&#x200B;**[!UICONTROL Actions]**&#x200B;欄上，然後按一下所要特徵的&#x200B;**[!UICONTROL Get trait URL]**&#x200B;符號。
1. 將[!DNL URL]提供給供應商或合作夥伴。

## 範例

此基本事件呼叫會傳送特徵ID 1234至[!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件呼叫中序列化特徵ID，以協助減少頁面的`HTTP`流量。 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
