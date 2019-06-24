---
description: 概述想要將資料從其他系統(離線)帶入Audience Manager的技術和非技術客戶。
keywords: 傳入傳入
seo-description: 概述想要將資料從其他系統(離線)帶入Audience Manager的技術和非技術客戶。
seo-title: 傳送批次資料至Audience Manager概述
solution: Audience Manager
title: 傳送批次資料至Audience Manager概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Send Batch Data to Audience Manager Overview{#send-batch-data-to-audience-manager-overview}

概述想要將資料從其他系統(離線)帶入Audience Manager的技術和非技術客戶。

## 優勢

<!-- c_offline_to_online.xml -->

您可以從Audience Manager提供的其他系統中建立資料。我們的系統可以幫助您解除鎖定值並運用先前收集到的使用者資料。This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. 雖然每個整合都展現了自己的挑戰，但他們都共用了這些常見步驟。檢閱此項資料有助於減少線上資料在線上傳輸所需的心力。

## 步驟1：同步化使用者ID

同步期間，Audience Manager會將唯一ID指派給客戶及其使用者。These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. 當此步驟完成時，Audience Manager和您的離線儲存庫應包含每個使用者記錄的對應ID。

此步驟的重要考量：

* **用戶端ID位置：** Audience Manager需要知道您的客戶ID在您的網站上顯示的位置(例如，它儲存在Cookie、Analytics變數、頁面程式碼中)。
* **排除[!DNL PII]：** 使用者ID不能包含個人識別資訊([!DNL PII])。
* **案例與內容敏感性：** 在即時資料同步期間，Audience Manager從您的網站擷取的使用者ID必須對應於從離線儲存庫傳入的ID。For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. 因此，此訪客的線上資訊無法與離線資料庫中的對應記錄相關聯。ID必須完全相符。

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

## 步驟2：資料檔案格式

檔案名稱和內容遵循嚴格准則。You *must* name and organize data files according to these specifications in this guide. 請參閱:

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [傳入資料檔案內容：語法、變數和範例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料適用於離線行銷活動

當您在線上提供離線資料時，您仍可使用此資訊來離線促銷活動。To do this, Audience Manager exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. 如需其他資訊或協助，請聯絡您的合作夥伴解決方案經理。

## 環境

Audience Manager提供下列檔案拖放環境：

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
   <td colname="col2"> <p> <code> demdex-s2 s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 進一步技術閱讀

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. 這些文章提供傳輸通訊協定、檔案內容和檔案名稱需求的詳細資訊。