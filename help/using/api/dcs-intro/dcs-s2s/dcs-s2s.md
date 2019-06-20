---
description: 伺服器至伺服器(S2S) API提供程式碼和方法，可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理此項資訊。
seo-description: 伺服器至伺服器(S2S) API提供程式碼和方法，可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理此項資訊。
seo-title: 適用於伺服器與伺服器資料傳輸的DCS API
solution: Audience Manager
title: 適用於伺服器與伺服器資料傳輸的DCS API
uuid: 8c369166-c8 a7-46b0-9913-4c027 f5 b1 df9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] 傳輸可協助您根據訪客興趣自訂著陸頁面或其他互動。常見的使用案例包括：

* 臨場感個人化：根據所屬區段動態新增相關內容並呼叫動作，借此縮短訪客在您網站上的體驗。
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. 此資料可提供呼叫服務或線上聊天營運商與客戶相關的個人化資訊。

## Requirements: User IDs and Regional Server Names {#requirements}

[!UICONTROL DCS API] 使用者ID和地區ID需要驗證並進行資料請求。

* 使用者ID是必要的，因為您需要將資料與特定訪客關聯。
* 地區ID是將呼叫系結回伺服器名稱的必要項目，因為使用者資料儲存在與網站訪客最接近的資料中心。

## 快速入門 {#getting-started}

目前，本指南涵蓋如何：

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

當新方法推出時，我們將會加入新方法。請參閱下列章節以開始使用。

* [從DCS回應取得使用者ID和地區](dcs-aam-ids.md)
* [透過Experience Cloud ID取得使用者ID和地區…](dcs-mcid-ids.md)
* [建立伺服器至伺服器DCS API呼叫](dcs-s2s-calls.md)

>[!MORE_贊_ this]
>
>* [DCS API參考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

