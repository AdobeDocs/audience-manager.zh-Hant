---
description: 傳輸控制(.info)檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴能夠驗證Audience Manager已正確處理的檔案傳輸。
seo-description: 傳輸控制(.info)檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴能夠驗證Audience Manager已正確處理的檔案傳輸。
seo-title: 用於記錄檔傳輸的傳輸控制檔案
solution: Audience Manager
title: 用於記錄檔傳輸的傳輸控制檔案
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: 傳出資料傳輸
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 6%

---

# 用於記錄檔傳輸的傳輸控制檔案 {#transfer-control-files-for-log-file-transfers}

傳輸控制([!DNL .info])檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴能夠驗證Audience Manager已正確處理的檔案傳輸。

[!DNL Audience Manager] 會透過每次檔案傳輸將傳輸控制檔案傳送給合作夥伴。由於[!DNL FTP]發佈器的多線程性質，在實際檔案完成傳輸之前可能會發送傳輸控制檔案。

[!DNL .info]檔案中的中繼資料可讓合作夥伴：

* 確定完整傳輸週期何時完成（已傳送序列中的檔案總數）;
* 確定序列中的任何給定檔案是否完整/正確(通過檢查檔案的大小（以位元組為單位）和行的總數；
* 驗證原始檔案中的行數與接收端資料庫中載入檔案後的行數（行中的檔案大小）。

## 檔案命名約定{#file-naming-conventions}

傳輸控制檔案與批次/序列的根檔案具有相同的名稱，副檔名為[!DNL .info]。s

例如，如果序列中的第一個檔案名為：[!DNL ftp_12345_67890_full_1500727351632-1.sync]，控制檔案的名稱為[!DNL ftp_12345_67890_iter_1500727351632.info]。

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
> 批總數不包括[!DNL .info]檔案本身。 也就是說，總計不包含[!DNL .info]檔案、其位元組大小或其行數。
>
> 檔案和行計數的位元組大小包含任何標題和間隔符（空白）行/行。 若要取得實際資料行/列的計數，請減去標題。
>
> 批中的行總數和位元組大小總計包含任何標題行和空格行。
