---
description: 說明如何防止競賽條件和DCS錯誤處理。
seo-description: 說明如何防止競賽條件和DCS錯誤處理。
seo-title: 競爭條件與錯誤處理
solution: Audience Manager
title: 競爭條件與錯誤處理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# 競爭條件與錯誤處理 {#race-conditions-and-error-handling}

說明如何防止競賽條件和錯 [!DNL DCS] 誤處理。

## 防止種族狀況 {#prevent-race-conditions}

如果您在回應初始查詢並將資料寫入使用者的Cookie之前，同時（或快速連續）傳送多個呼叫 [!DNL DCS] 至，就會發生競爭條件。 不需要競爭條件，因為它可能會損毀或不當覆寫Cookie資料。 為避免此問題，請考慮下列方法：

* 不要同時呼叫，或快速接續呼叫同一 [!DNL DCS] 位使用者。
* 等待每個回應返回，再進行後續呼叫。

## 錯誤處理 {#error-handling}

錯誤處理僅限於無效或格式錯誤的查詢。 無效的請求會傳回回 `HTTP 200 OK` 回應，而無資料。 此外，當使 [!DNL DCS] 用者符合下列條件時，這些應用程式會停止處理請求、捨棄特徵資 `HTTP 200 OK` 料並傳回回應：

* 在Audience Manager或合作夥伴層級退出追蹤。
* 來自無效／未選取的地理區域。
* 停用瀏覽器Cookie（全部或協力廠商）。

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).