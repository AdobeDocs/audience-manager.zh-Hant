---
description: 通過將元資料檔案發送到您的Audience Manager帳戶的特殊AmazonS3目錄來發送或更新它們。 有關傳遞/目錄路徑、檔案處理時間和更新的資訊，請參閱本節。
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 3%

---

# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

通過將元資料檔案發送到特殊檔案來發送或更新它們 [!DNL Amazon S3] Audience Manager帳戶的目錄。 有關傳遞/目錄路徑、檔案處理時間和更新的資訊，請參閱本節。

>[!IMPORTANT]
>
> 與Audience Manager顧問或客戶服務人員聯繫以開始並設定 [!DNL Amazon S3] 元資料檔案的目錄。

## 傳遞路徑語法和示例 {#syntax}

資料儲存在一個 [!DNL Amazon S3] 的子菜單。 檔案路徑遵循下面所示的語法。 注意，尖括弧 `<>` 指示變數佔位符。 其它元素是常數，不更改。

**語法:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**範例:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定義了檔案傳遞路徑中的每個元素。


| 檔案參數 | 說明 |
|---------|----------|
| `.../log_ingestion/` | 這是目錄儲存路徑的開始。 設定完全時，您將收到完整路徑。 |
| `pid=<AAM ID>` | 此鍵值對包含您的Audience Manager客戶ID。 |
| `dpid=<d_src>` | 此鍵值對包含在事件調用中傳遞的資料源ID。 資料源ID是將檔案中的所有內容與其所屬的實際資料聯繫起來的值。 </br> 例如，假設您有一個ID為123且名為「廣告商創意A」的創意。 由於事件呼叫僅在ID中傳遞，因此您需要在元資料檔案中包括「廣告商Creative A」。 活動和創意屬於資料源。 資料源ID是將這些內容關聯在一起的，它讓我們能夠準確地將檔案內容與事件調用中發送的ID關聯起來。 請參閱 [事件調用ID如何確定檔案名、內容和傳遞路徑](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 這是檔案名。 請參閱 [元資料檔案的命名約定](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 檔案處理時間和更新 {#processing-times}

每天處理四次元資料檔案，間隔不定。

要更新元資料記錄，只需發送包含新資訊的檔案即可。 您無需每次發送完整更新。
