---
description: 客戶資料摘要 (CDF) 檔案的常見問題集。
seo-description: 客戶資料摘要 (CDF) 檔案的常見問題集。
seo-title: 客戶資料摘要常見問題集
solution: Audience Manager
title: 客戶資料摘要常見問題集
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 100%

---


# 客戶資料摘要常見問題集{#customer-data-feed-faq}

客戶資料摘要 (CDF) 檔案的常見問題集。

## Amazon S3 儲存空間 {#amazon-s3-storage}

**我的 CDF 檔案儲存在[!DNL Amazon]上的何處？**

您的 CDF 檔案儲存在 [!DNL Amazon S3] 伺服器的 `aam-cdf` 根目錄中。此預設貯體由管理 [!DNL Audience Manager]。另請參閱[客戶資料摘要檔案命名慣例](../features/cdf-files.md#cdf-naming-conventions)。

<br> 

**我的貯體是否安全？**

是。客戶只能存取自己的儲存空間。您會擁有儲存貯體的唯讀存取權。您不會有寫入存取權。

<br> 

**我可以自訂儲存貯體或將檔案儲存在其他目錄中嗎？**

不會。不提供自訂和替代儲存空間選項。

<br> 

**我的目錄中缺少了某個鐘頭的檔案。這些檔案在哪裡？**

缺少檔案表示那個鐘頭 [!DNL Audience Manager] 無法處理 CDF 檔案。這通常發生在我們的伺服器在處理 CDF 檔案方面有所落後時。在這種情況下，您的檔案並不會遺失。我們的系統有機會趕上進度後，檔案會出現在之後的每小時目錄中。另請參閱[客戶資料摘要檔案處理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

**如何知道 CDF 檔案何時準備就緒？**

請參閱[客戶資料摘要檔案處理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

## 檔案大小 {#file-sizes}

**預期的檔案大小有多大？CDF 檔案的平均大小為何？**

檔案大小很難預估，而且每個檔案的大小都不盡相同。每小時和每天的檔案大小都不同。如果您要接收 CDF 檔案，請做好管理大量資料的準備，這樣會有所幫助。

<br> 

**我會收到多少檔案？**

同樣地，這也很難預估。但是如果您要接收 CDF 檔案，請做好管理大量資料的準備，這樣會有所幫助。

<br> 

## 資料完整性 {#data-integrity}

**如何檢查上傳至 Amazon S3 的資料的完整性？**

[!DNL Amazon] 會將大型檔案分割成較小的片段，然後使用多部分上傳功能將其上傳至 [!DNL Amazon S3]。接著會針對多部分上傳產生一個 `ETag` 值。首先系統會計算每個已上傳部分的個別 MD5 檢查加總，然後將它們串連到單個字串中，接著再計算該字串的 MD5 檢查加總。再來會用連字號附加產生的檢查加總 (`ETag`)，以及用於上傳的片段總數。例如，在上傳期間分割為 5 個片段的檔案之 `ETag` 可能如下所示：`2c51427d19021e88cf3395365895b6d4-5`

<br> 

## 資料保留 {#data-retension}

**你們會將 CDF 檔案儲存多久時間？**

資料會在八 (8) 天後刪除。

<br> 

**我是否可以回溯取得過去或幾天前的 CDF 檔案？**

您只能產生過去 8 天的 CDF 檔案。不能重新產生間隔 8 天以上的 CDF 檔案。

>[!MORELIKETHIS]
>
>* [客戶資料摘要](../features/cdf-files.md)

