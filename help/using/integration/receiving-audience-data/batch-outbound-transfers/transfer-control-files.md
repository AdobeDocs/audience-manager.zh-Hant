---
description: 傳輸控制(.info)檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可驗證Audience Manager是否正確地處理檔案傳輸。
seo-description: 傳輸控制(.info)檔案提供檔案傳輸的中繼資料資訊，讓合作夥伴可驗證Audience Manager是否正確地處理檔案傳輸。
seo-title: 傳輸控制檔案檔案檔案傳輸
solution: Audience Manager
title: 傳輸控制檔案檔案檔案傳輸
uuid: ef58213e-7b37-4c5a-8556-0de695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] 傳送移轉控制檔案給合作夥伴，並傳送檔案給合作夥伴。Due to the multi-thread nature of the [!DNL FTP] publisher, the transfer-control file might be sent before the actual files are finished transferring.

[!DNL .info] 檔案中的中繼資料可讓合作夥伴：

* 判斷完整傳輸週期何時完成(序列中的檔案總份數)；
* 判斷序列中的任何指定檔案是否完整/正確(透過檢查檔案大小和線條總數)；
* 驗證原始檔案中的列數，會在檔案載入至接收結束(以行大小的檔案大小)後，記錄列數。

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

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
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> 檔案的位元組大小和行數皆包含任何標題和間距(空白)線條/列。若要取得實際資料行/列的計數，請減去標題。
>
> 批次總計和位元組大小總計包含任何標題和空間列。