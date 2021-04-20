---
description: 說明傳送資料至Audience Manager時，您需要遵循的必填欄位、語法、命名慣例和檔案大小。 將資料傳送至Audience ManagerFTP目錄時，請根據這些規格來設定檔案的名稱和大小。
seo-description: 說明傳送資料至Audience Manager時，您需要遵循的必填欄位、語法、命名慣例和檔案大小。 將資料傳送至Audience ManagerFTP目錄時，請根據這些規格來設定檔案的名稱和大小。
seo-title: 傳入資料檔案的 FTP 名稱和檔案大小要求
solution: Audience Manager
title: 傳入資料檔案的 FTP 名稱和檔案大小要求
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 8%

---

# [!DNL FTP]傳入資料檔案的 名稱和檔案大小要求{#ftp-name-and-file-size-requirements-for-inbound-data-files}

說明將資料傳送至[!DNL Audience Manager]時，您需遵循的必填欄位、語法、命名慣例和檔案大小。 將資料發送到[!DNL FTP]Audience Manager目錄時，請根據這些規範設定檔案的名稱和大小。

>[!WARNING]
>
>我們正在逐步淘汰對[!DNL FTP]配置的支援。 雖然現有[!DNL FTP]整合仍支援傳入資料檔案擷取，但強烈建議使用[!DNL Amazon S3]來載入新整合的離線資料。 如需詳細資訊，請參閱[傳入資料檔案的 Amazon S3 名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法{#file-name-syntax}

[!DNL FTP] 檔案名稱包含下列必要和選用元素：

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

如需其他接受的檔案名稱格式，請參閱[自訂合作夥伴整合](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>[!DNL Audience Manager] 僅處理 [!DNL ASCII] 和編 [!DNL UTF-8] 碼檔案。

### 命名元素

該表定義了[!DNL FTP]檔案名中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> FTP目錄的路徑和名稱。 請連絡您的帳戶管理員以取得FTP目錄和認證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>此lD會告訴<span class="keyword">Audience Manager</span>資料檔案是否包含您自己的使用者ID、Android ID、iOS ID或屬於<a href="/help/using/features/global-data-sources.md">全域資料來源</a>的其他ID。 接受下列選項：</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>資料來源ID（也稱為資料提供者ID）:</b> 這是Audience Manager指派給資料來源的唯一ID(請參 <a href="/help/using/reference/ids-in-aam.md"> 閱Audience ManagerID索 </a>引)。傳送包含您自己使用者ID的資料時，請在檔案名稱中使用此指派的ID。 例如，<code>...ftp_dpm_21_123456789.sync</code>指示<span class="keyword">Audience Manager</span>將線上資料告知屬於資料源21的ID。 </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID)：如果</b> 資料檔案名稱包含Android ID，請使用ID 20914。使用Android ID時，您必須使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code>會告訴<span class="keyword">Audience Manager</span>資料檔案僅包含Android ID，且ID應符合<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料來源的特徵。</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA)：如</b> 果資料檔案名稱包含iOS ID，請使用ID 20915。使用iOS ID時，您必須使用欄位<code><i>_DPID_TARGET_DATA_OWNER</i></code>。 例如，<code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code>告訴<span class="keyword">Audience Manager</span>資料檔案僅包含iOS ID，且ID應符合屬於<code><i>_DPID_TARGET_DATA_OWNER</i></code>資料來源的特徵。</li>
     <li> <b>屬於其他全域資料來源的ID</b>:您可以在Roku ID上安裝廣告(RIDA)、Microsoft Advertising ID(MAID)和其他ID。使用與每個資料來源對應的ID，如<a href="/help/using/features/global-data-sources.md">全域資料來源文章</a>所述。</li> 
    </ul> <p> <p>注意： 請勿在資料檔案中混用ID類型。 例如，如果您的檔案名稱包含Android識別碼，請勿在資料檔案中放入iOS ID或您自己的ID。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>此欄位會告訴Audience Manager要將線上資料傳送至哪個資料來源。 如果您將DPID設為屬於全域資料來源的Android ID、iOS ID或其他ID，此欄位是必填欄位。 這可讓<span class="keyword">Audience Manager</span>將檔案資料連結回您的組織。 </p> <p>例如： </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 告訴Audience Manager，您對屬於資料來源33的客戶ID有資格獲得屬於資料來源21的特徵或信號。 </li> 
     <li> <b>Android ID(GAID)：告</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> 訴 <span class="keyword"> Audience </span> Manager資料檔案僅包含Android ID，且ID應符合屬於資料來源21的特徵資格。</li> 
     <li> <b>iOS ID(IDFA)：告</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 訴 <span class="keyword"> Audience </span> Manager資料檔案僅包含iOS ID，且ID應符合屬於資料來源21的特徵。</li>
     <li> <b>屬於其他全域資料來源的ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> 告訴 <span class="keyword"> Audience </span> Manager資料檔案僅包含Roku ID，且ID應符合屬於資料來源21的特徵資格。使用與每個資料來源對應的ID，如<a href="/help/using/features/global-data-sources.md">全域資料來源文章</a>所述。</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>同步選項包括： </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:當協力廠商資料提供者依使用者傳送要在Audience Manager系統中新增或移除的特徵時，通常會出現此情形。 </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:可讓客戶和資料提供者依每位使用者傳送特徵清單，以覆寫Audience Manager中指定資料來源的所有此使用者現有特徵。您不需要將所有使用者納入覆寫檔案中。 僅包含您要變更的使用者。 未指派給目標資料來源的特徵將不會被清除。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案分割為多個部分時使用，以縮短處理時間。 數字表示您要傳送的原始檔案的哪個部分。 </p> <p>為提高檔案處理的效率，請依照下列指示分割資料檔案： </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">未壓縮：1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">壓縮：200-300 MB </li> 
    </ul> <p>請參閱下面前2個<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples">檔案名示例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10位數的UTC UNIX時間戳記，以秒為單位。 時間戳記有助於使每個檔案名稱都是唯一的。 </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip是允許的FTP檔案名稱壓縮格式。 如果您使用檔案壓縮，請確定檔案名稱的副檔名正確。 </p> <p>壓縮檔案必須為3 GB或更小。 如果您的檔案較大，請與客戶服務聯絡。 雖然Audience Manager可以處理大型檔案，但我們可以協助您減少檔案大小，並提高資料傳輸的效率。 請參閱<a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">傳入資料傳輸檔案的檔案壓縮</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名示例{#file-name-examples}

以下示例顯示格式正確的檔案名。 您的檔案名稱可能看起來類似。

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[如果](assets/ftp_dpm_1234_1445374061.overwrite) 您需要其他範例，請下載範例檔案。此檔案以`.overwrite`檔案副檔名保存。 使用簡單的文字編輯器開啟它。

## 接受的檔案大小{#accepted-file-sizes}

請考慮下圖，以便最快／最早地處理您的檔案，以及將資料傳送至[!DNL Audience Manager] / [!DNL FTP]目錄時的檔案大小限制。

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

