---
description: 使用Amazon簡單儲存服務(Amazon S3)之客戶的傳出資料傳輸程式會要求我們提供您的Amazon S3存取金鑰和機密金鑰，以將傳出資料檔案傳送至您的貯體。
seo-description: 使用Amazon簡單儲存服務(Amazon S3)之客戶的傳出資料傳輸程式會要求我們提供您的Amazon S3存取金鑰和機密金鑰，以將傳出資料檔案傳送至您的貯體。
seo-title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
solution: Audience Manager
title: 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: 傳出資料傳輸
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# 請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

使用[!DNL Amazon Simple Storage Service]([!DNL Amazon S3])的客戶的[!UICONTROL Outbound Data Transfer]程式會要求我們提供您的[!DNL Amazon S3]存取金鑰和機密金鑰，以將傳出資料檔案傳送至您的貯體。

如果您不想與我們共用您的[!DNL Amazon S3]存取金鑰和秘密金鑰，請聯絡您的[!DNL Audience Manager]顧問或客戶服務，他們會為您設定[!DNL Cross-Account Bucket Permissions]。 您只需要將[!DNL Amazon S3]帳戶ID新增至[!DNL S3]貯體的允許清單，以便接收傳出資料檔案，如[Amazon S3檔案](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)所述。 您的[!DNL Audience Manager]顧問或客戶服務會提供您的[!DNL Amazon S3]帳戶ID。
