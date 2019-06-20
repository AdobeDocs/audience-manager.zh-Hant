---
description: 作為選項，您可以在傳送至Audience Manager時壓縮資料檔案。
seo-description: 作為選項，您可以在傳送至Audience Manager時壓縮資料檔案。
seo-title: 傳入資料傳輸檔案的檔案壓縮
solution: Audience Manager
title: 傳入資料傳輸檔案的檔案壓縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

作為選項，您可以在傳送至Audience Manager時壓縮資料檔案。

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager也支援未壓縮的檔案。

>[!IMPORTANT]
>
>我們目前不支援相同傳入資料檔案上的加密和壓縮。You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Amazon S壓縮

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. 壓縮的檔案必須為GB或更小。如果檔案較大，請與客戶服務討論檔案和傳輸程序。Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>[!DNL FTP] 您的用戶端必須使用二進位模式來傳輸壓縮或加密檔案。Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## 最佳實務

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* `.gz` 壓縮檔案的壓縮檔案大小上限為1GB。
* 最佳化分割大小最快/最早處理檔案的大小約為1GB，壓縮為200-300MB。
* [!DNL Amazon S3] 會對上傳檔案造成5GB的檔案大小限制。