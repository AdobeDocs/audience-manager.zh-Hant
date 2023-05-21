---
description: Audience Manager根據這些規範向第三方內容提供商發送批處理資料。
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: 批次傳出資料傳輸
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 19%

---

# 批次傳出資料傳輸

Audience Manager根據這些規範向第三方內容提供商發送批處理資料。

* [傳出資料檔案名稱：語法與範例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   描述用於命名出站資料檔案的必需欄位、語法和約定。

* [配置批資料傳輸整合](batch-server-configuration.md)

   介紹配置批處理資料傳輸整合的方法。

* [用於記錄檔傳輸的傳輸控制檔案](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   傳輸控制(.info)檔案提供有關檔案傳輸的元資料資訊，以便合作夥伴可以驗證Audience Manager處理的檔案傳輸是否正確。

* [輸出範本巨集](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   列出可用於建立出站模板的宏。 這些宏包括檔案名宏、標題宏和內容宏。

* [輸出巨集範例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   一些常用宏用於建立出站檔案模板的示例。

* [請對您的傳出文件使用 Amazon S3 跨帳戶貯體權限](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   使用Amazon簡單儲存服務(AmazonS3)的客戶的出站資料傳輸過程要求我們要求您的AmazonS3訪問密鑰和密鑰，以便將出站資料檔案傳送到您的儲存桶。
