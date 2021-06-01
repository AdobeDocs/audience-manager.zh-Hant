---
description: 伺服器對伺服器(S2S)API提供的程式碼和方法可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理此資訊。
seo-description: 伺服器對伺服器(S2S)API提供的程式碼和方法可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中處理此資訊。
seo-title: 用於伺服器對伺服器資料傳輸的 DCS API
solution: Audience Manager
title: 用於伺服器對伺服器資料傳輸的 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# 用於伺服器對伺服器資料傳輸的 DCS API{#dcs-apis-for-server-to-server-data-transfers}

伺服器對伺服器([!UICONTROL S2S])[!DNL API]提供的代碼和方法可讓您發送和接收[!DNL DCS]用戶資料，並在您自己的系統或應用程式中處理此資訊。

## 常見使用案例{#common-use-cases}

[!UICONTROL Server-to-server] 轉移可協助您根據訪客興趣自訂登錄頁面或其他互動。某些常見使用案例包括：

* 站上個人化：根據訪客所屬區段動態新增相關內容及動作呼叫，量身打造您網站上的訪客體驗。
* 改善客戶服務：透過伺服器對伺服器的資料傳輸，將[!DNL Audience Manager]區段匯入[!DNL CRM]或其他系統。 此資料可提供呼叫服務或線上聊天營運商有關客戶的相關個人化資訊。

## 需求：使用者ID和地區伺服器名稱 {#requirements}

[!UICONTROL DCS API]需要使用者ID和地區ID來驗證和提出資料請求。

* 由於您需要將資料與特定訪客建立關聯，因此需要使用者ID。
* 需要地區ID，才能將呼叫系結回伺服器名稱，且因為使用者資料儲存在地理位置上最接近網站訪客的資料中心。

## 快速入門 {#getting-started}

目前，本指南涵蓋如何：

* 從您已接收為[!DNL Audience Manager]客戶的[!DNL DCS]檔案中取得使用者和地區ID。

* 如果您使用[!DNL Visitor ID Service]，請取得使用者和地區ID。
* 在您擁有使用者和地區ID後，對[!DNL DCS]進行呼叫。

我們會在新方法可用時加以新增。 請參閱下列章節以開始使用。

* [從 DCS 回應取得使用者 ID 和區域。](dcs-aam-ids.md)
* [透過Experience CloudID取得使用者ID和地區……](dcs-mcid-ids.md)
* [發出伺服器對伺服器 DCS API 呼叫](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 參考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

