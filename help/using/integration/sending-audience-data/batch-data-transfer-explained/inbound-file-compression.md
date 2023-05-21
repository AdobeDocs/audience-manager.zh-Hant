---
description: 作為一個選項，可以在將資料檔案發送到Audience Manager時壓縮它們。
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: 傳入資料傳輸檔案的檔案壓縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 7%

---

# 傳入資料傳輸檔案的檔案壓縮{#file-compression-for-inbound-data-transfer-files}

可以將資料檔案發送到Audience Manager時進行壓縮。

<!-- inbound-file-compression.xml -->

Audience Manager支援gzip(`.gz`)用於入站非同步資料傳輸的壓縮。

Audience Manager還支援未壓縮的檔案。

>[!IMPORTANT]
>
>不支援對使用gzip壓縮的入站檔案進行加密(`.gz`)。
>
>要加密和壓縮入站檔案，請使用 [PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP] 加密包括檔案壓縮。

## AmazonS3壓縮

用於交貨到 [!DNL Amazon S3]，必須使用 `.gz` 或未壓縮的檔案。 壓縮檔案必須為1 GB或更小。 如果檔案較大，請與客戶服務部門討論檔案和傳輸過程。 儘管 [!DNL Audience Manager] 可以處理非常大的檔案，可能有辦法減小檔案大小或提高資料傳輸的效率。

>[!IMPORTANT]
>
>您 [!DNL FTP] 客戶端必須使用二進位模式來傳輸壓縮或加密的檔案。 已壓縮或加密的檔案已發送到 [!DNL ASCII] 模式將損壞資料傳輸檔案。

## 最佳實務

* 檔案應為 [!DNL .gzip] 壓縮(並具有 [!DNL .gz] 檔案副檔名)。
* 最大壓縮檔案大小 `.gz` 壓縮檔案為1 GB。
* 最佳剝離大小（用於檔案的最快/最早處理）大約是1 GB未壓縮或200-300 MB壓縮。
* [!DNL Amazon S3] 對上載的檔案施加其自己的5 GB檔案大小限制。
