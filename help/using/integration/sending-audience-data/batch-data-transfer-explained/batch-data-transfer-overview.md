---
description: 技術客戶和非技術客戶，若想將其他系統（離線）的資料帶入Audience Manager，此概觀適用。
keywords: 傳入，批次，批次上傳，批次資料
seo-description: 技術客戶和非技術客戶，若想將其他系統（離線）的資料帶入Audience Manager，此概觀適用。 若要這麼做，請在Audience Manager中使用批次上傳選項。
seo-title: 將批次資料傳送至 Audience Manager 概述
solution: Audience Manager
title: 將批次資料傳送至 Audience Manager 概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: 傳入資料傳輸
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 將批資料發送到[!DNL Audience Manager]概述{#send-batch-data-to-audience-manager-overview}

技術客戶和非技術客戶，若想將其他系統（離線）的資料帶入[!DNL Audience Manager]，請參閱概述。

## 優勢

您可以在[!DNL Audience Manager]中使其他系統的資料可用。 我們的系統可協助您解鎖價值，並運用您先前收集的使用者資料。 這包括購買、客戶調查、註冊資料、[!DNL CRM]資料庫等相關資訊。 雖然每項整合都帶來各自的挑戰，但它們都有共同的步驟。 請檢閱此資料，協助您減少線上離線資料所需的工作量。

## 步驟1:同步用戶ID

在同步期間，[!DNL Audience Manager]會為用戶端及其使用者指派唯一ID。 這些ID分別稱為[!UICONTROL Data Provider ID]([!UICONTROL DPID])和[!UICONTROL Unique User ID]([!UICONTROL UUID])。 [!DNL Audience Manager] 使用 [!UICONTROL DPID] 和來 [!UICONTROL UUID] 識別使用者，並讓他們符合 [!UICONTROL traits]、 [!UICONTROL segments]、對象群組和報表的資格。此外，我們的資料收集代碼([!UICONTROL DIL])會尋找這些ID，以從您的網站擷取訪客資料。 完成此步驟後，[!DNL Audience Manager]和您的離線存放庫應包含每個使用者記錄的對應ID。

有關此步驟的重要考量事項：

* **用戶端ID位置：** [!DNL Audience Manager] 需要知道用戶端ID在您網站上的顯示位置（例如，該ID儲存在Cookie、Analytics變數、頁面程式碼等中）。
* **排除 [!DNL PII]:** 使用者ID不得包含個人識別資訊([!DNL PII])。
* **區分大小寫和內容區分：** 在即時資料同步期間，依從您網站擷取的使用者ID必 [!DNL Audience Manager] 須對應到從離線存放庫傳入的ID。例如，如果離線記錄含有[!DNL User123]的相關資訊，但您的網站將該ID轉譯為[!DNL USER123]，則[!DNL Audience Manager]會將這些ID視為不同的訪客。 因此，此訪客的線上資訊無法與離線資料庫中的對應記錄相關聯。 ID必須完全相符。

請參閱傳入資料傳輸的[ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)。

## 步驟2:資料檔案格式

檔案名稱和內容遵循嚴格的准則。 您&#x200B;*必須*&#x200B;命名，並根據本指南中的這些規範組織資料檔案。 請參閱：

* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [傳入資料檔案內容：語法、變數和範例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 線上資料可用於離線行銷工作

當您將離線資料上線時，您仍可將此資訊用於離線促銷活動。 若要這麼做，[!DNL Audience Manager]會將特徵和區段資訊匯出至您選擇的[!DNL FTP]或[!DNL Amazon S3]位置。 如需詳細資訊或協助，請連絡您的合作夥伴解決方案經理。

## 環境

[!DNL Audience Manager] 為檔案下拉式清單提供下列環境：

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

## 進一步技術閱讀

系統工程師、開發人員或技術/實作團隊應檢閱[說明的批次資料傳輸程式](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)以及本節中的其他文章。 這些文章提供傳輸通訊協定、檔案內容和檔案名稱要求的詳細資訊。
