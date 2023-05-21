---
description: DCS API代碼、方法和進程的概念資訊、說明和定義。
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: DCS API 參考概述
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 14%

---

# DCS API 參考概述

概念資訊、說明和定義 [!DNL DCS API] 代碼、方法和進程。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   將資料發送到 [!DNL DCS API] 使用GET或POST方法。

* [DCS 錯誤碼、訊息和範例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   資料收集伺服器(DCS)按代碼ID以數字順序列出生成的錯誤代碼和消息。

* [ID監控和密碼清單](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS監視它接收的ID，並將在短時間內以異常高的速率發送的ID添加到拒絕清單。

* [DCS 區域 ID、位置與主機名稱。](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   要調用DCS，需要使用區域DCS伺服器主機名。 這是因為DCS將資訊儲存在地理上靠近站點訪問者的資料中心中。 如果將查詢發送到錯誤的DCS，則查詢將起作用，但這些調用效率低下，可能會延遲響應。 要發出DCS請求，請將區域ID與其相應的區域主機名匹配，並使用正確的主機名來形成查詢。

* [格式化 DCS 呼叫中的索引鍵值配對](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   在進行呼叫時，DCS接受標準或序列化格式的鍵值資料。 有關如何格式化標準值和序列化鍵值資料的資訊，請查看本節。

* [競爭條件與錯誤處理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   介紹如何防止競爭情況和DCS錯誤處理。

* [DCS API 呼叫的支援屬性。](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出並說明可以傳遞到資料收集伺服器(DCS)的語法和支援的屬性（或鍵值對）。 此資訊可幫助您格式化DCS請求並瞭解此系統返回的參數。
