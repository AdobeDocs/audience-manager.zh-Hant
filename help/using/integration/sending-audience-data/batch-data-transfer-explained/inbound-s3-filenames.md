---
description: 描述向Audience Manager發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小。 將資料發送到Audience Manager/AmazonS3目錄時，根據這些規範設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Amazon入站資料檔案的S3名稱和檔案大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: f073dd733b512aa60d7817acbef76e51594900f8
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---

# 入站資料檔案的[!DNL Amazon S3]名稱和檔案大小要求 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

描述向[!DNL Audience Manager]發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小。 將資料發送到[!DNL Audience Manager] / [!DNL Amazon S3]目錄時，根據這些規範設定檔案的名稱和大小。

>[!NOTE]
>
>此文檔中的文本樣式（`monospaced text`、*斜體*、方括弧`[ ]` `( )`等）表示代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法 {#file-name-syntax}

[!DNL S3]檔案名包含以下必需和可選元素：

* **[!DNL S3]前置詞：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **檔案名元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

如需其他接受的檔案名稱格式，請參閱[自訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager]僅處理[!DNL ASCII]和[!DNL UTF-8]編碼的檔案。

### 名稱元素

該表定義[!DNL S3]檔案名中的元素。

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 Bucket的路徑和名稱。 請聯繫您的客戶經理，瞭解S3目錄名稱、路徑和憑據。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>傳送檔案至S3儲存貯體的時間戳記（根據UTC時間）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword"> Audience Manager</span>資料檔案是否包含您自己的使用者ID、Android ID、iOS ID或其他屬於<a href="/help/using/features/global-data-sources.md">全域資料來源</a>的ID的lD。 接受下列選項：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料Source識別碼（也稱為資料提供者識別碼）：</b>這是Audience Manager指派給資料來源的唯一ID （請參閱ID <a href="/help/using/reference/ids-in-aam.md">的Audience Manager </a>索引）。 在發送包含您自己的用戶ID的資料時，請在檔案名中使用此分配的ID。 例如，<code>...ftp_dpm_21_123456789.sync</code>將<span class="keyword">Audience Manager</span>告知板載資料為屬於資料源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b>如果包含Android ID，請在資料檔案名中使用ID 20914。 使用Android ID時，需要使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code>告訴<span class="keyword">Audience Manager</span>，資料檔案僅包含Android ID,ID應符合屬於<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料源的特徵。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOSID(IDFA):</b>如果包含iOSID，請在資料檔案名中使用ID 20915。 使用iOSID時，需要使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code>告訴<span class="keyword">Audience Manager</span>，資料檔案僅包含iOSID,ID應符合屬於<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料源的特徵。</li>
     <li> <b>屬於其他全局資料源的ID</b>：您可以在Roku ID上安裝廣告(RIDA)、Microsoft廣告ID(MAID)和其他ID。 使用與每個資料源對應的ID，如<a href="/help/using/features/global-data-sources.md">全局資料源項目</a>中所述。</li> 
    </ul> <p> <p>注意：不要在資料檔案中混合ID類型。 例如，如果您的檔案名包括Android標識符，則不要將iOSID或您自己的ID放入資料檔案中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位將告訴Audience Manager板載資料的資料源。 如果將DPID設定為Android ID或iOSID或屬於全局資料源的其他ID，則此欄位是必需的。 這樣，Audience Manager就可以將檔案資料連結回您的組織。 <br>此目標資料源需要歸您的公司所有。 為了實現第二方資料共用，為了將資料插入屬於另一公司的目標資料源，您必須在公司和目標資料源之間具有訪問映射。 請聯絡您的Adobe顧問或客戶支援，以設定對應。</p> <p><b>重要注意事項：</b>您<i>不</i>需要為現有的資料共用關係請求對應（針對屬於您於2022年3月14日之前將資料上線的其他公司的目標資料來源）。 將資料上線至屬於您的PID的目標資料來源時，也不一定需要對應。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code>告知Audience Manager您正在為屬於資料源33的客戶ID資格，以獲取屬於資料源21的特徵或信號。 </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code>告知<span class="keyword">Audience Manager</span>，資料檔案僅包含Android ID,ID應符合屬於資料源21的特徵。</li> 
     <li> <b>iOSID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code>告知<span class="keyword">Audience Manager</span>資料檔案僅包含iOSID,ID應符合屬於資料源21的特徵。</li>
     <li> 屬於其他全域資料來源的<b>ID</b>： <code>...ftp_dpm_121963_21_1234567890.sync</code>會告訴<span class="keyword"> Audience Manager</span>，資料檔案僅包含Roku ID，而且這些ID應該符合屬於資料來源21的特徵。 使用對應至每個資料來源的ID，如<a href="/help/using/features/global-data-sources.md">全域資料來源文章</a>所述。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在<span class="keyword"> Audience Manager</span>中使用的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>以秒為單位的10位數UTC UNIX時間戳記。 時間戳記有助於讓每個檔案名稱是唯一的。 </p> 
    <!--
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    -->
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>：第三方資料提供程式按每個用戶發送要在Audience Manager系統中添加或刪除的特徵時的正常情況。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>：允許資料提供程式按每個用戶發送一個特性清單，該清單應覆蓋該Audience Manager中此資料提供程式的此用戶的所有現有第三方特性。 您不需要將所有用戶都包括在覆蓋檔案中。 僅包括要更改的用戶。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案拆分為多個部件以縮短處理時間時使用。 該數字指示您正在發送的原始檔案的哪個部分。 </p> <p>為了高效處理檔案，請按照以下說明拆分資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">已壓縮：200-300 MB </li> 
    </ul> <p>請參閱下面的前2個<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples">檔案名示例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>將檔案發送到AmazonS3時，僅使用gzip壓縮。 壓縮後，這些檔案將獲取<code> .gz</code>副檔名。 不要使用.zip壓縮。 </p> <p>壓縮檔案必須為3 GB或更小。 如果您的檔案較大，請洽詢客戶服務。 儘管Audience Manager可以處理大檔案，但我們可能可以幫助您減小檔案大小，並使資料傳輸更加高效。 請參閱傳入資料傳輸檔案的<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">檔案壓縮</a>。 </p> </td> 
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

如果需要其他示例，可以[下載](assets/ftp_dpm_1234_1445374061.overwrite)示例檔案。 此檔案已用`.overwrite`檔案副檔名保存。 使用簡單的文本編輯器開啟它。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，瞭解檔案的最快/最早處理以及將資料發送到[!DNL Audience Manager] / [!DNL Amazon S3]目錄時的檔案大小限制。

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案類型 </th> 
   <th colname="col2" class="entry"> 最佳大小 </th> 
   <th colname="col3" class="entry"> 最大大小 </th> 
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

## 行長限制 {#line-limits}

入站資料檔案的行長限制為102400位元組。 超過此限制的行將從轉移中排除。

>[!MORELIKETHIS]
>
>* [傳入資料檔案的 FTP 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
