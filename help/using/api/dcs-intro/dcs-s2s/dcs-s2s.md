---
description: 伺服器對伺服器(S2S) API提供程式碼和方法，可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理這些資訊。
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: 用於伺服器對伺服器資料傳輸的DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 用於伺服器對伺服器資料傳輸的DCS API{#dcs-apis-for-server-to-server-data-transfers}

伺服器對伺服器([!UICONTROL S2S]) [!DNL API]提供程式碼和方法，可讓您傳送和接收[!DNL DCS]使用者資料，並在您自己的系統或應用程式中處理這些資訊。

## 常見使用案例 {#common-use-cases}

[!UICONTROL Server-to-server]傳輸可協助您根據訪客興趣自訂登陸頁面或其他互動。 常見的使用案例包括：

* 站上個人化：根據訪客所屬的區段動態新增相關內容和行動號召，以量身打造訪客在您網站上的體驗。
* 改善客戶服務：透過伺服器對伺服器資料傳輸，將[!DNL Audience Manager]區段匯入[!DNL CRM]或其他系統。 此資料可提供電話服務或線上聊天操作員有關客戶的相關個人化資訊。

## 需求：使用者ID與地區伺服器名稱 {#requirements}

[!UICONTROL DCS API]需要使用者ID與地區ID才能驗證及提出資料要求。

* 使用者ID為必要項，因為您必須將資料與特定訪客建立關聯。
* 區域ID是將呼叫連結回伺服器名稱所必需，而且因為使用者資料會儲存在地理位置上最接近網站訪客的資料中心。

## 快速入門 {#getting-started}

目前，本指南涵蓋如何：

* 從您可能已作為[!DNL DCS]客戶收到的[!DNL Audience Manager]檔案中取得使用者和地區ID。

* 如果您使用[!DNL Visitor ID Service]，請取得使用者和地區ID。
* 在擁有使用者和地區ID後，呼叫[!DNL DCS]。

我們會在新方法可用時加以新增。 請參閱下列章節以開始使用。

* [從DCS回應取得使用者ID和區域](dcs-aam-ids.md)
* [透過Experience Cloud ID取得使用者ID和區域……](dcs-mcid-ids.md)
* [發出伺服器對伺服器DCS API呼叫](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API參考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
