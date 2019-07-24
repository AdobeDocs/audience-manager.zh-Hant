---
description: 說明如何防止種族條件和DCS錯誤處理。
seo-description: 說明如何防止種族條件和DCS錯誤處理。
seo-title: 比賽條件和錯誤處理
solution: Audience Manager
title: 比賽條件和錯誤處理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. 競爭條件不受歡迎，因為它可能會損毀或不當覆寫Cookie資料。作為最佳實務，請考慮下列方法以避免此問題：

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* 等候每個回應在後續呼叫之前回來。

## Error Handling {#error-handling}

錯誤處理受到無效或格式化查詢的限制。An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* 退出Audience Manager或合作夥伴層級追蹤。
* 來自無效/未選取的地理區域。
* 停用瀏覽器Cookie(全部或第三方)。

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).