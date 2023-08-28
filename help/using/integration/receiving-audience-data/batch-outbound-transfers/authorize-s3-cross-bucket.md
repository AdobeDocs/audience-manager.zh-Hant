---
description: 使用Amazon Simple Storage Service (Amazon S3)的客戶的「傳出資料傳輸」程式需要我們要求您的Amazon S3存取金鑰和秘密金鑰，才能將傳出資料檔案傳送至您的貯體。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

此 [!UICONTROL Outbound Data Transfer] 適用於客戶的程式，使用 [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3])需要我們詢問您的 [!DNL Amazon S3] 存取金鑰和秘密金鑰，以將傳出資料檔案傳遞至您的貯體。

若您不想共用您的 [!DNL Amazon S3] 使用我們的存取金鑰與秘密金鑰，請連絡您的 [!DNL Audience Manager] 顧問或客戶服務，他們將會設定 [!DNL Cross-Account Bucket Permissions] 敬請參考使用：

您只需要新增我們的 [!DNL Amazon S3] 帳戶ID加入允許清單 [!DNL S3] 您想要接收傳出資料檔案的貯體，如 [Amazon S3檔案](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). 您的 [!DNL Audience Manager] 顧問或客戶服務將提供 [!DNL Amazon S3] 帳戶ID。
