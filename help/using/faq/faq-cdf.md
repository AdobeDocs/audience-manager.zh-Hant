---
description: 客戶資料饋送(CDF)檔案的常見問題。
seo-description: 客戶資料饋送(CDF)檔案的常見問題。
seo-title: 客戶資料饋送常見問答集
solution: Audience Manager
title: 客戶資料饋送常見問答集
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# 客戶資料饋送常見問答集{#customer-data-feed-faq}

客戶資料饋送(CDF)檔案的常見問題。

## Amazon S3儲存空間 {#amazon-s3-storage}

**我的CDF檔案儲存在何處[!DNL Amazon]?**

您的CDF檔案儲存在服 `aam-cdf` 務器的根目錄 [!DNL Amazon S3] 中。 此預設貯體由管理 [!DNL Audience Manager]。 另請參閱 [客戶資料饋送檔案命名慣例](../features/cdf-files.md#cdf-naming-conventions)。

<br> 

**我的儲存桶是否安全？**

是。客戶只能訪問自己的儲存空間。 您將擁有對儲存桶的唯讀訪問權限。 您將沒有寫訪問權限。

<br> 

**我可以自訂儲存貯體或將檔案儲存在其他目錄中嗎？**

不會。無法使用自訂和替代儲存選項。

<br> 

**我的目錄在特定小時內缺少檔案。 在哪？**

缺少檔案表 [!DNL Audience Manager] 示該小時無法處理CDF檔案。 這通常發生在我們的伺服器在處理CDF檔案時落後時。 在這種情況下，您的檔案不會遺失。 在我們的系統有機會追趕之後，它會出現在稍後的每小時目錄中。 另請參閱「客 [戶資料饋送檔案處理通知」](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

**如何知道CDF檔案何時準備就緒？**

請參閱 [客戶資料饋送檔案處理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

## 檔案大小 {#file-sizes}

**我應該期待何種檔案大小？ 平均CDF檔案大小為多大？**

很難估計檔案大小。 而且，每個檔案的大小可以不同。 大小依小時和日而異。 如果您要接收CDF檔案，則做好管理大量資料的準備會有所幫助。

<br> 

**我會收到多少個檔案？**

同樣，很難估計這一點。 但是，如果您要接收CDF檔案，則有助於準備管理大量資料。

<br> 

## 資料完整性 {#data-integrity}

**如何檢查上傳至Amazon S3的資料的完整性？**

[!DNL Amazon] 將大型檔案分割成較小的部分，然後使用多 [!DNL Amazon S3] 部分上傳來上傳檔案。 然後，它會為多 `ETag` 部件上傳產生一個值。 它會先計算每個已上載部分的個別MD5校驗和，然後將它們串連到單個字串中。 然後，計算字串的MD5校驗和。 然後，產生的校驗和( `ETag`)會附加一個連字型大小，以及用於上載的部件總數。 例如，在上 `ETag` 傳期間分割為5個部分的檔案可能如下所示： `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**您儲存CDF檔案的時間有多長？**

資料會在八(8)天后刪除。

<br> 

**我是否可以追溯取得CDF檔案，或是前幾天？**

您只能生成過去8天的CDF檔案。 不能重新生成過去8天以前間隔的CDF檔案。

>[!MORELIKETHIS]
>
>* [客戶資料饋送](../features/cdf-files.md)

