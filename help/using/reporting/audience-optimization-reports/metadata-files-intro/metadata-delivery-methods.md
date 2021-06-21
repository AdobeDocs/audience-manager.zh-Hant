---
description: 將中繼資料檔案傳送至您Audience Manager帳戶的特殊Amazon S3目錄，以傳送或更新中繼資料檔案。 如需傳遞/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本區段。
seo-description: 將中繼資料檔案傳送至您Audience Manager帳戶的特殊Amazon S3目錄，以傳送或更新中繼資料檔案。 如需傳遞/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本區段。
seo-title: 中繼資料檔案的傳送方法
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: 記錄檔
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

將元資料檔案發送到您Audience Manager帳戶的特殊[!DNL Amazon S3]目錄，以發送或更新元資料檔案。 如需傳遞/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本區段。

>[!IMPORTANT]
>
> 請連絡您的Audience Manager顧問或客戶服務，以開始使用並設定中繼資料檔案的[!DNL Amazon S3]目錄。

## 傳遞路徑語法與範例 {#syntax}

資料儲存在[!DNL Amazon S3]目錄中每個客戶的獨立命名空間中。 檔案路徑遵循下列語法。 注意，角括弧`<>`表示變數佔位符。 其他元素為常數，不會變更。

**語法:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**範例:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定義檔案傳送路徑中的每個元素。


| 檔案參數 | 說明 |
|---------|----------|
| `.../log_ingestion/` | 這是目錄儲存路徑的開始。 設定完畢後，您會收到完整路徑。 |
| `pid=<AAM ID>` | 此機碼值組包含您的Audience Manager客戶ID。 |
| `dpid=<d_src>` | 此機碼值組包含在事件呼叫中傳入的資料來源ID。 資料來源ID是將檔案中的所有內容與其所屬的實際資料系結的值。 </br> 例如，假設您的創意內容ID為123，名稱為「廣告商創意A」。 由於事件呼叫只會傳入ID，因此您必須在中繼資料檔案中加入「廣告商創意A」。促銷活動和創意屬於資料來源。 資料來源ID是將這些連結在一起的原因，可讓我們將檔案內容準確關聯至在事件呼叫時傳入的ID。 請參閱[事件呼叫ID如何決定檔案名稱、內容和傳送路徑](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 這是檔案名。 請參閱[中繼資料檔案的命名慣例](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 檔案處理時間和更新{#processing-times}

中繼資料檔案每天會處理四次，定期間。

若要更新中繼資料記錄，只需傳送包含新資訊的檔案即可。 您不需要每次都傳送完整更新。
