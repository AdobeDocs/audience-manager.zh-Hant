---
description: 常見API問題和問題。
seo-description: 常見API問題和問題。
seo-title: API常見問題
solution: Audience Manager
title: API常見問題
uuid: 8222ef0-b50 e-4f48-8021-dffca2828 b7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

常見API問題和問題。

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 文件包含特定方法和程式碼範例的詳細資訊。

<br> 

**為甚麼[!UICONTROL DIL]要使用[!UICONTROL GET]和[!UICONTROL POST]方法呼叫事件？**

[!UICONTROL DIL] 會根據 [!DNL Audience Manager] 事件 `GET` 呼叫 `POST` 的查詢字串長度，將資料傳遞給資料。This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] 在URL包含2048個字元 `GET` 或更少的字元時，會呼叫事件。`GET` 事件呼叫包含URL中的資料作為查詢字串參數，這些參數會以索引鍵值配對傳入。

* [!UICONTROL DIL] 會在URL包含超過 `POST` 2048個字元時呼叫事件呼叫。`POST` 事件呼叫包含請求內文中的資料。[!UICONTROL DIL] 將資料放入關鍵值配對，並將資訊傳遞為表單資料，而非URL查詢字串中的資料。

雖然每個方法以不同方式傳遞資料，但這並不影響功能。For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**我要[!UICONTROL REST API]怎麼做？**

[!UICONTROL REST API]s可讓您以程式設計方式工作，其中大部分 [!DNL Audience Manager] 功能和功能可在使用者介面中使用。

<br> 

**我要如何取得[!UICONTROL REST API]用戶端ID和機密？**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
