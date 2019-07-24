---
description: 有關將離線資料帶入Audience Manager的常見問題。
keywords: ftp或s3；s或ftp
seo-description: 有關將離線資料帶入Audience Manager的常見問題。
seo-title: 傳入客戶資料擷取常見問題集
solution: Audience Manager
title: 傳入客戶資料擷取常見問題集
uuid: 491e9ec1-4731-46a8-86e7-d8 c613 e6 cexc
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

有關將離線資料帶入Audience Manager的常見問題。

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**您可以摘要一下入門程序嗎？**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). 這些包括：

* ID同步
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

以下是您在檢閱文件後可能會發現有用的問題和答案清單。

>[!NOTE]
>
>本節中的範例會簡化或縮短，以供簡短和展示用途使用。如需檔案格式和語法的詳細規格，請參閱「內嵌資料擷取」文件。

<br> 

**您可以總結部署程序嗎？**

我們建議您：

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider's visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* 部署DIL/ID同步至生產環境。您的Adobe顧問將會在DIL程式碼中設定ID同步為模組。
* Transfer production data files to [!DNL Audience Manager]. 基於ID同步映射的相依性，在程式碼部署後最多一周內開始傳輸資料或許可行，不過當程式碼進入生產時，您可以立即開始傳輸資料檔案。

<br> 

**我應該使用哪一個FTP模式來傳輸壓縮或加密的檔案？**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**我可以先上傳傳入資料檔案 ([!DNL .sync]或[!DNL .overwrite]檔)，再將[!DNL Audience Manager]程式碼部署到生產環境嗎?**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>案例 1</b> </p> </td> 
   <td colname="col2"> <p>星期一，當訪客ABC登入時，CRM資料庫中發現訪客，會啓動用戶端ID同步。<span class="keyword"> Audience Manager</span> 會儲存訪客ABC至 <span class="keyword"> Audience Manager</span> 訪客123的對應。 </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC「gender」=「mostle」，「volume_ shopper」=「yes」</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">從儲存的ID同步映射識別訪客ABC。 </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>案例 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF「gender」=「girl」，「wine_ pushast」=「yes」</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> 沒有此訪客的記錄(或相關聯的訪客ID)，因此無法處理此記錄。 </p> <p>星期二，訪客DEF登入。此動作會起始該訪客的第一個用戶端ID同步。This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. 但是，此訪客沒有與其描述檔相關聯的CRM資料。As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF」gender」=「girl」，「wine_ pushast」=「yes」，「dma」=「paris」</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">從儲存的ID同步映射識別訪客DEF。 </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>案例3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> . sync</code> 檔案包含： </p> <p> 
     <ul class="simplelist"> 
      <li><code> GI123456789</code> </li> 
     </ul> </p> <p> <code> . overwrite</code> 檔案包含： </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GI「gender」=「gener」「wine_ pushast」=「no」</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JCMS「gender」=「grian」「wine_ pushast」=「yes」</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> 會從先前的ID同步，保留訪客JTW的映射記錄至ID789。 </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">從儲存的ID同步映射識別訪客JTW。 </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">忽略訪客GI的特徵關聯，因為其ID只會同步至目前的批次。To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**我應該在哪一天傳輸我的檔案？**

[!DNL Audience Manager] 檢查並處理檔案多次。當您準備好時，上傳您的資料。

<br> 

**上傳已上載檔案的資料可供定位多久？**

資料可在48小時後進行定位。此外，請勿將「成功上傳」電子郵件解譯為可用資料。This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**我要多久才傳送檔案，這些檔案應該是完整或增量的檔案？**

最好的作法是每天傳送一次遞增檔案給新訪客和資料已變更的訪客。Many [!DNL Audience Manager] customers send a full file once per month. 但是，這些檔案間隔和增量有彈性。您應該適時地傳送資料，並對您有意義。

<br> 

**Audience Manager會將我的檔案保存在伺服器上多久？**

FTP檔案在處理後會被移除。[!DNL S3] 檔案會在30天後移除。無法處理由於格式、語法或其他錯誤而無法處理的檔案。See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**完整和增量檔案之間有何差異？**

* **完整：** 完整檔案會覆寫您所有現有訪客描述檔，並取代檔案中的資料。Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >[!DNL .overwrite] 這些檔案只會覆寫 [!DNL Audience Manager] 與此資料提供者關聯的描述檔資料。In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **漸進式：** 遞增檔案會附加新資料至您現有的訪客個人資料。Incremental files are identified by the `.sync` tag appended to the file name. 傳送遞增檔案並不會擦除或覆寫現有描述檔。

下列使用案例說明這些檔案類型如何影響儲存的訪客描述檔。

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>遞增和完整</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>僅限增量</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415"><code> 第2.同步</code> 檔案內容： <code> visitor123= c，d，e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

如需完整和漸進式檔案類型的詳細資訊，請參閱：

* [傳入資料的Amazon S名稱和檔案大小需求…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**如果我在檔案中傳送從未執行頁面ID同步的訪客，會發生甚麼情況？**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. 如果DPID(資料提供者ID)設定為跨裝置DPID，則在ID同步儲存之前已吸收的資料會儲存，並且可在ID同步發生後立即使用。

<br> 

**時間戳記是甚麼，它適用於甚麼，您可以提供範例嗎？**

時間戳記用於記錄和記錄保留。語法必須是格式正確的傳入檔案名稱所使用的語法。請參閱:

* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**甚麼是資料提供者ID(DPID)，我要如何取得它？**

您的Adobe顧問會為您的特定資料來源指派三位數或四位數的DPID。此ID是唯一的，但不會變更。

<br> 

**每日資料檔案大小？**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Audience Manager支援檔案壓縮嗎？**

可以。請參閱:

* [傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**資料來源資料庫中的主要索引鍵是電子郵件地址。Is that considered personally identifiable information?**

是。[!DNL Audience Manager] 不會將電子郵件地址儲存在我們的資料庫中。在初始化ID同步之前，應先指派隨機ID或單向雜湊版本的電子郵件地址。

<br> 

**資料檔案內容是否區分大小寫？How about the ID sync?**

資料檔案有兩個基本元件：唯一使用者ID(UUID)和描述檔資料(通常是關鍵值配對或代碼的形式)。UUID區分大小寫。一般而言，描述檔或索引鍵值資料不區分大小寫。

<br> 

**我是否應使用FTP或[!DNL Amazon S3]傳輸檔案？**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] 將FTP檔案傳輸至 [!DNL S3] 不受限制，如此當您自行放下檔案時，程序就更為 [!DNL Amazon S3] 簡化。此外，客戶同時上傳至FTP時，FTP的頻寬也會跟著增加，因此預期上傳速度會減慢。[!DNL Amazon S3] 也會複製和散髮，因此比FTP伺服器更安全可靠。For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**Audience Manger如何處理傳入的檔案？**

[!DNL Audience Manager] 用於 [!DNL Amazon Simple Queue Service (SQS)] 傳入資料處理。以下是運作方式：

1. [!DNL Audience Manager] 客戶將傳入的資料上傳 [!DNL Amazon S3] 至貯體。

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] 最多可從 [!DNL Amazon SQS] 佇列讀取119000個項目，並以最多個批次分割。每個批次中的檔案都會同時處理。

<br> 

**我需要同時上載多個檔案。Will the files be processed simultaneously?**

視需要而定。[!DNL Audience Manager] 最多可從 [!DNL Amazon SQS] 佇列讀取119000個項目，並以最多個批次分割。只有當檔案最後出現在同一批次時，才會同時處理。However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_贊_ this]
>
>* [批次資料傳輸程序說明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

