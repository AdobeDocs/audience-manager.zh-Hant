---
description: API 的常見疑問與問題。
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: API 常見問題集
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
TQID: https://experienceleague.adobe.com/IKztfem2G3SCH36c-2Qe5cJWVhPWRLQXjU5TEgF9Cgs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 100%

---

# API 常見問題集{#api-faq}

API 的常見疑問與問題。

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 文件中包含特定方法和程式碼範例的詳細資訊。

<br> 

**[!UICONTROL DIL] 為何使用 [!UICONTROL GET] 和 [!UICONTROL POST] 方法進行事件呼叫？**

[!UICONTROL DIL] 會根據事件呼叫的查詢字串長度，以 `GET` 或 `POST` 方法將資料傳遞至 [!DNL Audience Manager]。預設情況下，此行為內建在 `GET` 和 `POST` 方法中。這不是 [!DNL Audience Manager] 專屬的行為。

* 當 URL 包含 2048 個或更少字元，[!UICONTROL DIL] 會透過 `GET` 進行事件呼叫。`GET` 事件呼叫包含 URL 中作為查詢字串參數的資料，這些參數會作為索引鍵值配對傳入。

* 當 URL 包含超過 2048 個字元，[!UICONTROL DIL] 會透過 `POST` 進行事件呼叫。`POST` 事件呼叫包含請求內文中的資料。[!UICONTROL DIL] 會將資料放入索引鍵值配對中，並將資訊以表單資料的形式傳遞，而非在 URL 查詢字串中傳遞。

雖然每種方法傳遞資料的方式都不同，但這不會影響功能。例如，使用其中任一種方法，[!DNL Audience Manager] 仍會將資料傳送至目的地、ID 同步正常運作，而且您可以從資料訊號建立特徵。

<br> 

**[!UICONTROL REST API] 能用來做什麼？**

[!UICONTROL REST API] 可讓您以程式設計方式運用使用者介面中提供的大部分 [!DNL Audience Manager] 特色和功能。

<br> 

**如何取得 [!UICONTROL REST API] 用戶端 ID 和密碼？**

請聯絡您的合作夥伴解決方案代表，取得 [!DNL API] 存取認證。我們的 API 使用 [OAuth 2.0](https://oauth.net/2/) 標準來進行代號驗證、授權和續約。如需詳細資訊，請參閱 [OAuth 驗證](../api/rest-api-main/aam-api-getting-started.md#oauth)。
