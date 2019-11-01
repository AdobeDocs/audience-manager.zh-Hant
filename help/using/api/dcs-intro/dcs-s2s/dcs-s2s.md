---
description: 伺服器對伺服器(S2S)API提供程式碼和方法，讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理這些資訊。
seo-description: 伺服器對伺服器(S2S)API提供程式碼和方法，讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理這些資訊。
seo-title: 用於伺服器到伺服器資料傳輸的DCS API
solution: Audience Manager
title: 用於伺服器到伺服器資料傳輸的DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 用於伺服器到伺服器資料傳輸的DCS API{#dcs-apis-for-server-to-server-data-transfers}

伺服器對伺服器([!UICONTROL S2S]) [!DNL API]提供程式碼和方法，讓您傳送和接收使用者資料，並在 [!UICONTROL DCS] 您自己的系統或應用程式中處理這項資訊。

## 常見使用案例 {#common-use-cases}

[!UICONTROL Server-to-server] 轉移可協助您根據訪客興趣自訂著陸頁面或其他互動。 一些常見使用案例包括：

* 臨場感個人化：根據訪客所屬的區段動態新增相關內容及行動要求，以量身打造您網站上的訪客體驗。
* 改善客戶服務：透過 [!DNL Audience Manager] 伺服器 [!DNL CRM] 到伺服器的資料傳輸，將區段匯入至其他系統。 這些資料可提供呼叫服務或線上聊天營運商有關客戶的相關個人化資訊。

## 需求：使用者ID和地區伺服器名稱 {#requirements}

需要 [!UICONTROL DCS API] 使用者ID和地區ID才能驗證並提出資料要求。

* 使用者ID是必要的，因為您需要將資料與特定訪客建立關聯。
* 地區ID是將呼叫系結回伺服器名稱的必要條件，而且使用者資料會儲存在地理上最接近網站訪客的資料中心。

## 快速入門 {#getting-started}

目前，本指南涵蓋如何：

* 從您已收到的客戶檔案 [!UICONTROL DCS] 中取得使用者和地區ID [!DNL Audience Manager] 。

* 如果您使用，請取得使用者和地區ID [!DNL Visitor ID Service]。
* 在您擁有使用 [!UICONTROL DCS] 者和地區ID後呼叫。

我們將在新方法推出時加入。 請參閱下列章節以開始使用。

* [從DCS回應取得使用者ID和地區](dcs-aam-ids.md)
* [透過Experience Cloud ID取得使用者ID和地區……](dcs-mcid-ids.md)
* [進行伺服器對伺服器DCS API呼叫](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API參考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

