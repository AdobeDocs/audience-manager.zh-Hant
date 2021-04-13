---
description: 有關Amazon簡單儲存服務(AmazonS3)的資訊。
seo-description: 有關Amazon簡單儲存服務(AmazonS3)的資訊。
seo-title: AmazonS3關於
solution: Audience Manager
title: AmazonS3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 參考
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3：關於{#amazon-s-about}

有關Amazon簡單儲存服務(AmazonS3)的資訊。

建議您最好使用AmazonS3來取代FTP，以從合作夥伴取得檔案並傳送檔案。 AmazonS3提供簡單的web services介面，可用來隨時隨地儲存和擷取任何數量的資料。

使用AmazonS3的好處包括：

* **可擴充性：** AmazonS3提供幾乎無限的擴充性。
* **可靠性和可用性：** AmazonS3提供高耐久性和高可用性儲存服務。
* **速度：** AmazonS3允許快速的資料傳輸。
* **易於使用：** AmazonS3易於使用和實施。您的實作可在約一小時內啟動及執行。 實作FTP目錄需要更長的時間。
* **多部分上傳：大型** 檔案可以像多部分檔案上傳一樣快速且有效率地上傳。
* **安全性：** AmazonS3提供強大的安全性。

   * 所有目錄都只能由適當的客戶或客戶訪問。
   * HTTPS通訊協定支援上傳和下載。 在[!DNL Audience Manager]中傳輸檔案時，請一律使用HTTPS。
   * AmazonS3提供靜態加密，用於加密[傳出資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我們使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，該方法允許由AmazonS3自動生成和管理加密密鑰。

* **除錯與備份支援：** AmazonS3可 [!DNL Audience Manager] 保留檔案的精確副本，讓除錯或重新傳輸更輕鬆。

如需AmazonS3的詳細資訊，請參閱下列資源：

[Amazon簡單儲存服務(AmazonS3),](https://aws.amazon.com/s3/) 在AmazonWeb服務網站上。

[從AWS文檔網站開始](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 使用Amazon簡單儲存服務。
