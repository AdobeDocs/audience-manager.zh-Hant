---
description: 介紹如何防止競爭情況和DCS錯誤處理。
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: 競爭條件與錯誤處理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# 競爭條件、速率限制和錯誤處理 {#race-conditions-and-error-handling}

介紹如何防止競賽條件和 [!DNL DCS] 錯誤處理。

## 防止種族狀況 {#prevent-race-conditions}

如果同時（或快速連續）向 [!DNL DCS] 在完成對初始查詢的響應並將資料寫入用戶的cookie之前。 競爭條件是不可取的，因為它可能損壞或不正確覆蓋cookie資料。 作為最佳做法，請考慮以下方法來幫助避免此問題：

* 不要同時呼叫或快速連續呼叫 [!DNL DCS] 來自同一用戶。
* 等待每個響應返回，然後再撥打後續電話。

## 速率限制 {#rate-limiting}

如果Adobe檢測到可能對服務可用性產生負面影響的過多DCS API調用，則可能會引入速率限制。

如果啟用了速率限制，您可能會收到 `429 Too Many Requests` DCS調用上的HTTP響應狀態代碼。 收到此HTTP響應時，請稍後重試API調用。

## 錯誤處理 {#error-handling}

錯誤處理僅限於無效或格式錯誤的查詢。 無效請求返回 `HTTP 200 OK` 沒有資料。 另外， [!DNL DCS] 停止處理請求、丟棄特性資料並返回 `HTTP 200 OK` 當用戶：

* 在Audience Manager或合作夥伴級別選擇不跟蹤。
* 來自無效/未選擇的地理區域。
* 禁用瀏覽器Cookie（全部或第三方）。

另請參見 [DCS錯誤代碼、消息和示例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。
