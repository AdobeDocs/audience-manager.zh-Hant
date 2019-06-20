---
description: 您可以在傳送至Audience Manager時，使用PGP加密加密資料檔案。
seo-description: 您可以在傳送至Audience Manager時，使用PGP加密加密資料檔案。
seo-title: 傳入資料類型的檔案PGP加密
solution: Audience Manager
title: 傳入資料類型的檔案PGP加密
uuid: 89casace1-0259-48fc-865b-d525 ec7822 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>我們目前不支援相同傳入資料檔案上的加密和壓縮。You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

依照下列步驟加密傳入的資料檔案。

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. 將公開金鑰匯入您信任的商店。

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. 執行下列命令，驗證索引鍵已正確匯入：

   `gpg --list-keys`

   您應該會看到類似下列的訊息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. 使用下列命令加密傳入的資料：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager支援任何索引鍵大小。