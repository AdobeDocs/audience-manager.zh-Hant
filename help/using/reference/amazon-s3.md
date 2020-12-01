---
description: 有關Amazon Simple Storage Service(Amazon S3)的資訊。
seo-description: 有關Amazon Simple Storage Service(Amazon S3)的資訊。
seo-title: Amazon S3關於
solution: Audience Manager
title: Amazon S3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 1%

---


# Amazon S3：關於{#amazon-s-about}

有關Amazon Simple Storage Service(Amazon S3)的資訊。

作為最佳實務，我們建議使用Amazon S3而非FTP來從合作夥伴取得檔案並傳送檔案。 Amazon S3提供簡單的web services介面，可用於隨時隨地從Web上儲存和擷取任何數量的資料。

使用Amazon S3的優點包括：

* **可擴充性：** Amazon S3提供幾乎無限的擴充能力。
* **可靠性和可用性：** Amazon S3提供高耐久性和高可用性儲存服務。
* **速度：** Amazon S3允許快速的資料傳輸。
* **易於使用：** Amazon S3非常易於使用和實施。您的實作可在約一小時內啟動及執行。 實作FTP目錄需要更長的時間。
* **多部分上傳：大型** 檔案可以像多部分檔案上傳一樣快速且有效率地上傳。
* **安全性：** Amazon S3提供強大的安全性。

   * 所有目錄都只能由適當的客戶或客戶訪問。
   * HTTPS通訊協定支援上傳和下載。 在[!DNL Audience Manager]中傳輸檔案時，請一律使用HTTPS。
   * Amazon S3提供靜態加密，用於加密[出站資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我們使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，該方法允許Amazon S3自動生成和管理加密密鑰。

* **除錯和備份支援：** Amazon S3可 [!DNL Audience Manager] 保留檔案的精確副本，讓除錯或重新傳輸更輕鬆。

如需Amazon S3的詳細資訊，請參閱下列資源：

[Amazon Web Services網站上的Amazon Simple Storage Service(Amazon S3)。](https://aws.amazon.com/s3/) 

[從AWS文檔網站開始](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 使用Amazon Simple Storage Service。
