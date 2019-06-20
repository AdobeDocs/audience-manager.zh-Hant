---
description: DCS API程式碼、方法和程序的概念資訊、說明和定義。
seo-description: Adobe Audience Manager(AAM)中DCS API程式碼、方法和程序的概念資訊、說明和定義。
seo-title: Adobe Audience Manager(AAM)中的DCS API參考概觀
title: DCS API參考概觀
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# DCS API參考概觀

DCS API程式碼、方法和程序的概念資訊、說明和定義。

* [DCS API方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法將資料傳送至DCS API。

* [DCS 錯誤碼、訊息和範例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   由資料收集伺服器(DCS)產生的錯誤碼和訊息，依程式碼ID列出。

* [ID監控與黑名單](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   DCS會監控收到並列入黑名單的ID，這些ID會在短時間內以異常高的速率傳送。

* [DCS地區ID、位置和主機名稱](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   必須有區域DCS伺服器主機名稱才能呼叫DCS。這是因為DCS儲存了地理位置接近網站訪客的資料中心資訊。如果您將查詢傳送至錯誤的DCS，查詢將會運作，但這些呼叫效率不彰，並可能延遲回應。若要提出DCS請求，請比對地區ID至其對應的地區主機名稱，並以適當的主機名稱形式填寫查詢。

* [在DCS呼叫中格式化索引鍵值配對](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   在進行呼叫時，DCS會接受標準或序列化格式的機碼值資料。請參閱本節以瞭解如何格式化標準和序列化關鍵值資料的相關資訊。

* [比賽條件和錯誤處理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   說明如何防止種族條件和DCS錯誤處理。

* [DCS API呼叫的支援屬性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出語法和支援的屬性(或關鍵值配對)，您可以傳入資料收集伺服器(DCS)。此資訊可協助您格式化DCS請求，並瞭解此系統傳回的參數。
