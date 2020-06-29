---
description: API 的常見疑問與問題。
seo-description: API 的常見疑問與問題。
seo-title: API 常見問題集
solution: Audience Manager
title: API 常見問題集
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# API 常見問題集{#api-faq}

API 的常見疑問與問題。

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 文件中包含特定方法和程式碼範例的詳細資訊。

<br> 

**[!UICONTROL DIL]為何使用[!UICONTROL GET]和[!UICONTROL POST]方法進行事件呼叫？**

[!UICONTROL DIL] 會根據事件呼叫的查詢字串長度，以 `GET` 或 `POST` 方法將資料傳遞至 [!DNL Audience Manager]。預設情況下，此行為內建在 `GET` 和 `POST` 方法中。這不是 [!DNL Audience Manager] 專屬的行為。

* 當 URL 包含 2048 個或更少字元，[!UICONTROL DIL] 會透過 `GET` 進行事件呼叫。`GET` 事件呼叫包含 URL 中作為查詢字串參數的資料，這些參數會作為索引鍵值配對傳入。

* 當 URL 包含超過 2048 個字元，[!UICONTROL DIL] 會透過 `POST` 進行事件呼叫。`POST` 事件呼叫包含請求內文中的資料。[!UICONTROL DIL] 會將資料放入索引鍵值配對中，並將資訊以表單資料的形式傳遞，而非在 URL 查詢字串中傳遞。

雖然每種方法傳遞資料的方式都不同，但這不會影響功能。例如，使用其中任一種方法，[!DNL Audience Manager] 仍會將資料傳送至目的地、ID 同步正常運作，而且您可以從資料訊號建立特徵。

<br> 

**[!UICONTROL REST API]能用來做什麼？**

[!UICONTROL REST API] 可讓您以程式設計方式運用使用者介面中提供的大部分 [!DNL Audience Manager] 特色和功能。

<br> 

**如何取得[!UICONTROL REST API]用戶端 ID 和密碼？**

請聯絡您的合作夥伴解決方案代表，取得 [!DNL API] 存取認證。我們的 API 使用 [OAuth 2.0](https://oauth.net/2/) 標準來進行代號驗證、授權和續約。如需詳細資訊，請參閱 [OAuth 驗證](../api/rest-api-main/aam-api-getting-started.md#oauth)。
