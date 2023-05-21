---
description: 伺服器到伺服器(S2S)API提供了代碼和方法，使您能夠發送和接收DCS用戶資料，並在您自己的系統或應用程式中使用此資訊。
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: 用於伺服器對伺服器資料傳輸的 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 10%

---

# 用於伺服器對伺服器資料傳輸的 DCS API{#dcs-apis-for-server-to-server-data-transfers}

伺服器到伺服器([!UICONTROL S2S]) [!DNL API]提供代碼和方法，以便您發送和接收 [!DNL DCS] 並在您自己的系統或應用程式中使用此資訊。

## 常用案例 {#common-use-cases}

[!UICONTROL Server-to-server] 轉接可以幫助您根據訪問者興趣定制登錄頁或其他交互。 一些常見使用案例包括：

* 現場個性化：通過根據訪問者所屬的網段動態添加相關內容和行動要求，定制訪問者在您的站點上的體驗。
* 改進客戶服務：導入 [!DNL Audience Manager] 段 [!DNL CRM] 或通過伺服器到伺服器的資料傳輸。 該資料可向呼叫服務或線上聊天操作員提供有關客戶的相關個性化資訊。

## 要求：用戶ID和區域伺服器名 {#requirements}

的 [!UICONTROL DCS API] 需要用戶ID和區域ID來驗證和發出資料請求。

* 需要用戶ID，因為您需要將資料與特定訪問者關聯。
* 需要區域ID將呼叫與伺服器名稱關聯，並且因為用戶資料儲存在地理上最接近站點訪問者的資料中心中。

## 快速入門 {#getting-started}

目前，本指南介紹如何：

* 從中獲取用戶和區域ID [!DNL DCS] 您已接收的檔案 [!DNL Audience Manager] 客戶。

* 如果使用 [!DNL Visitor ID Service]。
* 呼叫 [!DNL DCS] 獲得用戶和區域ID後。

當新方法可用時，我們將添加新方法。 請參閱以下各節以開始。

* [從 DCS 回應取得使用者 ID 和區域。](dcs-aam-ids.md)
* [通過Experience CloudID獲取用戶ID和區域……](dcs-mcid-ids.md)
* [發出伺服器對伺服器 DCS API 呼叫](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 參考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

