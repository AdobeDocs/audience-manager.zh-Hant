---
description: 使用Amazon Simple Storage Service (Amazon S3)的客戶的「傳出資料傳輸」程式需要我們要求您的Amazon S3存取金鑰和秘密金鑰，才能將傳出資料檔案傳送至您的貯體。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 請對您的傳出檔案使用Amazon S3跨帳戶貯體許可權
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
TQID: https://experienceleague.adobe.com/Ji1ltYPv4eoY5-eZiX62JyQ5SJzdMjFZdKeRzJnwKZg
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 186
ht-degree: 0%

---

# 請對您的傳出檔案使用Amazon S3跨帳戶貯體許可權 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

使用[!UICONTROL Outbound Data Transfer] ([!DNL Amazon Simple Storage Service])之客戶的[!DNL Amazon S3]程式需要我們要求您的[!DNL Amazon S3]存取金鑰和秘密金鑰，以將傳出資料檔案傳遞給您的貯體。

若您不想與我們共用您的[!DNL Amazon S3]存取金鑰與秘密金鑰，請連絡您的[!DNL Audience Manager]顧問或客戶服務，他們將會為您設定[!DNL Cross-Account Bucket Permissions]。

您只需要將我們的[!DNL Amazon S3]帳戶ID新增至您想要接收傳出資料檔案的[!DNL S3]儲存貯體的允許清單，如[Amazon S3檔案](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)所述。 您的[!DNL Audience Manager]顧問或客戶服務將提供您的[!DNL Amazon S3]帳戶ID。

>[!NOTE]
>
>由於Amazon S3物件大小限制，Audience Manager支援最高1 TB的分割大小。 如果您未指定任何分割大小，則會自動套用1 TB限制。

