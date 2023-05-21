---
description: 作為選項，在將資料檔案發送到Audience Manager時，可以使用PGP加密來加密它們。
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: 傳入資料類型的檔案 PGP 加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# 傳入資料類型的檔案 PGP 加密{#file-pgp-encryption-for-inbound-data-types}

您可以使用 [!DNL PGP] 將其發送到Audience Manager時進行加密。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 加密包括檔案壓縮。 發送時 [!DNL PGP] 加密的入站檔案，確保不 [壓縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 使用gzip(`.gz`)。
>
>[!DNL PGP] 加密的入站檔案 [壓縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 在Audience Manager中無效。

按照下面介紹的步驟加密入站資料檔案。

1. 下載 [Audience Manager公鑰](./assets/adobe_pgp.pub)。
2. 將公鑰導入受信任的儲存。

   例如，如果 [!DNL GPG]，該命令可能與以下命令類似：

   `gpg --import adobe_pgp.pub`

3. 通過運行以下命令驗證密鑰是否已正確導入：

   `gpg --list-keys`

   您應看到類似以下內容的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用以下命令加密入站資料：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密資料必須使用 `.pgp` 或 `.gpg` 作為檔案副檔名(例如 `ftp_dpm_100_123456789.sync.pgp` 或 `ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience Manager僅支援 [!DNL Advanced Encryption Standard (AES)] 資料加密算法。 Audience Manager支援任何密鑰大小。
