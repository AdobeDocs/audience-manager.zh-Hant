---
description: 技術和非技術客戶的概觀，這些客戶想要將其他系統（離線）的資料匯入Audience Manager。
keywords: inbound, batch, batch upload, batch data
seo-description: 技術和非技術客戶的概觀，這些客戶想要將其他系統（離線）的資料匯入Audience Manager。 若要這麼做，請使用Audience Manager中的批次上傳選項。
seo-title: 將批次資料傳送至 Audience Manager 概述
solution: Audience Manager
title: 將批次資料傳送至 Audience Manager 概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 6%

---


# Send Batch Data to [!DNL Audience Manager] Overview {#send-batch-data-to-audience-manager-overview}

技術客戶和非技術客戶想要將其他系統（離線）的資料帶入其中的概述 [!DNL Audience Manager]。

## 優勢

您可以在中提供其他系統的資料 [!DNL Audience Manager]。 我們的系統可協助您發揮價值，並運用您先前收集到的使用者資料。 這包括購買、客戶調查、註冊資料、資料庫 [!DNL CRM] 等的相關資訊。 雖然每項整合都會帶來各自的挑戰，但它們都有共同的步驟。 閱讀本資料，協助您減少線下資料上線所需的工作量。

## 步驟1: 同步使用者ID

在同步期間， [!DNL Audience Manager] 會為客戶端及其用戶分配唯一的ID。 這些ID分別 [!UICONTROL Data Provider ID] 稱[!UICONTROL DPID]為 [!UICONTROL Unique User ID] ()[!UICONTROL UUID]和()。 [!DNL Audience Manager] 使用 [!UICONTROL DPID] 和 [!UICONTROL UUID] 來識別使用者，並限定他們 [!UICONTROL traits]使用、 [!UICONTROL segments]觀眾群組和報告。 此外，我們的資料收集代碼([!UICONTROL DIL])會尋找這些ID，以從您的網站擷取訪客資料。 完成此步驟後，您的離 [!DNL Audience Manager] 線儲存庫應包含每個用戶記錄的相應ID。

有關此步驟的重要考慮事項：

* **用戶端ID位置：** [!DNL Audience Manager] 需要知道您的用戶端ID在您網站上的顯示位置（例如，它是否儲存在Cookie、Analytics變數、頁面程式碼等）。
* **排除[!DNL PII]:** 使用者ID不得包含個人識別資訊([!DNL PII])。
* **區分大小寫和內容：** 在即時資料同步期間，從您的網站擷取的使用者ID必須 [!DNL Audience Manager] 與從離線儲存庫傳入的ID對應。 例如，若離線記錄包含相關資 [!DNL User123]訊，但您的網站會將該ID轉譯為 [!DNL USER123], [!DNL Audience Manager] 則會將其視為不同訪客。 因此，此訪客的線上資訊無法與離線資料庫中的對應記錄建立關聯。 ID必須完全相符。

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## 步驟2: 資料檔案格式

檔案名稱和內容遵循嚴格的准則。 您必 *鬚根據本指南* 中的這些規格來命名和組織資料檔案。 請參閱：

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站資料檔案內容： 語法、變數和範例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料可供離線行銷工作使用

當您將離線資料線上化時，您仍可將這項資訊用於離線促銷活動。 若要這麼做， [!DNL Audience Manager] 請將特徵和區段資訊匯出至 [!DNL FTP] 您所選 [!DNL Amazon S3] 的或位置。 如需詳細資訊或協助，請洽詢您的合作夥伴解決方案經理。

## 環境

[!DNL Audience Manager] 為檔案刪除提供以下環境：

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 環境 </th> 
   <th colname="col02" class="entry"> 服務 </th> 
   <th colname="col2" class="entry"> 位置 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>生產</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>測試版環境</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 進一步的技術閱讀

系統工程師、開發人員或技術／實作團隊應檢閱「描述的 [批次資料傳輸流程](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) 」及本節中的其他文章。 這些文章提供傳輸通訊協定、檔案內容和檔案名稱要求的詳細資訊。
