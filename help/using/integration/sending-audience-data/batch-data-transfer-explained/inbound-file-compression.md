---
description: 選項是，在將資料檔案傳送至Audience Manager時，您可以壓縮這些檔案。
seo-description: 選項是，在將資料檔案傳送至Audience Manager時，您可以壓縮這些檔案。
seo-title: 傳入資料傳輸檔案的檔案壓縮
solution: Audience Manager
title: 傳入資料傳輸檔案的檔案壓縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# 傳入資料傳輸檔案的檔案壓縮{#file-compression-for-inbound-data-transfer-files}

您可以在將資料檔案傳送至Audience Manager時，加以壓縮。

<!-- inbound-file-compression.xml -->

Audience Manager支援gzip(`.gz`)壓縮，以用於傳入、非同步資料傳輸。

Audience Manager也支援解壓縮的檔案。

>[!IMPORTANT]
>
>我們不支援對使用gzip(`.gz`)壓縮的傳入檔案進行加密。
>
>要加密和壓縮入站檔案，請使用[PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP] 加密包括檔案壓縮。

## AmazonS3壓縮

若要傳送至[!DNL Amazon S3]，您必須使用`.gz`或未壓縮檔案。 壓縮檔案必須為1 GB或更小。 如果檔案較大，請與客戶服務討論檔案和傳輸程式。 雖然[!DNL Audience Manager]可處理非常大的檔案，但是可能有方法來減少檔案大小或提高資料傳輸的效率。

>[!IMPORTANT]
>
>您的[!DNL FTP]客戶端必須使用二進位模式來傳輸壓縮或加密的檔案。 在[!DNL ASCII]模式下發送的壓縮或加密檔案將損壞資料傳輸檔案。

## 最佳實務

* 檔案應壓縮為[!DNL .gzip]（且副檔名為[!DNL .gz]）。
* `.gz`壓縮檔案的最大壓縮檔案大小為1 GB。
* 最佳分割大小，以最快速／最早地處理檔案，大約是1 GB的解壓縮或200-300 MB的壓縮。
* [!DNL Amazon S3] 對已上傳的檔案施加5 GB檔案大小限制。
