---
description: 選項是，當您將資料檔案傳送至Audience Manager時，可使用PGP加密來加密資料檔案。
seo-description: 選項是，當您將資料檔案傳送至Audience Manager時，可使用PGP加密來加密資料檔案。
seo-title: 傳入資料類型的檔案PGP加密
solution: Audience Manager
title: 傳入資料類型的檔案PGP加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 傳入資料類型的檔案PGP加密{#file-pgp-encryption-for-inbound-data-types}

選項是，當將資料檔案傳送至Audience manager時，您可 [!DNL PGP] 以加密資料檔案。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>我們目前不支援相同傳入資料檔案的加密和壓縮。 您可以選擇加密或壓 [縮傳入](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 的檔案。

請依照下列步驟來加密傳入的資料檔案。

1. 下載 [Audience manager公開金鑰](./assets/adobe_pgp.pub)。
1. 將公開金鑰匯入您信任的商店。

   例如，如果您使用 [!DNL GPG]，該命令可能類似於以下內容：

   `gpg --import adobe_pgp.pub`

1. 通過運行以下命令驗證密鑰是否已正確導入：

   `gpg --list-keys`

   您應該會看到類似下列的訊息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. 使用以下命令加密入站資料：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密的資 `.pgp` 料都 `.gpg` 必須使用或做為副檔名( `ftp_dpm_100_123456789.sync.pgp` 例如或 `ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience manager僅支援資料 [!DNL Advanced Encryption Standard (AES)] 加密演算法。 Audience manager支援任何金鑰大小。