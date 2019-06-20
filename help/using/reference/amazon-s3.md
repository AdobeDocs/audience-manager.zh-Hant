---
description: Amazon Simple Storage Service(Amazon S3)的相關資訊。
seo-description: Amazon Simple Storage Service(Amazon S3)的相關資訊。
seo-title: Amazon S3關於
solution: Audience Manager
title: Amazon S3關於
uuid: 8192ecdf-df8 f-488d-back0-d8 d4205 b42 b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Amazon Simple Storage Service(Amazon S3)的相關資訊。

建議您使用Amazon S而非FTP做為取得檔案的方式，並將檔案傳送給合作夥伴。Amazon S提供簡單的web services介面，可用來隨時隨地儲存和擷取任何數量的資料。

使用Amazon S的優點包括：

* **調整彈性：** Amazon S提供近乎無障礙的調整能力。
* **可靠性與可用性：** Amazon S提供高耐久性和高可用性儲存服務。
* **速度：** Amazon S可讓您快速傳輸資料。
* **易於使用：** Amazon S非常容易使用和實施。您的實作約需一小時即可開始執行。實作FTP目錄需要較長的時間。
* **多部分上傳：** 可快速且有效率地上傳大型檔案做為多部分檔案上傳。
* **安全性：** Amazon S提供強大的安全性。

   * 所有目錄僅供適當客戶或客戶存取。
   * HTTPS通訊協定支援上傳和下載。You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **除錯與備份支援：** Amazon [!DNL Audience Manager] S可讓您保留正確的檔案復本，以進行除錯或重新傳輸。

如需Amazon S的詳細資訊，請參閱下列資源：

[Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) on Amazon Web Services網站。

[AWS文件網站上的Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 快速入門。
