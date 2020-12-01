---
description: 針對使用Amazon Simple Storage Service(Amazon S3)的客戶的出站資料傳輸流程要求我們要求您輸入Amazon S3訪問密鑰和密鑰，以便將出站資料檔案發送到您的儲存桶。
seo-description: 針對使用Amazon Simple Storage Service(Amazon S3)的客戶的出站資料傳輸流程要求我們要求您輸入Amazon S3訪問密鑰和密鑰，以便將出站資料檔案發送到您的儲存桶。
seo-title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
solution: Audience Manager
title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

使用[!DNL Amazon Simple Storage Service]([!DNL Amazon S3])的客戶的[!UICONTROL Outbound Data Transfer]程式要求我們要求您輸入[!DNL Amazon S3]存取金鑰和機密金鑰，以便將傳出資料檔案傳送至您的儲存貯體。

如果您不想與我們共用[!DNL Amazon S3]存取金鑰和機密金鑰，請連絡您的[!DNL Audience Manager]顧問或客戶服務，他們會為您設定[!DNL Cross-Account Bucket Permissions]。 您只需將我們的[!DNL Amazon S3]帳戶ID新增至您要接收傳出資料檔案的[!DNL S3]貯體的允許清單，如[Amazon S3檔案](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)所述。 您的[!DNL Audience Manager]顧問或客戶服務會為您提供我們的[!DNL Amazon S3]帳戶ID。