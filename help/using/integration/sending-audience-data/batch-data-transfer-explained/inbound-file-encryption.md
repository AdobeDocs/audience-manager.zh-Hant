---
description: 您可以選擇將資料檔案傳送至Audience Manager時，使用PGP加密來加密檔案。
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: 傳入資料型別的檔案PGP加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
TQID: https://experienceleague.adobe.com/eUhGeYNzSeQxjQ0VWydB8vnmgFh9GnWQQ3VmAG73w-k
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 165
ht-degree: 0%

---

# 傳入資料型別的檔案PGP加密{#file-pgp-encryption-for-inbound-data-types}

當資料檔傳送至Audience Manager時，您可以使用[!DNL PGP]加密來加密資料檔。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP]加密包含檔案壓縮。 傳送[!DNL PGP]個加密的傳入檔案時，請確定您未使用gzip ([) &#x200B;](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)壓縮`.gz`它們。
>
>在Audience Manager中，[!DNL PGP]同樣為[壓縮](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)的加密傳入檔案無效。

請依照下列步驟，加密傳入的資料檔案。

1. 下載[Audience Manager公開金鑰](./assets/adobe_pgp.pub)。
2. 將公開金鑰匯入您的信任存放區。

   例如，如果您使用[!DNL GPG]，則命令可能類似於以下內容：

   `gpg --import adobe_pgp.pub`

3. 執行下列命令，驗證金鑰是否已正確匯入：

   `gpg --list-keys`

   您應該會看到類似下列的訊息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用下列命令加密傳入資料：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密的資料都必須使用`.pgp`或`.gpg`做為副檔名（例如`ftp_dpm_100_123456789.sync.pgp`或`ftp_dpm_100_123456789.overwrite.gpg`）。

   >[!NOTE]
   >
   >Audience Manager僅支援[!DNL Advanced Encryption Standard (AES)]資料加密演演算法。 Audience Manager支援任何金鑰大小。
