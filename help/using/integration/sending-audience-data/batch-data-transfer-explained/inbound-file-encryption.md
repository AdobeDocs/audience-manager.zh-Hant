---
description: 選項是，您可以在將資料檔案傳送至Audience Manager時，以PGP加密方式加密資料檔案。
seo-description: 選項是，您可以在將資料檔案傳送至Audience Manager時，以PGP加密方式加密資料檔案。
seo-title: 傳入資料類型的檔案 PGP 加密
solution: Audience Manager
title: 傳入資料類型的檔案 PGP 加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: 傳入資料傳輸
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 12%

---

# 傳入資料類型的檔案 PGP 加密{#file-pgp-encryption-for-inbound-data-types}

將資料檔案發送到Audience Manager時，可以使用[!DNL PGP]加密來加密資料檔案。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 加密包括檔案壓縮。傳送[!DNL PGP]加密的傳入檔案時，請務必不要使用gzip(`.gz`)來壓縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。[
>
>[!DNL PGP] 加密的傳入檔案也被壓 [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 縮，在Audience Manager中無效。

請依照下列步驟加密傳入的資料檔案。

1. 下載[Audience Manager公開金鑰](./assets/adobe_pgp.pub)。
2. 將公開金鑰匯入信任的存放區。

   例如，如果使用[!DNL GPG]，命令可能類似於：

   `gpg --import adobe_pgp.pub`

3. 執行下列命令，以驗證金鑰是否已正確匯入：

   `gpg --list-keys`

   您應該會看到類似下列的訊息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用下列命令加密入站資料：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密資料都必須使用`.pgp`或`.gpg`作為副檔名(例如`ftp_dpm_100_123456789.sync.pgp`或`ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience Manager僅支援[!DNL Advanced Encryption Standard (AES)] data-encryption算法。 Audience Manager支援任何金鑰大小。
