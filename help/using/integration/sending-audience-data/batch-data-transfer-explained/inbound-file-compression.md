---
description: 您可以選擇將資料檔案傳送至Audience Manager時加以壓縮。
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: 傳入資料傳輸檔案的檔案壓縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# 傳入資料傳輸檔案的檔案壓縮{#file-compression-for-inbound-data-transfer-files}

將資料檔案傳送至Audience Manager時，您可以加以壓縮。

<!-- inbound-file-compression.xml -->

Audience Manager支援gzip (`.gz`)壓縮，以進行傳入的非同步資料傳輸。

Audience Manager也支援未壓縮檔案。

>[!IMPORTANT]
>
>不支援使用gzip (`.gz`)壓縮之輸入檔案的加密。
>
>若要加密及壓縮輸入檔案，請使用[PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP]加密包含檔案壓縮。

## Amazon S3壓縮

若要傳遞至[!DNL Amazon S3]，您必須使用`.gz`或未壓縮的檔案。 壓縮檔案的大小必須為1 GB。 如果檔案較大，請與客戶服務討論檔案和傳輸流程。 雖然[!DNL Audience Manager]可以處理非常大型的檔案，但可能有方法減少檔案大小，或讓資料傳輸更有效率。

>[!IMPORTANT]
>
>您的[!DNL FTP]使用者端必須使用二進位模式來傳輸壓縮或加密的檔案。 以[!DNL ASCII]模式傳送的壓縮或加密檔案將會損毀資料傳輸檔案。

## 最佳實務

* 檔案應該是[!DNL .gzip]個壓縮檔（且副檔名為[!DNL .gz]）。
* `.gz`壓縮檔案的最大壓縮檔案大小為1 GB。
* 最佳的分割大小，適用於最快/最早的檔案處理，大約是1 GB的未壓縮檔案或200-300 MB的壓縮檔案。
* [!DNL Amazon S3]對上傳的檔案施加自己的5 GB檔案大小限制。
