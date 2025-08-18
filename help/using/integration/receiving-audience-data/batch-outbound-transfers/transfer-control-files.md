---
description: 傳輸控制(.info)檔案會提供有關檔案傳輸的中繼資料資訊，讓合作夥伴能夠驗證Audience Manager是否正確處理檔案傳輸。
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: 用於記錄檔傳輸的傳輸控制檔案
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 用於記錄檔傳輸的傳輸控制檔案 {#transfer-control-files-for-log-file-transfers}

傳輸控制([!DNL .info])檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可以確認Audience Manager已正確處理檔案傳輸。

[!DNL Audience Manager]會傳送傳輸控制檔案給合作夥伴，每次進行檔案傳輸。 由於[!DNL FTP]發行者的多執行緒性質，傳輸控制檔案可能會在實際檔案完成傳輸之前傳送。

[!DNL .info]檔案中的中繼資料可讓合作夥伴：

* 決定完整傳輸週期何時完成（已傳送順序中的檔案總數）；
* 判斷序列中的任何指定檔案是否完整/正確(透過檢查檔案大小（以位元組為單位）和總行數)；
* 驗證原始檔案中的列數與檔案在接收端載入資料庫後的列數（檔案大小，以行為單位）相對應。

## 檔案命名慣例 {#file-naming-conventions}

傳輸控制檔的名稱與副檔名為[!DNL .info]的批次/序列的根相同。

例如，如果序列中的第一個檔案名為： [!DNL ftp_12345_67890_full_1500727351632-1.sync]，則控制檔將名為[!DNL ftp_12345_67890_iter_1500727351632.info]。

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

>[!NOTE]
>
> 批次總數不包括[!DNL .info]檔案本身。 也就是說，總計不包含[!DNL .info]檔案、其位元組大小或其行數。
>
> 檔案的位元組大小和行數包含任何標題和分隔符號（空白）行/列。 若要取得實際資料行/列的計數，請減去標題。
>
> 批次中的總計行數和總計位元組大小包含任何標題和空格列。
