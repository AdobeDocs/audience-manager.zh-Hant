---
description: 說明如何防止競賽條件和DCS錯誤處理。
seo-description: 說明如何防止競賽條件和DCS錯誤處理。
seo-title: 競爭條件與錯誤處理
solution: Audience Manager
title: 競爭條件與錯誤處理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# 競爭條件與錯誤處理 {#race-conditions-and-error-handling}

說明如何防止競賽條件和[!DNL DCS]錯誤處理。

## 防止種族條件{#prevent-race-conditions}

如果您在[!DNL DCS]完成對初始查詢的回應並將資料寫入使用者的Cookie之前，同時（或快速連續）傳送多個呼叫至&lt;a0/>，就會發生競爭條件。 不需要競爭條件，因為它可能會損毀或不當覆寫Cookie資料。 為避免此問題，請考慮下列方法：

* 不要同時呼叫同一用戶的[!DNL DCS]，或快速連續呼叫。
* 等待每個回應返回，再進行後續呼叫。

## 處理{#error-handling}錯誤

錯誤處理僅限於無效或格式錯誤的查詢。 無效的請求會傳回`HTTP 200 OK`回應，而且沒有資料。 此外，當使用者：[!DNL DCS]`HTTP 200 OK`

* 在Audience Manager或合作夥伴層級退出追蹤。
* 來自無效／未選取的地理區域。
* 停用瀏覽器Cookie（全部或協力廠商）。

另請參閱[DCS錯誤代碼、消息和示例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。