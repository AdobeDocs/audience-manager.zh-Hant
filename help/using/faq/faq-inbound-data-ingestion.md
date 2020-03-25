---
description: 有關將離線資料匯入Audience Manager的常見問題。
keywords: ftp or s3;s3 or ftp
seo-description: 有關將離線資料匯入Audience Manager的常見問題。
seo-title: 傳入客戶資料擷取常見問答集
solution: Audience Manager
title: 傳入客戶資料擷取常見問答集
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 187874fb5d0c4363f771297766f3c4bc9d967c9b

---


# 傳入客戶資料擷取常見問答集{#inbound-customer-data-ingestion-faq}

有關將離線資料匯入Audience Manager的常見問題。

 

**您可以總結入門程式嗎？**

上線程式包含兩個步驟，如「傳送批次資 [料至Audience Manager概觀」所述](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* 步驟1:同步用戶ID;
* 步驟2:遵循檔案格式要求，建立並傳輸傳入的資料檔案。

 

**您可以總結部署流程嗎？**

我們建議您：

* 與資料提供者合作，根據Adobe規格格式化每日傳入的資料檔案。 如需檔案命名和語法需求，請參閱下列檔案：
   * [ID 同步檔案的名稱和內容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [入站資料檔案內容：語法、無效字元、變數和範例](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [入站資料檔案的Amazon S3名稱和檔案大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* 與您的顧 [!DNL Adobe] 問合作，將測試資料檔案傳輸至格 [!DNL Adobe] 式驗證。
* 請與顧問 [!DNL Adobe] 合作，製作適合於解釋資料檔案內容的分類法。
* 在測試／開發環境中，確認ID同步設定為正確擷取資料提供者的訪客ID，並將其即時傳輸 [!DNL Audience Manager] 至伺服器。
* 將DIL/ID同步部署至生產環境。 您的Adobe顧問已將ID同步設定為DIL程式碼中的模組。
* 將生產資料檔案傳輸至 [!DNL Audience Manager]。 鑑於ID同步對應的相依性，在部署生產程式碼後一週內開始傳輸資料或許是合理的，不過當程式碼投入生產時，您可以立即開始傳輸資料檔案。

 

**我應使用何種FTP模式來傳輸壓縮或加密的檔案？**

請參 [閱傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

>[!WARNING]
>
>我們正逐步淘汰對FTP組態的支援。 雖然現有FTP整合仍支援傳入資料檔案擷取，但強烈建議使用Amazon S3將離線資料載入新整合的線上。 如需詳 [細資訊，請參閱Amazon S3傳入資料檔案的名稱和檔案大小需求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 。

 

**我可以先上傳傳入資料檔案 ([!DNL .sync]或[!DNL .overwrite]檔)，再將[!DNL Audience Manager]程式碼部署到生產環境嗎？**

是。只要您使用跨裝置資料來源來儲存您上傳的CRM資料，Audience Manager就會一律儲存資料。 事實上，在Audience Manager於2019年10月啟動的「設定檔合併規則」增強功能允許離線使用案例後，您無需將Audience Manager程式碼部署至生產環境，即可上傳資料並採取行動。 請參閱:

* [描述檔合併規則增強功能概觀](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* 以人為本的目的地- [基於僅線下資料的個人化](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

**我應該在幾點傳輸我的檔案？**

[!DNL Audience Manager] 一天中多次檢查及處理檔案。 在您準備好時上傳資料。

 

**上傳檔案的資料可用於定位需要多久的時間？**

48小時後，資料可供定位。 此外，請勿將「成功上傳」電子郵件解譯為資料可用的陳述式。 這隻表示已 [!DNL Audience Manager] 擷取檔案並完成處理的第一個步驟。

 

**我應該多久傳送檔案，這些檔案應是完整檔案或增量檔案？**

最佳實務是，為新訪客和資料已變更的訪客每天傳送一次遞增檔案。 許多 [!DNL Audience Manager] 客戶每個月傳送一次完整檔案。 不過，這些檔案間隔和增量是有彈性的。 您應該以漸進方式傳送資料，有時候會對您有意義。

 

**Audience Manager會將我的檔案存放在伺服器上多久？**

FTP檔案在處理後即會移除。 [!DNL S3] 檔案會在30天後移除。 由於格式、語法或其他錯誤而無法處理的檔案會移除。 另請參閱隱私 [與資料保留常見問答](../faq/faq-privacy.md)。

 

**完整檔案和增量檔案之間有何差異？**

* **完整：** 完整檔案會覆寫您所有現有的訪客描述檔，並以檔案中的資料取代這些訪客描述檔。 完整檔案由附加至檔 `.overwrite` 案名稱的標籤識別。 您可以使用檔 `.overwrite` 案重設訪客特徵或移除過時的陳舊過時特徵。

   >[!NOTE]
   >
   >檔案 [!DNL .overwrite] 只會覆寫與此資 [!DNL Audience Manager] 料提供者相關聯的描述檔資料。 換言之，在處理 [!DNL Adobe Analytics] 檔案後，與訪客相關的所有資料 [!DNL .overwrite] 都將保持不變。

* **增量：** 增量檔案會將新資料附加至您現有的訪客資料。 增量檔案由附加到文 `.sync` 件名的標籤標識。 傳入增量檔案並不會清除或覆寫現有的描述檔。

下列使用案例說明這些檔案類型如何影響儲存的訪客描述檔。

| 使用案例 | 說明 |
|---|---|
| 增量和完整 | <ul><li>第1天 `.sync` 檔案內容： `visitor123 = a,b,c`</li><li>第2天 `.overwrite` 檔案內容： `visitor123 = c,d,e`</li><li>第3天訪客資料ID 123內容： `c,d,e`</li></ul> |
| 僅增量 | <ul><li>第1天 `.sync` 檔案內容： `visitor123 = a,b,c`</li><li>第2天 `.sync` 檔案內容： `visitor123 = c,d,e`</li><li>第3天訪客資料ID 123內容： `a,b,c,d,e`</li></ul> |

有關完整和增量檔案類型的詳細資訊，請參閱：

* [傳入資料的Amazon S3名稱和檔案大小需求……](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**如果我為從未執行過頁面ID同步的訪客傳送ID檔案時，會發生什麼情況？**

在處理期 [!DNL Audience Manager] 間，跳過該記錄並移至下一個。 如果 [DPID（資料提供者ID）](../reference/ids-in-aam.md) 設為跨裝置DPID，則儲存在ID同步之前所擷取的資料，並可在ID同步發生後不久使用。

 

**時間戳記是什麼，它是幹什麼的，您能提供一個示例嗎？**

時間戳記用於記錄和記錄保存。 格式正確的傳入檔案名所使用的語法需要這些語法。 請參閱:

* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**什麼是資料提供者ID(DPID)，我要如何取得？**

您的Adobe顧問會為您的特定資料來源指派一位三位數或四位數 [DPID](../reference/ids-in-aam.md) （資料提供者ID）。 此ID是唯一的，不會變更。

 

**每日資料檔案的大小為何？**

請參 [閱傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

 

**Audience Manager是否支援檔案壓縮？**

可以。請參閱:

* [傳入資料傳輸檔案的檔案壓縮](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [傳入資料檔案的 Amazon S3 名稱要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**我的資料源資料庫中的主鍵是電子郵件地址。 這是否被視為個人識別資訊？**

是。[!DNL Audience Manager] 不會將電子郵件地址儲存在其資料庫中。 在開始ID同步之前，應先為訪客指派隨機產生的ID或單向雜湊的電子郵件地址版本。

 

**資料檔案內容區分大小寫嗎？ ID同步如何？**

資料檔案有兩個基本元件：A [!UICONTROL User ID] (請參 [!UICONTROL User ID] 閱 [「定義檔案變數](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)」)和描述檔資料，通常以索引鍵值配對或程式碼的形式。 區 [!UICONTROL User ID] 分大小寫。 一般而言，描述檔或索引鍵值資料不區分大小寫。

 

**我應使用FTP或[!DNL Amazon S3]傳輸檔案？**

我們建議您採用最佳實務， [!DNL Amazon S3] 因為程式更簡單。 [!DNL Audience Manager] 不論傳輸FTP檔 [!DNL S3] 案至何處，如果您將檔案自行放置，程式就會更 [!DNL Amazon S3] 簡化。 此外，客戶同時上傳至FTP會共用FTP的頻寬，因此他們預期上傳速度會變慢。 [!DNL Amazon S3] 也會複製和散布，因此通常比FTP伺服器更安全可靠。 如需詳細資訊，請 [參閱關於Amazon S3](../reference/amazon-s3.md)。

>[!WARNING]
>
>我們正逐步淘汰對FTP組態的支援。 雖然現有FTP整合仍支援傳入資料檔案擷取，但強烈建議使用Amazon S3將離線資料載入新整合的線上。 如需詳 [細資訊，請參閱Amazon S3傳入資料檔案的名稱和檔案大小需求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 。

 

**Audience Manager如何處理傳入檔案？**

[!DNL Audience Manager] 用於 [!DNL Amazon Simple Queue Service (SQS)] 入站資料處理。 以下是其運作方式：

1. [!DNL Audience Manager] 客戶將其傳入資料上傳至儲 [!DNL Amazon S3] 存貯體。
1. 資料進入隊 [!DNL Amazon SQS] 列，等待被處理 [!DNL Audience Manager]。
1. [!DNL Audience Manager] 從隊列中讀取最多119000個條目， [!DNL Amazon SQS] 並將它們分成最多3個批。 每個批次中的檔案都會同時處理。

 

**我需要同時上傳多個檔案。 是否會同時處理檔案？**

這要看情況。 [!DNL Audience Manager] 從隊列中讀取最多119000個條目， [!DNL Amazon SQS] 並將它們分成最多3個批。 只有在檔案最後歸為同一批時，才會同時處理檔案。 但是，由於日常接收的資料量很大， [!DNL Audience Manager] 無法保證任何檔案處理順序。

>[!MORELIKETHIS]
>
>* [批資料傳輸流程說明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

