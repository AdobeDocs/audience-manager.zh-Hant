---
description: 說明將資料傳送至Audience Manager時，必須遵循的欄位、語法、命名慣例和檔案大小。 將資料傳送至Audience Manager/Amazon S3目錄時，請依照這些規格設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 傳入資料檔案的Amazon S3名稱和檔案大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---

# 傳入資料檔案的[!DNL Amazon S3]名稱和檔案大小要求 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

說明將資料傳送至[!DNL Audience Manager]時，必須遵循的欄位、語法、命名慣例和檔案大小。 當您傳送資料至[!DNL Audience Manager] / [!DNL Amazon S3]目錄時，請依照這些規格設定檔案的名稱和大小。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)檔案中會指示程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名稱語法 {#file-name-syntax}

[!DNL S3]檔案名稱包含下列必要和選用元素：

* **[!DNL S3]首碼：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **檔案名稱元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

如需其他接受的檔案名稱格式，請參閱[自訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager]僅處理[!DNL ASCII]和[!DNL UTF-8]編碼的檔案。

### 名稱元素

表格定義了[!DNL S3]檔案名稱中的專案。

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 為元素命名 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 Bucket的路徑和名稱。 請連絡您的帳戶管理員，取得您的S3目錄名稱、路徑和認證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>傳送檔案至S3儲存貯體的時間戳記（根據UTC時間）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>資料檔是否包含您自己的使用者ID、Android ID、iOS ID或其他屬於<a href="/help/using/features/global-data-sources.md">全域資料來源</a>的ID的lD。 接受下列選項：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料Source識別碼（也稱為資料提供者識別碼）：</b>這是Audience Manager指派給資料來源的唯一ID (請參閱ID </a>的Audience Manager<a href="/help/using/reference/ids-in-aam.md">索引)。 在傳送包含您自己的使用者ID的資料時，在檔案名稱中使用此指派ID。 例如，<code>...ftp_dpm_21_123456789.sync</code>告訴<span class="keyword">Audience Manager</span>將資料上線到屬於資料來源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID)：</b>如果資料檔名稱包含Android ID，請使用ID 20914。 使用Android ID時，您需要使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code>會通知<span class="keyword">Audience Manager</span>，資料檔案僅包含Android ID，且這些ID應符合屬於<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料來源的特徵。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA)：</b>如果資料檔名稱包含iOS ID，請使用ID 20915。 使用iOS ID時，您需要使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code>會通知<span class="keyword">Audience Manager</span>，資料檔案僅包含iOS ID，且這些ID應符合屬於<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料來源的特徵。</li>
     <li> <b>屬於其他全域資料來源的ID</b>：您可以將Roku ID加入Advertising (RIDA)、Microsoft Advertising ID (MAID)和其他ID。 使用對應至每個資料來源的ID，如<a href="/help/using/features/global-data-sources.md">全域資料來源文章</a>所述。</li> 
    </ul> <p> <p>注意：請勿在資料檔案中混合使用ID型別。 例如，如果您的檔案名稱包含Android識別碼，請勿在資料檔案中放入iOS ID或您自己的ID。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位會告知Audience Manager要將資料上線到的資料來源。 如果您將DPID設為Android ID、iOS ID或其他屬於全域資料來源的ID，則此欄位為必填欄位。 這可讓Audience Manager將檔案資料連結回您的組織。 <br>此目標資料來源必須由您的公司擁有。 針對第二方資料共用目的，若要將資料擷取至屬於其他公司的目標資料來源，您的公司與目標資料來源之間必須具有存取對應。 請聯絡您的Adobe顧問或客戶支援，以設定對應。</p> <p><b>重要注意事項：</b>您<i>不</i>需要為現有的資料共用關係請求對應（針對屬於您於2022年3月14日之前將資料上線的其他公司的目標資料來源）。 將資料上線至屬於您的PID的目標資料來源時，也不一定需要對應。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code>告訴Audience Manager，您正在將資料來源33的客戶ID限定為資料來源21的特徵或訊號。 </li> 
     <li> <b>Android ID (GAID)：</b> <code>...ftp_dpm_20914_21_1234567890.sync</code>會通知<span class="keyword">Audience Manager</span>，資料檔案僅包含Android ID，且這些ID應符合資料來源21所屬的特徵。</li> 
     <li> <b>iOS ID (IDFA)：</b> <code>...ftp_dpm_20915_21_1234567890.sync</code>會通知<span class="keyword">Audience Manager</span>，資料檔案僅包含iOS ID，且這些ID應符合資料來源21所屬的特徵。</li>
     <li> 屬於其他全域資料來源的<b>ID</b>： <code>...ftp_dpm_121963_21_1234567890.sync</code>會告訴<span class="keyword">Audience Manager</span>，資料檔案僅包含Roku ID，而且這些ID應該符合屬於資料來源21的特徵。 使用對應至每個資料來源的ID，如<a href="/help/using/features/global-data-sources.md">全域資料來源文章</a>所述。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在<span class="keyword">Audience Manager</span>中使用的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>以秒為單位的10位數UTC UNIX時間戳記。 時間戳記有助於讓每個檔案名稱是唯一的。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：第三方資料提供者傳送要新增或移除到Audience Manager系統中的特徵給每個使用者時的正常案例。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：讓資料提供者傳送每個使用者的特徵清單，這些特徵清單應會覆寫Audience Manager中此資料提供者的所有現有第三方特徵。 您不需要在覆寫檔案中加入所有使用者。 僅包含您要變更的使用者。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 當您將大型檔案分割成多個零件以縮短處理時間時使用。 數字表示您傳入原始檔案的哪個部分。 </p> <p>為有效率地處理檔案，請依照以下指示分割您的資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">已壓縮：200-300 MB </li> 
    </ul> <p>請參閱下列前2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples">個檔案名稱範例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>將檔案傳送至Amazon S3時，請僅使用gzip壓縮。 壓縮後，這些檔案會取得<code> .gz</code>副檔名。 請勿使用.zip壓縮。 </p> <p>壓縮的檔案必須等於或小於3 GB。 如果您的檔案較大，請洽詢客戶服務。 雖然Audience Manager可以處理大型檔案，但我們或許可以協助您縮減檔案大小，並提高資料傳輸效率。 請參閱傳入資料傳輸檔案的<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">檔案壓縮</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名稱範例 {#file-name-examples}

下列範例顯示格式正確的檔案名稱。 您的檔案名稱可能類似。

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

如果您需要其他範例，可以[下載](assets/ftp_dpm_1234_1445374061.overwrite)範例檔案。 此檔案已以`.overwrite`副檔名儲存。 使用簡單的文字編輯器將其開啟。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，以瞭解處理檔案的速度最快/最早，以及傳送資料至[!DNL Audience Manager] / [!DNL Amazon S3]目錄時的檔案大小限制。

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案類型 </th> 
   <th colname="col2" class="entry"> 最佳大小 </th> 
   <th colname="col3" class="entry"> 大小上限 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>已壓縮</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>未壓縮</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>


>[!NOTE]
>
>傳入資料驗證程式會將空白檔案標籤為無效，且不會處理這些檔案。

## 行長度限制 {#line-limits}

傳入資料檔案的行長度限製為102400個位元組。 超出此限制的行會從傳輸中排除。

>[!MORELIKETHIS]
>
>* [傳入資料檔案的 FTP 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
