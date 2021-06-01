---
description: 說明如何防止競爭條件和DCS錯誤處理。
seo-description: 說明如何防止競爭條件和DCS錯誤處理。
seo-title: 競爭條件與錯誤處理
solution: Audience Manager
title: 競爭條件與錯誤處理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# 競爭條件與錯誤處理 {#race-conditions-and-error-handling}

說明如何防止競爭條件和[!DNL DCS]錯誤處理。

## 防止競爭條件{#prevent-race-conditions}

如果您在[!DNL DCS]完成對初始查詢的回應並將資料寫入使用者的Cookie之前，同時（或快速連續）傳送多個呼叫，則可能會發生競爭條件。 競爭條件不是您預期的，因為可能會損毀或不正確覆寫Cookie資料。 為避免此問題，請考量下列方法：

* 請勿從同一位使用者同時呼叫或快速連續呼叫[!DNL DCS]。
* 等待每個回應返回，再進行後續呼叫。

## 錯誤處理{#error-handling}

錯誤處理僅限於無效或格式不良的查詢。 無效的請求返回`HTTP 200 OK`響應，但沒有資料。 此外，當使用者符合下列條件時，[!DNL DCS]會停止處理請求、捨棄特徵資料並傳回`HTTP 200 OK`回應：

* 選擇不在Audience Manager或合作夥伴層級進行追蹤。
* 來自無效/未選取的地理區域。
* 停用瀏覽器Cookie（全部或第三方）。

另請參閱[DCS錯誤碼、訊息和範例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。
