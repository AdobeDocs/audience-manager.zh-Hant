---
description: 說明用於命名出站資料檔案的必填欄位、語法和慣例。
seo-description: 說明用於命名出站資料檔案的必填欄位、語法和慣例。
seo-title: 出站資料檔案名語法和示例
solution: Audience Manager
title: 出站資料檔案名語法和示例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# 出站資料檔案名：語法與範例{#outbound-data-file-name-syntax-and-examples}

說明用於命名出站資料檔案的必填欄位、語法和慣例。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`、斜 *體*、括 `[ ]``( )`號等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 語法和檔案名稱元素 {#syntax-file-name}

出站檔案名包含以下元素。 以下所有元素都是選用的。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 參數

該表定義了出站資料檔案名中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>指資料傳輸方法。 傳輸方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP —— 使用SFTP傳輸 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> -傳輸至 <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目標ID。 </p> <p>在 <span class="keyword"> Audience Manager中， </span>目標是整合的例項，您可在其中對應可定位的區段。 客戶可以有多個目標，具體取決於業務需求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者或資料來源ID。 此ID可識別檔案內容中存在的使用者ID類型。 最常見的使用者ID金鑰為： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID(原始 </span> 、未雜湊) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers(原始、 </span> 未雜湊) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">廠商ID —— 協力廠商使用者ID(Web/Cookie) </li> 
     </ul> </p> <p>如需詳 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">細資訊，請參閱全域資料</a> 來源。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 來自第三方平台的客戶識別碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一個宏佔位符，它根據同步類型將標籤添加到檔案名。 同步類型包括完整和增量。 它們會以或的形式出現在檔案 <code> iter </code> 名中 <code> full </code>。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>:表示「迭代」或增量同步。 增量檔案只包含自上次同步以來收集的新資料。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>:表示「完全」同步。 完全同步的檔案包含自上次同步以來收集的舊資料和任何新資料。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>13位數的UNIX時間戳記，以毫秒為單位，在UTC時區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整數。 識別已分割為多個部分的檔案的一部分，以改善處理時間。 數字表示資料所屬的原始檔案的哪個部分。</p>  <p>如果拆分大小小於100個部分，則整數必須至少為3位數，前面必須是零。</p>  <p>原始檔案將沒有任何分割號碼。 第一個分割檔案將以001結尾。 請參閱下列範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名稱範例 {#file-name-examples}

### 方案1

將檔案傳送至 [!DNL Amazon S3] 檔案內容中 *`PID_ALIAS="XYZCustomer"`* 的位 [!DNL Google Advertiser IDs] 置及位置。

例如，增量檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

例如，完整檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 方案2

檔案被發送到 [!DNL FTP] 位置，在檔案內 *`PID_ALIAS`* 容中 [!DNL Apple Advertiser IDs] 沒有和有：

例如，增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如，完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**方案3**:檔案傳送至 [!DNL FTP] 位置， *`PID_ALIAS="XYZCustomer"`* 檔案內容( *`Vendor ID=45454`*)中有第三方使用者ID:

例如，增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如，完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 出站資料檔案內容：語法與參數 {#outbound-contents-syntax}

說明用於組織傳出資料檔案中資訊的必填欄位、語法和慣例。 根據這些規格格式化資料。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`、斜 *體*、括 `[ ]``( )`號等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

### 語法

資料檔案中的欄位依下列順序顯示：

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 參數

該表列出了定義資料檔案內容的變數。

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>由 <span class="keyword"> Audience Manager指派的唯一使用者ID </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>將UUID和區段資料分隔為空格 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>訪客所屬的區段ID。 以逗號分隔多個區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>使用者被取消資格的區段ID。 以逗號分隔多個區段。 使用完全同步時，您可以忽略移除的區段，因為資料檔案將包含使用者目前區段的完整清單。 通常，您會想瞭解使用者所屬的區段，而非已移除的區段。 另請參閱 <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 出站資料檔案名：語法和範例 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 範例：基本檔案格式

格式正確的資料檔案看起來可能類似下列範例。 此檔案項目表示使用者符合區段24、26和27的資格。 視需要，空格會分隔 `UUID` 和區段ID。 另一個空格會分隔區段ID的集合。 在此範例中，使用者屬於區段24、26和27。 已從區段25和28中移除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
