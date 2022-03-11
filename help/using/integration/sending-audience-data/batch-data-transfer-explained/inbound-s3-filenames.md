---
description: 描述向Audience Manager發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小。 將資料發送到Audience Manager/AmazonS3目錄時，根據這些規範設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 傳入資料檔案的 Amazon S3 名稱和檔案大小要求
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: 3e25db0fc74a0b125f4f0ecd0f45f3fb877be099
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 4%

---

# [!DNL Amazon S3] 入站資料檔案的名稱和檔案大小要求 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

描述向發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小 [!DNL Audience Manager]。 在將資料發送到 [!DNL Audience Manager] / [!DNL Amazon S3] 的子菜單。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法 {#file-name-syntax}

[!DNL S3] 檔案名包含以下必需和可選元素：

* **[!DNL S3]前置詞：**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **檔案名元素：**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有關其他接受的檔案名格式，請參見 [定制合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] 僅進程 [!DNL ASCII] 和 [!DNL UTF-8] 編碼檔案。

### 名稱元素

表定義 [!DNL S3] 檔案名。

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
   <td colname="col2"> <p>AmazonS3儲存桶的路徑和名稱。 請聯繫您的客戶經理，瞭解S3目錄名稱、路徑和憑據。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>將檔案發送到S3儲存段時的時間戳（基於UTC時間）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>一個LD <span class="keyword"> Audience Manager</span> 如果資料檔案包含您自己的用戶ID、Android ID、iOSID或屬於 <a href="/help/using/features/global-data-sources.md"> 全局資料源</a>。 接受以下選項：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料源ID（也稱為資料提供程式ID）:</b> 這是Audience Manager分配給資料源的唯一ID(請參閱Audience Manager <a href="/help/using/reference/ids-in-aam.md"> ID的索引 </a>)。 在發送包含您自己的用戶ID的資料時，請在檔案名中使用此分配的ID。 比如說， <code>...ftp_dpm_21_123456789.sync</code> 告 <span class="keyword"> Audience Manager</span> 到屬於資料源21的ID的板載資料。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> 如果資料檔案名中包含Android ID，請使用ID 20914。 您需要使用該欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 使用Android ID時。 比如說， <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID且ID應符合屬於 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料源。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOSID(IDFA):</b> 如果資料檔案名中包含iOSID，請使用ID 20915。 您需要使用該欄位 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 用iOS身份證。 比如說， <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOSID，且ID應符合屬於 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 資料源。</li>
     <li> <b>屬於其他全局資料源的ID</b>:您可以在Roku ID上安裝廣告RIDA、Microsoft廣告ID(MAID)和其他ID。 使用與每個資料源對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全局資料源文章</a>。</li> 
    </ul> <p> <p>注：不要在資料檔案中混合使用ID類型。 例如，如果您的檔案名包括Android標識符，則不要將iOSID或您自己的ID放入資料檔案中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位將告訴Audience Manager板載資料的資料源。 如果將DPID設定為Android ID或iOSID或屬於全局資料源的其他ID，則此欄位是必需的。 這樣，Audience Manager就可以將檔案資料連結回您的組織。 <br> 此目標資料源需要歸您的公司所有。 為了實現第二方資料共用，為了將資料插入屬於另一公司的目標資料源，您必須在公司和目標資料源之間具有訪問映射。 請與Adobe顧問或客戶支援聯繫以設定映射。</p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告訴Audience Manager您正在為屬於資料源33的客戶ID確認屬於資料源21的特性或信號。 </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID,ID應符合屬於資料源21的特徵。</li> 
     <li> <b>iOSID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOSID,ID應符合屬於資料源21的特徵。</li>
     <li> <b>屬於其他全局資料源的ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 該資料檔案僅包含Roku ID且ID應符合屬於資料源21的特徵。 使用與每個資料源對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全局資料源文章</a>。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>您在中使用的公司或組織名稱 <span class="keyword"> Audience Manager</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10位UTC UNIX時間戳（秒）。 時間戳有助於使每個檔案名唯一。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:正常情形，即第三方資料提供者按用戶基準發送要在Audience Manager系統中添加或刪除的特徵。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:允許資料提供程式按每個用戶發送一個特徵清單，該清單應覆蓋該Audience Manager中此資料提供程式的此用戶的所有現有第三方特徵。 您不需要將所有用戶都包括在覆蓋檔案中。 僅包括要更改的用戶。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案拆分為多個部件以縮短處理時間時使用。 該數字指示您正在發送的原始檔案的哪個部分。 </p> <p>為了高效處理檔案，請按照以下說明拆分資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">壓縮：200-300 MB </li> 
    </ul> <p>請參閱前2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> 檔案名示例</a> 下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>將檔案發送到AmazonS3時，僅使用gzip壓縮。 壓縮後，這些檔案 <code> .gz</code> 擴展。 不要使用.zip壓縮。 </p> <p>壓縮檔案必須為3 GB或更小。 如果您的檔案較大，請與客戶服務部聯繫。 儘管Audience Manager可以處理大檔案，但我們可能可以幫助您減小檔案大小，並提高資料傳輸的效率。 請參閱<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">傳入資料傳輸檔案的檔案壓縮</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名示例 {#file-name-examples}

以下示例顯示格式正確的檔案名。 您的檔案名可能看起來類似。

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

你可以 [下載](assets/ftp_dpm_1234_1445374061.overwrite) 示例檔案。 此檔案已與 `.overwrite` 檔案副檔名。 使用簡單的文本編輯器開啟它。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，瞭解檔案的最快/最早處理，以及將資料發送到 [!DNL Audience Manager] / [!DNL Amazon S3] 的子菜單。

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
   <td colname="col1"><b>壓縮</b> </td> 
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
>入站資料驗證進程會將空檔案標籤為無效，並且不會處理它們。

## 行長限制 {#line-limits}

入站資料檔案的行長度限制為102400位元組。 超過此限制的行將從轉移中排除。

>[!MORELIKETHIS]
>
>* [傳入資料檔案的 FTP 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

