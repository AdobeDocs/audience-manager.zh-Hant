---
description: 說明傳送資料至Audience Manager時需要遵循的必填欄位、語法、命名慣例和檔案大小。當您將資料傳送至Audience Manager/Amazon S目錄時，根據這些規格設定檔案的名稱和大小。
seo-description: 說明傳送資料至Audience Manager時需要遵循的必填欄位、語法、命名慣例和檔案大小。當您將資料傳送至Audience Manager/Amazon S目錄時，根據這些規格設定檔案的名稱和大小。
seo-title: 傳入資料檔案的Amazon S名稱和檔案大小需求
solution: Audience Manager
title: 傳入資料檔案的Amazon S名稱和檔案大小需求
uuid: 3692a122-6ad5-468c-934e-5304bd8cf71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

說明傳送資料至Audience Manager時需要遵循的必填欄位、語法、命名慣例和檔案大小。Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## File Name Syntax {#file-name-syntax}

[!DNL S3] 檔案名稱包含下列必要項目和選擇性元素：

* **[!DNL S3]首碼：**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **檔案名稱元素：**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance=「high」}
>
>[!DNL Audience Manager] 只有流程 [!DNL ASCII] 和 [!DNL UTF-8] 編碼檔案。

### 名稱元素

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>AWS_ directory</i></code> </p> </td> 
   <td colname="col2"> <p>您的Amazon S儲存貯體的路徑和名稱。請洽詢您的帳戶管理員，以瞭解您的S目錄名稱、路徑和認證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>當您將檔案傳送至S儲存貯體時的時間戳記(根據UTC時間)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="term"> 資料提供者ID</span> (DPID)是識別 <span class="keyword"> 資料檔案(</span> 如果資料檔案包含您自己的使用者ID或Android或iOS ID)的識別碼。接受下列選項： </p> <p> <b>資料合作夥伴ID</b> </p> <p>這是唯一的ID Audience Manager指派給您的公司或組織。傳送包含您自己的使用者ID的資料時，請在檔案名稱中使用此指派的ID。For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>Android ID(GAID)</b> </p> <p> 如果檔案包含Android ID，請使用ID20914作為資料檔案名稱的DPID。When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. 例如，假設您要使用Android ID傳入檔案，而您的資料供應商ID則為21。In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>iOS ID(IDFA)</b> </p> <p> 如果檔案包含iOS ID，請使用ID20915作為資料檔案名稱的DPID。When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. 例如，假設您要使用Android ID傳入檔案，而您的資料供應商ID則為21。In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料合作夥伴ID：</b> 這是唯一的ID Audience Manager指派給您的公司或組織。傳送包含您自己的使用者ID的資料時，請在檔案名稱中使用此指派的ID。For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID)：</b> 如果資料檔案名稱包含Android ID，請使用ID20914。For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. 注意，ID21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA)：</b> 如果資料檔案名稱包含iOS ID，請使用ID20915。For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>注意：請勿在您的資料檔案中混合ID類型。例如，如果您的檔案名稱包含Android識別碼，請勿將iOS ID或您自己的ID放入資料檔案中。 </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ ATA_ OMAR</i></code> </p> </td> 
   <td colname="col2"> <p>ID的預留位置。For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>例如: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_33_21_12345678890. sync</code> 顯示ID21的合作夥伴已從使用ID33的資料來源傳送資料。 </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_20914_21_12345678890. sync</code> 顯示ID21的合作夥伴已在包含Android ID的資料中傳送。 </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_20915_21_12345678890. sync</code> 顯示ID21的合作夥伴已在包含iOS ID的資料中傳送。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>時間戳記</i></code> </p> </td> 
   <td colname="col2"> <p>10位數，UTC UNIX時間戳記，秒數。時間戳記可讓每個檔案名稱唯一。 </p> 
    <draft-comment> 
     <p> <p>注意：Audience Manager不會在傳入檔案期間使用時間戳記。在Audience Manager中，檔案名稱中的時間戳記已過時，但仍需要回溯相容性。 </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync|. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> 同步</code>：一般情況：第三方資料供應商根據每位使用者的基礎傳送特性，以便在Audience Manager系統中新增或移除。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> 覆寫</code>：讓資料供應商根據每位使用者來傳送特性清單，該清單應覆寫Audience Manager中此資料提供者的所有現有第三方特性。您不需要將所有使用者包含在覆寫檔案中。只包含您想要變更的使用者。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。當您將大型檔案分割為多個部分以改善處理時間時使用。數字表示您要傳入的原始檔案部分。 </p> <p>如需有效的檔案處理，請依指示分割您的資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">壓縮：200-300MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>將檔案傳送至Amazon S時，只能使用gzip壓縮。When compressed, these files get the <code> .gz</code> extension. 請勿使用.zip壓縮。 </p> <p>壓縮的檔案必須為GB或更小。如果檔案較大，請與客戶服務聯絡。雖然Audience Manager可處理大型檔案，但是我們可以協助您減少檔案大小，並提高資料傳輸效率。See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

下列範例顯示格式正確的檔案名稱。您的檔案名稱看起來可能類似。

<ul class="simplelist"> 
 <li> <code> s3n://&lt; AWS_ Buck&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt; AWS_ Buck&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt; AWS_ Bruct&gt;/&lt; partner_ name&gt;/date=2016-05-09/ftp_ dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt; AWS_ Buck&gt;/&lt; partner_ name&gt;/date= 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt; AWS_ Buck&gt;/&lt; partner_ name&gt;/date=2016-05-09/ftp_ dpm_478_1366545717.overwrite</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. 使用簡單的文字編輯器開啓它。

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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
   <td colname="col1"><b>壓縮壓縮</b> </td> 
   <td colname="col2"> <p>200-300MB </p> </td> 
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
>傳入的資料驗證程序會將空白檔案標示為無效，且不會加以處理。

>[!MORE_贊_ this]
>
>* [傳入資料檔案的 FTP 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

