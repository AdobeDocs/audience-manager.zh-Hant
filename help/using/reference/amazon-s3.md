---
description: 有關Amazon簡單儲存服務(AmazonS3)的資訊。
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: AmazonS3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 1%

---

# Amazon S3：關於{#amazon-s-about}

有關Amazon簡單儲存服務(AmazonS3)的資訊。

作為最佳做法，我們建議將AmazonS3而不是FTP用作從合作夥伴處獲取檔案並將檔案傳送到合作夥伴的方法。 AmazonS3提供一個簡單的Web服務介面，可用於隨時隨地從Web上的任何位置儲存和檢索任何數量的資料。

使用AmazonS3的好處包括：

* **可擴充性：** AmazonS3提供了幾乎無限的可擴充性。
* **可靠性和可用性：** AmazonS3提供高耐用性和高可用性儲存服務。
* **速度：** AmazonS3允許快速資料傳輸。
* **易用性：** AmazonS3非常易於使用和實施。 您的實施可在大約一小時內啟動並運行。 實現FTP目錄需要更長的時間。
* **多部件上載：** 大檔案可以作為多部件檔案上載而快速高效地上載。
* **安全性：** AmazonS3提供強大的安全。

   * 所有目錄只能由相應的客戶或客戶端訪問。
   * HTTPS協定支援上載和下載。 在中傳輸檔案時應始終使用HTTPS [!DNL Audience Manager]。
   * AmazonS3提供靜態加密，用於加密 [出站資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我們使用 [南蘇鐵S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 加密方法，使加密密鑰由AmazonS3自動生成和管理。

* **調試和備份支援：** AmazonS3允許 [!DNL Audience Manager] 以保留檔案的精確副本，使調試或重新傳輸更容易。

有關AmazonS3的詳細資訊，請參閱以下資源：

[Amazon簡單儲存服務(AmazonS3)](https://aws.amazon.com/s3/) 在Amazon Web Services網站上。

[開始使用Amazon簡單儲存服務](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 在AWS文檔網站上。
