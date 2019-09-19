---
description: 針對想要將其他系統（離線）的資料匯入Audience manager的技術和非技術客戶的概述。
keywords: 入站，批次，批次上載，批次資料
seo-description: 技術和非技術客戶的概觀，這些客戶想要將其他系統（離線）的資料匯入Audience Manager。 若要這麼做，請使用Audience manager中的批次上傳選項。
seo-title: ' 傳送批次資料至Audience Manager概觀'
solution: Audience Manager
title: ' 傳送批次資料至Audience Manager概觀'
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


#  傳送批次資料至Audience Manager概觀{#send-batch-data-to-audience-manager-overview}

針對想要將其他系統（離線）的資料匯入Audience manager的技術和非技術客戶的概述。

## 優勢

<!-- c_offline_to_online.xml -->

您可以在Audience manager中提供其他系統的資料。 我們的系統可協助您發揮價值，並運用您先前收集到的使用者資料。 這包括購買、客戶調查、註冊資料、資料庫 [!DNL CRM] 等的相關資訊。 雖然每項整合都會帶來各自的挑戰，但它們都有共同的步驟。 閱讀本資料，協助您減少線下資料上線所需的工作量。

## 步驟1:同步使用者ID

在同步期間，Audience manager會為用戶端及其使用者指派唯一ID。 這些ID分別 [!UICONTROL Data Provider ID] 稱[!UICONTROL DPID]為 [!UICONTROL Unique User ID] ()[!UICONTROL UUID]和()。 Audience manager會使用 [!UICONTROL DPID] 和來 [!UICONTROL UUID] 識別使用者，並讓他們符合特徵、區段、對象群組和報告的資格。 此外，我們的資料收集代碼([!UICONTROL DIL])會尋找這些ID，以從您的網站擷取訪客資料。 完成此步驟後，Audience manager和您的離線儲存庫應包含每個使用者記錄的對應ID。

有關此步驟的重要考慮事項：

* **** 用戶端ID位置：Audience manager需要知道您的用戶端ID在您網站上的顯示位置（例如，它儲存在Cookie、Analytics變數、頁面代碼等中）。
* **[!DNL PII]排除**:使用者ID不得包含個人識別資訊([!DNL PII])。
* **** 區分大小寫和內容：在即時資料同步期間，Audience manager從您的網站擷取的使用者ID必須對應於從離線儲存庫傳入的ID。 例如，若離線記錄包含相關資訊 [!DNL User123]，但您的網站將該ID轉譯為 [!DNL USER123],Audience manager會將這些ID視為不同的訪客。 因此，此訪客的線上資訊無法與離線資料庫中的對應記錄建立關聯。 ID必須完全相符。

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## 步驟2:資料檔案格式

檔案名稱和內容遵循嚴格的准則。 您必 *鬚根據本指南* 中的這些規格來命名和組織資料檔案。 請參閱:

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站資料檔案內容：語法、變數和範例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料可供離線行銷工作使用

當您將離線資料線上化時，您仍可將這項資訊用於離線促銷活動。 為此，Audience manager會將特徵和區段資訊匯出至您 [!DNL FTP] 所選 [!DNL Amazon S3] 的或位置。 如需詳細資訊或協助，請洽詢您的合作夥伴解決方案經理。

## 環境

Audience manager提供下列檔案下拉環境：

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