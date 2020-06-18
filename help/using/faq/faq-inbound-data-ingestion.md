---
description: 將離線資料匯入 Audience Manager 的常見問題集。
keywords: ftp or s3;s3 or ftp
seo-description: 將離線資料匯入 Audience Manager 的常見問題集。
seo-title: 傳入客戶資料擷取常見問題集
solution: Audience Manager
title: 傳入客戶資料擷取常見問題集
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 91%

---


# 傳入客戶資料擷取常見問題集{#inbound-customer-data-ingestion-faq}

將離線資料匯入 Audience Manager 的常見問題集。

 

**您可以概要說明上線流程嗎？**

如[將批次資料傳送至 Audience Manager 概述](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)所述，上線流程包含兩個步驟：

* 步驟1：同步使用者 ID；
* 步驟 2：遵循檔案格式要求，建立並傳輸傳入資料檔案。

 

**您可以概要說明部署流程嗎？**

我們建議以下事項：

* 與資料提供者合作，根據 Adobe 規格將每日傳入資料檔案格式化。如需檔案命名和語法要求，請參閱下列文件：
   * [ID 同步檔案的名稱和內容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [傳入資料檔案內容：語法、無效字元、變數和範例](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [傳入資料檔案的 Amazon S3 名稱和檔案大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* 請與您的 [!DNL Adobe] 顧問合作，將測試資料檔案傳輸至 [!DNL Adobe] 進行格式驗證。
* 請與您的 [!DNL Adobe] 顧問合作，製作適合解讀資料檔案內容的分類法。
* 在中繼/開發環境中，確認 ID 同步已設定為正確擷取資料提供者的訪客 ID，並將其即時傳輸 [!DNL Audience Manager] 至伺服器。
* 將 DIL/ID 同步部署至生產環境。屆時您的 Adobe 顧問已將 ID 同步設定為 DIL 程式碼中的模組。
* 將生產資料檔案傳輸至 [!DNL Audience Manager]。雖然您可在程式碼投入生產時立即開始傳輸資料檔案，但考慮到 ID 同步對應的相依性，在部署生產程式碼後最多一週內開始傳輸資料是合理的作法。

 

**我應使用何種 FTP 模式來傳輸壓縮或加密的檔案？**

請參閱[傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

>[!WARNING]
>
>我們正逐步淘汰對 FTP 組態的支援。雖然現有 FTP 整合仍支援傳入資料檔案擷取，但強烈建議使用 Amazon S3 將離線資料上線以進行新整合。如需詳細資訊，請參閱[傳入資料檔案的 Amazon S3 名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

 

**我可以先上傳傳入資料檔案 ([!DNL .sync]或[!DNL .overwrite]檔)，再將[!DNL Audience Manager]程式碼部署到生產環境嗎？**

是。As long as you use a [!UICONTROL cross-device data source] to store the CRM data that you upload, Audience Manager always stores the data. In fact, following the [!UICONTROL Profile Merge Rules] enhancements that Audience Manager launched in October 2019 that allow for offline-only use cases, you can upload and action on data without deploying Audience Manager code into production at all. 請參閱：

* [設定檔合併規則增強功能概述](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] -根 [據僅離線資料個人化](https://docs.adobe.com/content/help/zh-Hant/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.translate.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**我應該在幾點傳輸檔案？**

[!DNL Audience Manager] 一整天會多次檢查及處理檔案。您只要準備好便可隨時上傳資料。

 

**已上傳檔案中的資料需過多久才可用於目標定位？**

48 小時後資料可用於目標定位。此外，請勿將「成功上傳」電子郵件看待為資料可供使用的聲明。這只表示 [!DNL Audience Manager] 已擷取檔案並完成處理程序的第一個步驟。

 

**我應多久傳送一次檔案？這些檔案應是完整檔案還是增量檔案？**

最佳實務是每天為新訪客和資料有所變更的訪客傳送一次增量檔案。許多 [!DNL Audience Manager] 客戶每個月會傳送一次完整檔案。不過這些檔案間隔和增量內容是有彈性的。您應以增量方式傳送資料，並在您認為有意義時傳送。

 

**Audience Manager 會將我的檔案保存在伺服器上多久？**

FTP 檔案一經處理便會隨即移除。[!DNL S3] 檔案會在 30 天後移除。由於格式、語法或其他錯誤而無法處理的檔案會遭移除。另請參閱[隱私權與資料保留常見問題集](../faq/faq-privacy.md)。

 

**完整檔案和增量檔案有何差異？**

* **完整：**&#x200B;完整檔案會覆寫您所有現有的訪客設定檔，並以該檔案中的資料取代這些設定檔中的資料。識別完整檔案的方式為附加至檔案名稱的 `.overwrite` 標籤。您可以使用 `.overwrite` 檔案重設訪客特徵或移除過時的淘汰特徵。

   >[!NOTE]
   >
   >[!DNL .overwrite] 檔案只會覆寫與此資料提供者相關聯的 [!DNL Audience Manager] 設定檔資料。換言之，處理 [!DNL .overwrite] 檔案後，與訪客相關聯的所有 [!DNL Audience Manager] 資料都會保持不變。

* **增量：**&#x200B;增量檔案會將新資料附加至您現有的訪客設定檔中。識別增量檔案的方式為附加至檔案名稱的 `.sync` 標籤。傳入增量檔案並不會清除或覆寫現有的設定檔。

下列使用案例說明這些檔案類型對儲存的訪客設定檔有何影響。

| 使用案例 | 說明 |
|---|---|
| 增量和完整 | <ul><li>第 1 天 `.sync` 檔案內容：`visitor123 = a,b,c`</li><li>第 2 天 `.overwrite` 檔案內容：`visitor123 = c,d,e`</li><li>第 3 天訪客設定檔 ID 123 內容：`c,d,e`</li></ul> |
| 僅使用增量 | <ul><li>第 1 天 `.sync` 檔案內容：`visitor123 = a,b,c`</li><li>第 2 天 `.sync` 檔案內容：`visitor123 = c,d,e`</li><li>第 3 天訪客設定檔 ID 123 內容：`a,b,c,d,e`</li></ul> |

有關完整和增量檔案類型的詳細資訊，請參閱：

* [傳入資料檔案的 Amazon S3 名稱和檔案大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**如果傳送的檔案中含有從未執行過頁面 ID 同步的訪客之 ID，會發生什麼情況？**

處理期間，[!DNL Audience Manager] 會跳過該筆記錄並繼續處理下一個。如果將 [DPID (資料提供者 ID)](../reference/ids-in-aam.md) 設為跨裝置 DPID，系統便會儲存進行 ID 同步之前擷取的資料，且 ID 同步發生後不久即可供使用。

 

**時間戳記是什麼？用途為何？可以提供範例嗎？**

時間戳記用於記錄和保存記錄。格式正確的傳入檔案名稱所使用的語法需要時間戳記。請參閱：

* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**什麼是[!DNL Data Provider ID (DPID)]a，我要如何取得？**

Adobe 顧問會為您的特定資料來源指派一個三位數或四位數的 [DPID (資料提供者 ID)](../reference/ids-in-aam.md)。此 ID 不重複且不會變更。

 

**每日資料檔案的大小為何？**

請參閱[傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

 

**Audience Manager 是否支援檔案壓縮？**

是。請參閱：

* [傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**我資料來源資料庫中的主索引鍵是電子郵件地址。這是否會視為個人識別資訊？**

是。[!DNL Audience Manager] 不會將電子郵件地址儲存在其資料庫中。在啟動ID同步之前，應先為訪客指派隨機產生的ID或單向雜湊的電子郵件地址版本。

 

**資料檔案內容是否會區分大小寫？ID 同步是否區分大小寫？**

資料檔案有兩個基本元件：[!UICONTROL User ID] (請參閱[已定義的檔案變數](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)中的 [!UICONTROL User ID]) 和設定檔資料，其形式通常為索引鍵值配對或程式碼。[!UICONTROL User ID] 區分大小寫。一般而言，設定檔或索引鍵值資料不區分大小寫。

 

**我應使用 FTP 或[!DNL Amazon S3]傳輸檔案？**

根據最佳實務，建議您使用 [!DNL Amazon S3]，因為其流程較簡單。無論如何 [!DNL Audience Manager] 都會將 FTP 檔案傳輸至 [!DNL S3]，如果您自行將檔案放置到 [!DNL Amazon S3] 上，流程就會更簡化。此外，同時上傳至 FTP 的客戶會共用 FTP 的頻寬，因此預期的上傳速度較慢。系統也會複製和分配 [!DNL Amazon S3]，因此通常比 FTP 伺服器更安全可靠。如需詳細資訊，請參閱[關於 Amazon S3](../reference/amazon-s3.md)。

>[!WARNING]
>
>我們正逐步淘汰對 FTP 組態的支援。While inbound data file ingestion is still supported in existing FTP integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. 如需詳細資訊，請參閱[傳入資料檔案的 Amazon S3 名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

 

**Audience Manager 如何處理傳入檔案？**

[!DNL Audience Manager] 會使用 [!DNL Amazon Simple Queue Service (SQS)] 來處理傳入資料。以下是其運作方式：

1. [!DNL Audience Manager] 客戶將其傳入資料上傳至 [!DNL Amazon S3] 貯體。
1. 資料排入 [!DNL Amazon SQS] 佇列，等待 [!DNL Audience Manager] 處理。
1. [!DNL Audience Manager] 會從 [!DNL Amazon SQS] 佇列中讀取最多 119000 個項目，並將其分為最多 3 個批次。系統會同時處理每個批次中的檔案。

 

**我需要同時上傳多個檔案。系統是否會同時處理這些檔案？**

視情況而定。[!DNL Audience Manager] 會從 [!DNL Amazon SQS] 佇列中讀取最多 119000 個項目，並將其分為最多 3 個批次。只有當您的檔案最後歸入同一個批次時，系統才會同時處理這些檔案。但是由於 [!DNL Audience Manager] 每天擷取的資料量極大，因此無法保證任何檔案處理順序。

>[!MORELIKETHIS]
>
>* [批次資料傳輸流程說明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

