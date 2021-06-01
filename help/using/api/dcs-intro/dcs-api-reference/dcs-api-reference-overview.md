---
description: DCS API程式碼、方法和程式的概念資訊、說明和定義。
seo-description: Adobe Audience Manager(AAM)中DCS API程式碼、方法和程式的概念資訊、說明和定義。
seo-title: Adobe Audience Manager(AAM)中的DCS API參考概述
title: DCS API 參考概述
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# DCS API 參考概述

[!DNL DCS API]代碼、方法和進程的概念資訊、說明和定義。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法將資料傳送至[!DNL DCS API]。

* [DCS 錯誤碼、訊息和範例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   資料收集伺服器(DCS)產生的錯誤碼和訊息會依程式碼ID以數值順序列出。

* [ID監控與封鎖](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS會監控收到的ID，並將在短時間內以異常高的頻率傳送的ID新增至拒絕名單。

* [DCS 區域 ID、位置與主機名稱。](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   呼叫DCS時需要地區DCS伺服器主機名稱。 這是因為DCS會將資訊儲存在地理位置鄰近網站訪客的資料中心。 如果您將查詢傳送至錯誤的DCS，則您的查詢會有效，但這些呼叫效率低下，且可能會延遲回應。 若要提出DCS要求，請將地區ID與其對應的地區主機名稱相符，並以適當的主機名稱來建立查詢。

* [格式化 DCS 呼叫中的索引鍵值配對](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   發出呼叫時，DCS會接受標準或序列化格式的機碼值資料。 請參閱本節，了解如何格式化標準和序列化鍵值資料的資訊。

* [競爭條件與錯誤處理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   說明如何防止競爭條件和DCS錯誤處理。

* [DCS API 呼叫的支援屬性。](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出並說明您可傳遞至資料收集伺服器(DCS)的語法和支援的屬性（或機碼值組）。 此資訊可協助您設定DCS請求的格式，並了解此系統傳回的參數。
