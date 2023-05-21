---
description: 使用Amazon簡單儲存服務(AmazonS3)的客戶的出站資料傳輸過程要求我們要求您的AmazonS3訪問密鑰和密鑰，以便將出站資料檔案傳送到您的儲存桶。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

的 [!UICONTROL Outbound Data Transfer] 客戶使用的流程 [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3])要求我們 [!DNL Amazon S3] 訪問密鑰和密鑰，以便將出站資料檔案傳送到儲存桶。

如果你不想和你 [!DNL Amazon S3] 與我們聯繫，聯繫 [!DNL Audience Manager] 顧問或客戶服務，他們將 [!DNL Cross-Account Bucket Permissions] 為你。 您只需添加 [!DNL Amazon S3] 帳戶ID到允許清單 [!DNL S3] 希望接收出站資料檔案的儲存段，如中所述 [AmazonS3文檔](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)。 您 [!DNL Audience Manager] 顧問或客戶服務將為您提供 [!DNL Amazon S3] 帳戶ID。
