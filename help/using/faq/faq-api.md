---
description: 常見API問題與問題。
seo-description: 常見API問題與問題。
seo-title: API常見問答集
solution: Audience Manager
title: API常見問答集
uuid: 822ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API常見問答集{#api-faq}

常見API問題與問題。

<!-- 

faq_api.xml

 -->

REST API文 [件包含](../api/rest-api-main/rest-api-main.md) ，其中包含特定方法和程式碼範例的詳細資訊。

<br> 

**為何使[!UICONTROL DIL]用和方法進行事[!UICONTROL GET]件呼[!UICONTROL POST]叫？**

[!UICONTROL DIL] 根據事件 [!DNL Audience Manager] 呼叫的查 `GET` 詢字串長度，以或方 `POST` 法傳遞資料至。 預設情況下，此行為內 `GET` 置於 `POST` 和方法中。 它不是特定的 [!DNL Audience Manager]。

* [!UICONTROL DIL] 在URL包含2048個 `GET` 或更少字元時，進行事件呼叫。 事 `GET` 件呼叫包含URL中的資料作為查詢字串參數，這些參數會作為鍵值配對傳入。

* [!UICONTROL DIL] 在URL包含2048 `POST` 個以上字元時，進行事件呼叫。 事 `POST` 件呼叫包含請求內文中的資料。 [!UICONTROL DIL] 將資料放入索引鍵值配對，並將資訊以表單資料的形式傳遞，而非在URL查詢字串中。

雖然每個方法以不同的方式傳送資料，但這不會影響功能。 例如，使用任一方法， [!DNL Audience Manager] 仍會傳送資料至目的地，ID同步正常運作，而且您可以從資料訊號建立特徵。

<br> 

**我能[!UICONTROL REST API]做什麼？**

可 [!UICONTROL REST API]讓您以程式設計方式處理使用者 [!DNL Audience Manager] 介面中大部分的功能和功能。

<br> 

**我要如何取得用戶[!UICONTROL REST API]端ID和密碼？**

請連絡您的合作夥伴解決方案代表以取得 [!DNL API] 存取認證。 我們的API使 [用OAuth 2.0](https://oauth.net/2/) 標準來驗證Token、授權和續約。 如需詳 [細資訊，請參閱](../api/rest-api-main/aam-api-getting-started.md#oauth) 「OAuth驗證」。
