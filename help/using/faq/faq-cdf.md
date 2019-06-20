---
description: 關於客戶資料饋送(CMS)檔案的常見問題。
seo-description: 關於客戶資料饋送(CMS)檔案的常見問題。
seo-title: 客戶資料饋送常見問題
solution: Audience Manager
title: 客戶資料饋送常見問題
uuid: 7183b3e-e999-4e1 e-892f-2bab335 c13 b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

關於客戶資料饋送(CMS)檔案的常見問題。

## Amazon S3 Storage {#amazon-s3-storage}

**我的CMS檔案儲存在何處[!DNL Amazon]？**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**我的儲存貯體安全嗎？**

是。客戶只能存取自己的儲存空間。您將擁有儲存貯體的唯讀存取權。您將無法擁有寫入權限。

<br> 

**我可以自訂儲存貯體或將檔案儲存在另一個目錄中嗎？**

不會。不提供自訂和替代儲存選項。

<br> 

**我的目錄遺失特定小時的檔案。Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. 當我們的伺服器處理CMS檔案時，通常會發生這種情況。在此情況下，您的檔案不會遺失。在我們的系統有機會追趕後，它會在稍後的每小時目錄中顯示。See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**我要如何知道我的CMS檔案已準備就緒？**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**我需要何種檔案大小？How big is an average CDF file?**

估計檔案大小很困難。而且，每個檔案都可以是不同的大小。大小會隨著小時和天而有所不同。如果您要收到CMS檔案，可以準備好管理許多資料。

<br> 

**我將收到幾個檔案？**

同樣地，很難估計這點。不過，如果您要收到CMS檔案，可協助準備管理大量資料。

<br> 

## Data Integrity {#data-integrity}

**如何檢查上傳至Amazon S的資料完整性？**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] 產生多部分上傳的 `ETag` 值。它會先計算每個上傳部分的個別MD檢查總和，然後串連到單一字串中。然後，它會計算字串的MD檢查加總。The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**您儲存CMS檔案的時間有多長？**

資料會在(8)天後刪除。

<br> 

**我可以回溯或舊版取得CMS檔案嗎？**

您只能在過去天產生CMS檔案。舊版比過去天更早的CMS檔案無法重新產生。

>[!MORE_贊_ this]
>
>* [客戶資料饋送](../features/cdf-files.md)

