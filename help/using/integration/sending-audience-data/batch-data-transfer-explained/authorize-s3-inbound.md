---
description: 若要將資料從您自己的Amazon S3儲存貯體傳送至Audience Manager，您必須先要求設定專用的Amazon S3角色。
solution: Audience Manager
title: 對您的傳入檔案運用Amazon S3跨帳戶貯體許可權
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# 對您的傳入檔案運用Amazon S3跨帳戶貯體許可權 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

若要將資料從您自己的Amazon S3儲存貯體傳送至Audience Manager，您必須先要求設定專用的Amazon S3角色。

請依照下列步驟以執行此操作。

1. 請聯絡客戶服務，要求以其他方法傳送檔案至Audience Manager。
2. 為您用來傳送檔案的Amazon S3帳戶中的角色提供客戶服務[!DNL Amazon Resource Name (ARN)]。 _在您連絡客戶服務前，必須先建立此角色_。 完成設定後，客戶服務將為您新建立的角色提供[!DNL Amazon Resource Name (ARN)]。
3. 編輯您現有Amazon S3角色的許可權，承擔由客戶服務提供的角色。

>[!NOTE]
>
>將傳入資料傳輸至Audience Manager Amazon S3儲存貯體時，請務必使用`bucket-owner-full-control` [存取控制清單](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)，以便Audience Manger正確處理資料。
>
>Amazon Web Services命令的範例： `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
