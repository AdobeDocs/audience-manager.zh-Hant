---
description: 傳送或更新中繼資料檔案至您Audience Manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-description: 傳送或更新中繼資料檔案至您Audience Manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-title: 中繼資料檔案的傳送方法
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

傳送或更新中繼資料檔案至您Audience Manager帳戶 [!DNL Amazon S3] 的特殊目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

>[!IMPORTANT]
>
> 請連絡您的Audience Manager顧問或客戶服務，以開始並設定中繼資 [!DNL Amazon S3] 料檔案的目錄。

## 傳送路徑語法與範例 {#syntax}

資料會儲存在目錄中每位客戶的個別命名空 [!DNL Amazon S3] 間中。 檔案路徑遵循下列語法。 注意，尖括弧 `<>` 表示變數預留位置。 其他元素是常數，不會變更。

**語法:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**範例:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定義了檔案傳送路徑中的每個元素。


| 檔案參數 | 說明 |
---------|----------|
| `.../log_ingestion/` | 這是目錄儲存路徑的開始。 一切就緒後，您將獲得完整的路徑。 |
| `pid=<AAM ID>` | 此金鑰值配對包含您的Audience Manager客戶ID。 |
| `dpid=<d_src>` | 此金鑰值配對包含在事件呼叫中傳入的資料來源ID。 資料來源ID是將檔案中所有內容與其所屬實際資料系結的值。 </br> 例如，假設您有ID為123的創意素材，且名稱為「廣告商創意A」。 當事件呼叫只傳遞在ID中時，您必須在中繼資料檔案中包含「廣告商創意A」。 促銷活動和創意素材屬於資料來源。 資料來源ID是這些連結的原因，可讓我們將檔案內容精確關聯至事件呼叫時傳送的ID。 請參 [閱事件呼叫ID如何決定檔案名稱、內容和傳送路徑](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 這是檔案名。 請參 [閱中繼資料檔案的命名慣例](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 檔案處理時間與更新 {#processing-times}

中繼資料檔案每天處理四次，每隔一定時間。

若要更新中繼資料記錄，請傳送包含新資訊的檔案。 您不需要每次都傳送完整更新。
