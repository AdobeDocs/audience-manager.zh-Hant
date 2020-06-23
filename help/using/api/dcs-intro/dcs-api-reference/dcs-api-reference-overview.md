---
description: DCS API程式碼、方法和程式的概念資訊、說明和定義。
seo-description: Adobe Audience Manager(AAM)中DCS API程式碼、方法和程式的概念資訊、說明和定義。
seo-title: Adobe Audience Manager(AAM)中的DCS API參考概觀
title: DCS API 參考概述
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# DCS API 參考概述

程式碼、方法和程式的概 [!DNL DCS API] 念資訊、說明和定義。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方 [!DNL DCS API] 法傳送資料至。

* [DCS 錯誤碼、訊息和範例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   資料收集伺服器(DCS)依程式碼ID以數值順序列出產生的錯誤碼和訊息。

* [ID監控和密碼清單](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS會監控其收到的ID，並將短時間內以異常高速率傳送的ID新增至拒絕清單。

* [DCS 區域 ID、位置與主機名稱](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)。

   對DCS進行呼叫時，需要地區DCS伺服器主機名稱。 這是因為DCS會在地理位置接近網站訪客的資料中心儲存資訊。 如果您將查詢傳送至錯誤的DCS，則查詢會有效，但這些呼叫會很低效，而且會延遲回應。 若要提出DCS請求，請將地區ID與其對應的地區主機名稱相符，並使用正確的主機名稱來建立查詢。

* [格式化 DCS 呼叫中的索引鍵值配對](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   進行呼叫時，DCS會接受標準或序號格式的金鑰值資料。 請檢閱本節，以瞭解如何設定標準和序號關鍵值資料的格式。

* [競爭條件與錯誤處理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   說明如何防止競賽條件和DCS錯誤處理。

* [DCS API 呼叫的支援屬性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)。

   列出並說明您可傳入資料收集伺服器(DCS)的語法和支援的屬性（或金鑰值配對）。 此資訊可協助您格式化DCS要求，並瞭解此系統傳回的參數。
