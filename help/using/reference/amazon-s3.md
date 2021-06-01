---
description: Amazon Simple Storage Service(Amazon S3)的相關資訊。
seo-description: Amazon Simple Storage Service(Amazon S3)的相關資訊。
seo-title: Amazon S3關於
solution: Audience Manager
title: Amazon S3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 參考
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3：關於{#amazon-s-about}

Amazon Simple Storage Service(Amazon S3)的相關資訊。

建議您使用Amazon S3而非FTP，作為從合作夥伴取得檔案並傳送檔案的方法，這才是最佳作法。 Amazon S3提供簡單的Web服務介面，可供您隨時從Web上的任何位置儲存及擷取任何數量的資料。

使用Amazon S3的好處包括：

* **可擴充性：** Amazon S3提供幾乎無限的擴充性。
* **可靠性和可用性：** Amazon S3提供高耐用性和高可用性儲存服務。
* **速度：** Amazon S3允許快速資料傳輸。
* **易於使用：** Amazon S3易於使用且易於實作。您的實作可在約一小時內啟動並執行。 實作FTP目錄需要的時間要長得多。
* **多部分上傳：** 大型檔案可以像多部分檔案上傳一樣快速且有效地上傳。
* **安全性：** Amazon S3提供強大的安全性。

   * 所有目錄只能由適當的客戶或客戶端訪問。
   * 上傳和下載支援HTTPS通訊協定。 在[!DNL Audience Manager]中傳輸檔案時，應始終使用HTTPS。
   * Amazon S3提供重新加密，用於加密[傳出資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我們使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，該方法允許由Amazon S3自動生成和管理加密密鑰。

* **除錯和備份支援：** Amazon S3可 [!DNL Audience Manager] 保留檔案的確切副本，以便更輕鬆進行除錯或重新傳輸。

如需Amazon S3的詳細資訊，請參閱下列資源：

[Amazon簡單儲存服務(Amazon S3)](https://aws.amazon.com/s3/) (位於Amazon網站服務網站)。

[在AWS文檔網站上](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 開始使用Amazon Simple Storage Service。
