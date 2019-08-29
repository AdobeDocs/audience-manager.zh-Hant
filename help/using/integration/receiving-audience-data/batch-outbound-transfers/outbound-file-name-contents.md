---
description: 說明用來命名對外資料檔案的必填欄位、語法和慣例。
seo-description: 說明用來命名對外資料檔案的必填欄位、語法和慣例。
seo-title: 傳出資料檔案名稱語法和範例
solution: Audience Manager
title: 傳出資料檔案名稱語法和範例
uuid: effpaf6-c37 c-45f3-9d2 f-a938 a9 da47 a6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# 傳出資料檔案名稱：語法和範例{#outbound-data-file-name-syntax-and-examples}

說明用來命名對外資料檔案的必填欄位、語法和慣例。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`、 *斜體*、括號 `[ ]``( )`等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 語法和檔案名稱元素 {#syntax-file-name}

對外檔案名稱包含下列元素。以下所有元素均為選用項目。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 參數

表格會定義傳出資料檔案名稱中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>同步_類型 </i></code> </p> </td> 
   <td colname="col2"> <p>指資料傳輸方法。傳輸方式包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP-使用SFTP傳輸 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S </span> -轉移 <span class="keyword"> 至Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目的地ID。 </p> <p><span class="keyword"> 在Audience Manager </span>中，目的地是整合的例項，可讓您對應可搜尋區段。客戶可以有多個目的地，視業務需求而定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_ DPID </i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者或資料來源ID。此ID識別檔案內容中存在的使用者ID類型。最常見的使用者ID金鑰為： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google廣告商ID </span> (原始、已處理) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Advertisers的Apple ID </span> (原始、已處理) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">廠商ID-第三方使用者ID(網路/Cookie) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ ALIAS </i></code> </p> </td> 
   <td colname="col2"> 第三方平台的客戶識別碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>同步_ MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是巨集預留位置，可根據同步類型新增標籤至檔案名稱。同步類型包括完整和增量。檔案名稱會以 <code> It </code> 或 <code> 完整版 </code>顯示。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> ier </code>：表示「反覆」或增量同步。遞增檔案只包含自從上次同步後收集的新資料。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> 完整 </code>：表示「完整」同步。完全同步化的檔案包含舊資料，以及自上次同步後收集的任何新資料。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>時間戳記 </i></code> </p> </td> 
   <td colname="col2"> <p>以毫秒為單位的13位數UNIX時間戳記，位於UTC時區。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNum</i></code></p> </td> 
   <td colname="col2"> <p>整數。識別已分割為多個部分的檔案部分，以改善處理時間。數字表示資料屬於原始檔案的哪一部分。</p>  <p>如果分割大小低於100個組件，整數必須至少有位數長，且預設為零。</p>  <p>原始檔案不會有任何分割號碼。第一個分割檔案將以001結尾。請參閱下方範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz(選用) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名稱範例 {#file-name-examples}

### 方案1

檔案傳送到 [!DNL Amazon S3] 位置，並包含 *`PID_ALIAS="XYZCustomer"`*[!DNL Google Advertiser IDs] 在檔案內容中。

E.g. 增量檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

E.g. 完整檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 方案2

傳送至 [!DNL FTP] 位置的檔案(不含 *`PID_ALIAS`* 和包含 [!DNL Apple Advertiser IDs] 在檔案內容中)：

E.g. 增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. 完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**方案3**：傳送到 [!DNL FTP] 位置的檔案， *`PID_ALIAS="XYZCustomer"`* 以及檔案內容中的第三方使用者ID( *`Vendor ID=45454`*)：

E.g. 增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. 完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 傳出資料檔案內容：語法和參數 {#outbound-contents-syntax}

說明用來組織傳出資料檔案中資訊的必填欄位、語法和慣例。根據這些規格格式化您的資料。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`、 *斜體*、括號 `[ ]``( )`等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

### 語法

資料檔案中的欄位會依此順序顯示：

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 參數

表格會列出定義資料檔案內容的變數。

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager指派的唯一使用者ID </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; SAINT&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>將UUID和區段資料與空格分隔 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>區段_ N </i></code> </p> </td> 
   <td colname="col2"> <p>訪客所屬的區段ID。以逗號分隔多個區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>EXCERDED_ SERGE_ N </i></code> </p> </td> 
   <td colname="col2"> <p>使用者被取消資格的區段ID。以逗號分隔多個區段。透過完全同步，您可以忽略移除的區段，因為資料檔案將包含使用者目前區段的完整清單。通常，您想知道使用者屬於哪些群體，而非使用者已移除的區段。另請參閱 <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 「對外資料檔案名稱」：語法和範例 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 範例：基本檔案格式

格式正確的資料檔案看起來類似下列範例。此檔案項目指出使用者符合區段24、26和27的資格。視需要，空格會分隔和 `UUID` 區段ID。另一個空間會分隔區段ID集。在此範例中，使用者屬於區段24、26和27。它們已從區段25和28移除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
