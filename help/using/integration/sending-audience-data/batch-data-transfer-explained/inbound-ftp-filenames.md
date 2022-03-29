---
description: 描述向Audience Manager發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小。 將資料發送到Audience ManagerFTP目錄時，根據這些規範設定檔案的名稱和大小。
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 傳入資料檔案的 FTP 名稱和檔案大小要求
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: 7721083fd538f0b74f72cfc78981e2cc76777790
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 6%

---

# [!DNL FTP]傳入資料檔案的 名稱和檔案大小要求 {#ftp-name-and-file-size-requirements-for-inbound-data-files}

描述向發送資料時需要遵循的必填欄位、語法、命名約定和檔案大小 [!DNL Audience Manager]。 將資料發送到Audience Manager時，根據這些規範設定檔案的名稱和大小 [!DNL FTP] 的子菜單。

>[!WARNING]
>
>我們正在逐步取消對 [!DNL FTP] 配置。 雖然現有資料檔案接收仍支援入站資料檔案接收 [!DNL FTP] 整合，強烈建議使用 [!DNL Amazon S3] 用於新整合的板載離線資料。 如需詳細資訊，請參閱[傳入資料檔案的 Amazon S3 名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法 {#file-name-syntax}

[!DNL FTP] 檔案名包含以下必需和可選元素：

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

有關其他接受的檔案名格式，請參見 [定制合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>[!DNL Audience Manager] 僅進程 [!DNL ASCII] 和 [!DNL UTF-8] 編碼檔案。

### 名稱元素

表定義 [!DNL FTP] 檔案名。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>您的路徑和名稱 <span class="keyword"> Audience Manager</span> FTP目錄。 請聯繫您的客戶經理以獲取FTP目錄和憑據。 </p> </td> 
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
   <td colname="col2"> <p>此欄位將告訴Audience Manager板載資料的資料源。 如果將DPID設定為Android ID或iOSID或屬於全局資料源的其他ID，則此欄位是必需的。 這樣 <span class="keyword"> Audience Manager</span> 將檔案資料連結回您的組織。 <br> 此目標資料源需要歸您的公司所有。 為了實現第二方資料共用，為了將資料插入屬於另一公司的目標資料源，您必須在公司和目標資料源之間具有訪問映射。 請與Adobe顧問或客戶支援聯繫以設定映射。</p><p><b>重要說明：</b> 你 <i>不</i> 需要請求現有資料共用關係的映射（適用於您在2022年3月14日之前將資料放入的其他公司的目標資料源）。 將資料載入到屬於您的PID的目標資料源時，也不需要映射。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告訴Audience Manager您正在為屬於資料源33的客戶ID確認屬於資料源21的特性或信號。 </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含Android ID,ID應符合屬於資料源21的特徵。</li> 
     <li> <b>iOSID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 資料檔案僅包含iOSID,ID應符合屬於資料源21的特徵。</li>
     <li> <b>屬於其他全局資料源的ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> 告 <span class="keyword"> Audience Manager</span> 該資料檔案僅包含Roku ID且ID應符合屬於資料源21的特徵。 使用與每個資料源對應的ID，如 <a href="/help/using/features/global-data-sources.md"> 全局資料源文章</a>。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:正常情形，即第三方資料提供者按用戶基準發送要在Audience Manager系統中添加或刪除的特徵。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:允許客戶和資料提供商按用戶發送一個特徵清單，該清單應覆蓋Audience Manager中給定資料源的此用戶的所有現有特徵。 您不需要將所有用戶都包括在覆蓋檔案中。 僅包括要更改的用戶。 未分配給目標資料源的特性將不會被擦除。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案拆分為多個部件以縮短處理時間時使用。 該數字指示您正在發送的原始檔案的哪個部分。 </p> <p>為了高效處理檔案，請按照以下說明拆分資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">壓縮：200-300 MB </li> 
    </ul> <p>請參閱前2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> 檔案名示例</a> 下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10位UTC UNIX時間戳（秒）。 時間戳有助於使每個檔案名唯一。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip是允許的FTP檔案名壓縮格式。 如果使用檔案壓縮，請確保檔案名具有正確的副檔名。 </p> <p>壓縮檔案必須為3 GB或更小。 如果您的檔案檔案較大，請與客戶服務部聯繫。 儘管Audience Manager可以處理大檔案，但我們可能可以幫助您減小檔案大小，並提高資料傳輸的效率。 請參閱<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">傳入資料傳輸檔案的檔案壓縮</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名示例 {#file-name-examples}

以下示例顯示格式正確的檔案名。 您的檔案名可能看起來類似。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[下載](assets/ftp_dpm_1234_1445374061.overwrite) 示例檔案（如果需要其他示例）。 此檔案與 `.overwrite` 檔案副檔名。 使用簡單的文本編輯器開啟它。

## 接受的檔案大小 {#accepted-file-sizes}

請考慮下圖，瞭解檔案的最快/最早處理，以及將資料發送到 [!DNL Audience Manager] / [!DNL FTP] 的子菜單。

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

>[!MORELIKETHIS]
>
>* [傳入資料檔案的 Amazon S3 名稱要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

