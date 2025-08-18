---
description: 想要將其他系統（離線）的資料帶入Audience Manager的技術與非技術客戶概觀。
keywords: 傳入、批次、批次上傳、批次資料
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: 將批次資料傳送至Audience Manager概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# 將批次資料傳送至[!DNL Audience Manager]總覽 {#send-batch-data-to-audience-manager-overview}

想要將其他系統（離線）的資料帶入[!DNL Audience Manager]的技術與非技術客戶概觀。

## 優勢

您可以在[!DNL Audience Manager]中使用其他系統的資料。 我們的系統可協助您解鎖價值，並運用您先前收集的使用者資料。 這包括購買、客戶調查、註冊資料、[!DNL CRM]資料庫等相關資訊。 雖然每項整合都有各自的挑戰，但它們都有這些共同步驟。 請檢閱此資料，協助您減少將離線資料上線所需的工作。

## 步驟1：同步使用者ID

同步處理期間，[!DNL Audience Manager]會指派唯一識別碼給使用者端及其使用者。 這些識別碼分別稱為[!UICONTROL Data Provider ID] ([!UICONTROL DPID])和[!UICONTROL Unique User ID] ([!UICONTROL UUID])。 [!DNL Audience Manager]會使用[!UICONTROL DPID]和[!UICONTROL UUID]來識別使用者，並授與他們[!UICONTROL traits]、[!UICONTROL segments]、對象群組及報表的資格。 此外，我們的資料收集程式碼([!UICONTROL DIL])會尋找這些ID，以從您的網站擷取訪客資料。 完成此步驟後，[!DNL Audience Manager]和您的離線存放庫應包含每個使用者記錄的對應ID。

此步驟的重要考量事項：

* **使用者端ID位置：** [!DNL Audience Manager]需要知道您的使用者端ID在您網站上的顯示位置（例如，它是否儲存在Cookie、Analytics變數、頁面代碼等）。
* **排除[!DNL PII]：**&#x200B;使用者識別碼不得包含個人識別資訊([!DNL PII])。
* **區分大小寫與內容：**&#x200B;在即時資料同步期間，[!DNL Audience Manager]從您的網站擷取的使用者ID必須對應到從離線存放庫傳入的ID。 例如，如果離線記錄儲存有關[!DNL User123]的資訊，但您的網站將該ID轉譯為[!DNL USER123]，[!DNL Audience Manager]會將它們視為不同的訪客。 因此，此訪客的線上資訊無法與離線資料庫中的對應記錄建立關聯。 ID必須完全相符。

請參閱傳入資料傳輸的[ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)。

## 步驟2：資料檔案格式

檔案名稱和內容遵循嚴格的准則。 您&#x200B;*必須*&#x200B;根據本指南中的這些規格命名並組織資料檔案。 請參閱：

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [傳入資料檔案內容：語法、變數和範例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料可用於離線行銷工作

當您將離線資料上線時，您仍可將此資訊用於離線行銷活動。 若要這麼做，[!DNL Audience Manager]會將特徵和區段資訊匯出至您選擇的[!DNL FTP]或[!DNL Amazon S3]位置。 如需其他資訊或協助，請連絡您的合作夥伴解決方案經理。

## 環境

[!DNL Audience Manager]為檔案流失提供下列環境：

| 環境 | 服務 | 位置 |
|---------|----------|---------|
| 生產 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta環境 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## 進一步技術閱讀

系統工程師、開發人員或技術/實作團隊應檢閱[描述的](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)批次資料傳輸程式，以及本節中的其他文章。 這些文章提供傳輸通訊協定、檔案內容和檔案名稱要求的詳細資訊。
