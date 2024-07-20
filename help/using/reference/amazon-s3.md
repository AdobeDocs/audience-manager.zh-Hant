---
description: Amazon Simple Storage Service (Amazon S3)的相關資訊。
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3：關於{#amazon-s-about}

Amazon Simple Storage Service (Amazon S3)的相關資訊。

最佳實務建議使用Amazon S3 （而非FTP）作為從合作夥伴取得檔案並將檔案傳送給合作夥伴的方法。 Amazon S3提供簡單的網站服務介面，可用於儲存及擷取任何數量的資料，且隨時可從網路上的任何位置存取。

使用Amazon S3的好處包括：

* **擴充性：** Amazon S3提供幾乎無限的擴充性。
* **可靠性與可用性：** Amazon S3提供高耐用度與高可用性儲存服務。
* **速度：** Amazon S3允許快速資料傳輸。
* **易用性：** Amazon S3非常容易使用及實作。 您的實作可在約一小時內完成並執行。 實作FTP目錄需花很長的時間。
* **多部分上傳：**&#x200B;大型檔案可以快速有效率地以多部分檔案上傳的方式上傳。
* **安全性：** Amazon S3提供強大的安全性。

   * 只有適當的客戶或使用者端可存取所有目錄。
   * HTTPS通訊協定支援上傳和下載。 在[!DNL Audience Manager]中傳輸檔案時，您應該一律使用HTTPS。
   * Amazon S3提供靜態加密功能，可加密[傳出資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我們使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，可讓Amazon S3自動產生並管理加密金鑰。

* **偵錯和備份支援：** Amazon S3可讓[!DNL Audience Manager]保留檔案的精確復本，以便更輕鬆地進行偵錯或重新傳輸。

如需Amazon S3的詳細資訊，請參閱下列資源：

Amazon Web Services網站上的[Amazon簡單儲存服務(Amazon S3)](https://aws.amazon.com/s3/)。

[開始使用AWS檔案網站上的Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html)。
