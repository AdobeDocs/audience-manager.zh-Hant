---
description: 傳輸控制(.info)檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴可以驗證Audience Manager處理的檔案傳輸是否正確。
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
ht-degree: 5%

---

# 用於記錄檔傳輸的傳輸控制檔案 {#transfer-control-files-for-log-file-transfers}

轉移控制([!DNL .info])檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴能夠驗證Audience Manager處理的檔案傳輸是否正確。

[!DNL Audience Manager] 每次檔案傳輸時都會向合作夥伴發送轉移控制檔案。 由於多線程性質 [!DNL FTP] publisher ，可能會在實際檔案傳輸完成之前發送傳輸控制檔案。

中的元資料 [!DNL .info] 檔案允許合作夥伴：

* 確定完成完整傳輸週期的時間（序列中已傳送的檔案總數）;
* 確定序列中的任何給定檔案是否完整/正確(通過檢查檔案的大小（以位元組為單位）和行總數；
* 驗證原始檔案中的行數與在檔案載入到接收端資料庫後的行數（檔案大小以行為單位）。

## 檔案命名約定 {#file-naming-conventions}

轉移控制檔案與批/序列的根具有相同的名稱， [!DNL .info] 檔案副檔名

例如，如果序列中的第一個檔案被命名為： [!DNL ftp_12345_67890_full_1500727351632-1.sync]，將命名控制項檔案 [!DNL ftp_12345_67890_iter_1500727351632.info]。

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
> 批總編號不包括 [!DNL .info] 檔案本身。 即，總數不包括 [!DNL .info] 檔案、其位元組大小或其行計數。
>
> 檔案的位元組大小和行計數包括任何標題和間隔（空白）行/行。 要獲取實際資料行/行的計數，請減去標題。
>
> 批中的行總數和位元組總大小包括任何標題行和空格行。
