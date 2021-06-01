---
description: 作為選項，您可以在將資料檔案傳送至Audience Manager時壓縮這些檔案。
seo-description: 作為選項，您可以在將資料檔案傳送至Audience Manager時壓縮這些檔案。
seo-title: 傳入資料傳輸檔案的檔案壓縮
solution: Audience Manager
title: 傳入資料傳輸檔案的檔案壓縮
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: 傳入資料傳輸
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# 傳入資料傳輸檔案的檔案壓縮{#file-compression-for-inbound-data-transfer-files}

將資料檔案傳送至Audience Manager時，您可以壓縮這些檔案。

<!-- inbound-file-compression.xml -->

Audience Manager支援傳入、非同步資料傳輸的gzip(`.gz`)壓縮。

Audience Manager也支援未壓縮的檔案。

>[!IMPORTANT]
>
>不支援對使用gzip(`.gz`)壓縮的傳入檔案進行加密。
>
>若要加密和壓縮傳入檔案，請使用[PGP encryption](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP] 加密包括檔案壓縮。

## Amazon S3壓縮

若要傳送至[!DNL Amazon S3]，您必須使用`.gz`或未壓縮檔案。 壓縮檔案必須是1 GB或更小。 如果檔案較大，請與客戶服務討論檔案和傳輸程式。 雖然[!DNL Audience Manager]可以處理非常大的檔案，但可能有辦法減小檔案大小或提高資料傳輸的效率。

>[!IMPORTANT]
>
>您的[!DNL FTP]客戶端必須使用二進位模式來傳輸壓縮或加密的檔案。 以[!DNL ASCII]模式發送的壓縮或加密檔案將損壞資料傳輸檔案。

## 最佳實務

* 檔案應壓縮[!DNL .gzip]（且副檔名為[!DNL .gz]）。
* `.gz`壓縮檔案的最大壓縮檔案大小為1 GB。
* 最佳分割大小，可以最快/最早地處理檔案，未壓縮大約1 GB或壓縮200-300 MB。
* [!DNL Amazon S3] 會對上傳的檔案施加自己的5 GB檔案大小限制。
