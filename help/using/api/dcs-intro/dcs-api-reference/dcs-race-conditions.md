---
description: 說明如何防止競爭條件和DCS錯誤處理。
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

說明如何防止競爭條件，並 [!DNL DCS] 錯誤處理。

## 防止種族條件 {#prevent-race-conditions}

如果您同時傳送多個呼叫（或快速連續）至 [!DNL DCS] 完成回應初始查詢及將資料寫入使用者Cookie之前。 競爭條件不是您預期的，因為可能會損毀或不正確覆寫Cookie資料。 為避免此問題，請考量下列方法：

* 請勿連續快速地向 [!DNL DCS] 來自同一個使用者。
* 等待每個回應返回，再進行後續呼叫。

## 速率限制 {#rate-limiting}

如果Adobe偵測到過多DCS API呼叫，而這些呼叫可能對服務可用性造成負面影響，則可能會引入速率限制。

如果已啟用速率限制，您可能會收到 `429 Too Many Requests` DCS呼叫上的HTTP回應狀態代碼。 收到此HTTP回應時，請稍後再試API呼叫。

## 錯誤處理 {#error-handling}

錯誤處理僅限於無效或格式不良的查詢。 無效的請求會傳回 `HTTP 200 OK` 回應且沒有資料。 此外， [!DNL DCS] 停止處理請求、捨棄特徵資料並傳回 `HTTP 200 OK` 使用者回應時：

* 選擇不在Audience Manager或合作夥伴層級進行追蹤。
* 來自無效/未選取的地理區域。
* 停用瀏覽器Cookie（全部或第三方）。

另請參閱 [DCS錯誤碼、訊息和範例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
