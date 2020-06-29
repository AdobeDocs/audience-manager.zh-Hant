---
description: 傳輸控制(.info)檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可以確認Audience Manager已正確處理檔案傳輸。
seo-description: 傳輸控制(.info)檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可以確認Audience Manager已正確處理檔案傳輸。
seo-title: 用於記錄檔傳輸的傳輸控制檔案
solution: Audience Manager
title: 用於記錄檔傳輸的傳輸控制檔案
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 6%

---


# 用於記錄檔傳輸的傳輸控制檔案 {#transfer-control-files-for-log-file-transfers}

傳輸控制([!DNL .info])檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可以確認Audience Manager已正確處理檔案傳輸。

[!DNL Audience Manager] 每次檔案傳輸時都會向合作夥伴發送轉移控制檔案。 由於發佈者的多執行緒性質，在 [!DNL FTP] 實際傳輸檔案完成之前，可能會傳送傳輸控制檔案。

檔案中的中繼資料 [!DNL .info] 可讓合作夥伴：

* 確定完整傳輸週期何時完成（序列中已傳送的檔案總數）;
* 確定序列中的任何給定檔案是否完整／正確(通過檢查檔案的大小（以位元組為單位）和行總數；
* 驗證原始檔案中的列數與接收端資料庫中載入檔案後的列數（以行為單位的檔案大小）。

## 檔案命名慣例 {#file-naming-conventions}

轉移控制檔案與批次／序列的根檔案具有相同的名稱，並 [!DNL .info] 具有檔案副檔名。

例如，如果序列中的第一個檔案是命名的： [!DNL ftp_12345_67890_full_1500727351632-1.sync]，則會命名控制檔 [!DNL ftp_12345_67890_iter_1500727351632.info]。

## 檔案格式 {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[注意]
>
> 批總數不包括檔案 [!DNL .info] 本身。 也就是說，總計不包括檔 [!DNL .info] 案、其位元組大小或行數。
>
> 檔案的位元組大小和行數包含任何標題和間隔符（空白）行／行。 為了取得實際資料行／列的計數，請減去標題。
>
> 批次行總數和位元組大小總計包含任何標題行和空格行。