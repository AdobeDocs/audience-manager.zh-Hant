---
description: 技術客戶和非技術客戶希望將其他系統（離線）中的資料引入Audience Manager。
keywords: 入站，批處理，批處理上載，批處理資料
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: 將批次資料傳送至 Audience Manager 概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 6%

---

# 將批資料發送到 [!DNL Audience Manager] 概述 {#send-batch-data-to-audience-manager-overview}

技術客戶和非技術客戶希望將其他系統（離線）中的資料帶入 [!DNL Audience Manager]。

## 優勢

您可以在中使其他系統的資料可用 [!DNL Audience Manager]。 我們的系統可以幫助您釋放價值並利用您以前收集的用戶資料。 這包括有關購買、客戶調查、註冊資料、 [!DNL CRM] 資料庫等 儘管每一個整合都帶來了各自的挑戰，但它們都有這些共同步驟。 查看此資料，以幫助減少使離線資料聯機所需的工作量。

## 步驟1:同步用戶ID

在同步過程中， [!DNL Audience Manager] 為客戶端及其用戶分配唯一ID。 這些ID稱為 [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) [!UICONTROL Unique User ID] ([!UICONTROL UUID])。 [!DNL Audience Manager] 使用 [!UICONTROL DPID] 和 [!UICONTROL UUID] 確定用戶並確定其資格 [!UICONTROL traits]。 [!UICONTROL segments]、受眾組和用於報告。 此外，我們的資料收集代碼([!UICONTROL DIL])查找這些ID以從您的網站捕獲訪問者資料。 完成此步驟後， [!DNL Audience Manager] 離線儲存庫應包含每個用戶記錄的相應ID。

有關此步驟的重要考慮事項：

* **客戶端ID放置：** [!DNL Audience Manager] 需要知道您的客戶端ID在您的網站上的顯示位置（例如，它是否儲存在cookie、分析變數、頁碼等中）。
* **排除 [!DNL PII]:** 用戶ID不得包含個人身份資訊([!DNL PII])。
* **大小寫和內容敏感性：** 在即時資料同步期間，通過 [!DNL Audience Manager] 必須與從離線儲存庫傳入的ID對應。 例如，如果離線記錄包含有關 [!DNL User123]，但您的站點將該ID呈現為 [!DNL USER123]。 [!DNL Audience Manager] 把它們看成不同的訪客。 因此，此訪問者的聯機資訊不能與離線資料庫中的相應記錄關聯。 ID必須完全匹配。

請參閱 [入站資料傳輸的ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)。

## 步驟2:資料檔案格式

檔案名和內容遵循嚴格的准則。 你 *必須* 根據本指南中的這些規範命名和組織資料檔案。 請參閱：

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站資料檔案內容：語法、變數和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料可用於離線營銷工作

在將離線資料聯機時，您仍然可以將此資訊用於離線市場活動。 要做到這一點， [!DNL Audience Manager] 將特性和段資訊導出到 [!DNL FTP] 或 [!DNL Amazon S3] 選擇的位置。 請聯繫您的合作夥伴解決方案經理以獲取其他資訊或幫助。

## 環境

[!DNL Audience Manager] 為檔案下拉提供以下環境：

| 環境 | 服務 | 位置 |
|---------|----------|---------|
| 生產 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s客戶端</li><li>ftp-in.demdex.com</li></ul> |
| Beta環境 | <ul><li>AmazonS3</li><li>FTP</li></ul> | <ul><li>demdex s2s客戶端 — sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;&quot;

## 進一步的技術閱讀

系統工程師、開發人員或技術/實施團隊應審查 [描述的批資料傳輸流程](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 以及本節中的其他條款。 這些文章提供了有關傳輸協定、檔案內容和檔案名要求的詳細資訊。
