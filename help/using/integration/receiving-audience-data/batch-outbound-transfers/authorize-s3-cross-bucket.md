---
description: 使用Amazon Simple Storage Service(Amazon S3)的客戶離線資料傳輸程序要求您要求Amazon S存取金鑰和秘密金鑰，以便將傳出資料檔案傳送至您的儲存貯體。
seo-description: 使用Amazon Simple Storage Service(Amazon S3)的客戶離線資料傳輸程序要求您要求Amazon S存取金鑰和秘密金鑰，以便將傳出資料檔案傳送至您的儲存貯體。
seo-title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
solution: Audience Manager
title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
uuid: 400a8d67-ef3-48be-aa3 f-498a5441 f498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

The [!UICONTROL Outbound Data Transfer] process for customers using [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requires us to ask for your [!DNL Amazon S3] access key and secret key, in order to deliver the outbound data files to your bucket.

If you'd rather not share your [!DNL Amazon S3] access key and secret key with us, contact your [!DNL Audience Manager] consultant or Customer Care and they will set up [!DNL Cross-Account Bucket Permissions] for you. You only need to whitelist our [!DNL Amazon S3] account ID for the [!DNL S3] bucket where you wish to receive the outbound data files, as described in the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). [!DNL Audience Manager] 您的顧問或客戶服務會提供 [!DNL Amazon S3] 我們帳戶ID給您。