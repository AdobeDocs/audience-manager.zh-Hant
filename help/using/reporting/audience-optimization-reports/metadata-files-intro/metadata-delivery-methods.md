---
description: 將中繼資料檔案傳送至您Audience Manager帳戶的特殊Amazon S3目錄，以傳送或更新中繼資料檔案。 請參閱本節以瞭解有關傳送/目錄路徑、檔案處理時間和更新的資訊。
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

將中繼資料檔案傳送至您Audience Manager帳戶的特殊[!DNL Amazon S3]目錄，以傳送或更新中繼資料檔案。 請參閱本節以瞭解有關傳送/目錄路徑、檔案處理時間和更新的資訊。

>[!IMPORTANT]
>
> 請連絡您的Audience Manager顧問或客戶服務，以開始使用並為中繼資料檔案設定[!DNL Amazon S3]目錄。

## 傳遞路徑語法和範例 {#syntax}

資料會儲存在[!DNL Amazon S3]目錄中每個客戶的個別名稱空間中。 檔案路徑會遵循下列語法。 請注意，尖括弧`<>`表示變數預留位置。 其他元素則是常數，不會變更。

**語法:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**範例:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定義檔案傳送路徑中的各個元素。


| 檔案引數 | 說明 |
|---------|----------|
| `.../log_ingestion/` | 這是目錄儲存路徑的開頭。 一切設定完成後，您將會收到完整路徑。 |
| `pid=<AAM ID>` | 此機碼值組包含您的Audience Manager客戶ID。 |
| `dpid=<d_src>` | 此機碼值組包含傳入事件呼叫的資料來源ID。 資料來源ID是將檔案中的所有內容與其所屬的實際資料繫結的值。 </br>例如，假設您有ID 123且名稱為「Advertiser Creative A」的創意產品。 由於事件呼叫只會在ID中傳遞，因此您必須在中繼資料檔案中包含「廣告商Creative A」。 行銷活動和創意屬於資料來源。 資料來源ID可將這些連結在一起，並可讓我們將檔案內容準確地與事件呼叫時傳入的ID建立關聯。 請參閱[事件呼叫ID如何決定檔案名稱、內容和傳遞路徑](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 這是檔案名稱。 請參閱[中繼資料檔案的命名慣例](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 檔案處理時間和更新 {#processing-times}

中繼資料檔案會定期每日處理四次。

若要更新中繼資料記錄，只需傳送包含新資訊的檔案即可。 您不需要每次都傳送完整更新。
