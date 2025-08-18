---
description: 說明用來命名傳出資料檔案的必要欄位、語法和慣例。
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: 傳出資料檔案名稱語法和範例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---

# 傳出資料檔案名稱：語法與範例{#outbound-data-file-name-syntax-and-examples}

說明用來命名傳出資料檔案的必要欄位、語法和慣例。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>此檔案中的樣式元素（`monospaced text`、*斜體*、括弧`[ ]` `( )`等）表示程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 語法和檔案名稱元素 {#syntax-file-name}

輸出檔案名稱包含下列元素。 以下所有元素皆為選用元素。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 參數

此表格會定義傳出資料檔案名稱中的元素。

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
   <td colname="col2"> <p>請參閱資料傳輸方法。 傳輸方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP — 使用SFTP傳輸 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> — 轉移至<span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目的地ID。 </p> <p>在<span class="keyword"> Audience Manager </span>中，目的地是整合的執行個體，您可以在此對應您的目標定位區段。 客戶可有多個目的地，視業務需求而定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者或資料來源識別碼。 此ID可識別檔案內容中存在的使用者ID型別。 最常見的使用者ID索引鍵為： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google廣告商ID </span> （原始、未雜湊） </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 — 廣告商<span class="keyword">的</span> Apple ID （原始、未雜湊） </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">廠商ID — 第三方使用者ID （網頁/Cookie） </li> 
     </ul> </p> <p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html?lang=zh-Hant">全域資料來源</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 來自第三方平台的客戶識別碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一種巨集預留位置，可根據同步型別將標籤新增至檔案名稱。 同步型別包括完整和增量。 它們會在檔案名稱中顯示為<code> iter </code>或<code> full </code>。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>：表示「反複式」或累加式同步處理。 增量檔案僅包含自上次同步處理以來收集的新資料。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>：表示「完整」同步處理。 完全同步的檔案包含舊資料以及自上次同步後收集的任何新資料。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>以UTC時區表示的13位數UNIX時間戳記（以毫秒為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整數。 識別分割成多個部分的檔案部分，以縮短處理時間。 數字表示資料屬於原始檔案的哪一部分。</p>  <p>如果分割大小小於100個部分，整數必須至少為3位數，前面加零。</p>  <p>原始檔案沒有任何分割編號。 第一個分割檔案的結尾將會是001。 請參閱下列範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名稱範例 {#file-name-examples}

### 案例1

檔案已傳送至[!DNL Amazon S3]位置，檔案內容中有&#x200B;*`PID_ALIAS="XYZCustomer"`*&#x200B;和[!DNL Google Advertiser IDs]。

例如增量檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

例如完整檔案：

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 案例2

傳送至[!DNL FTP]位置的檔案，檔案內容中沒有&#x200B;*`PID_ALIAS`*&#x200B;和[!DNL Apple Advertiser IDs]：

例如增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**案例3**：傳送至[!DNL FTP]位置的檔案，在檔案內容( *`PID_ALIAS="XYZCustomer"`*)中包含&#x200B;*`Vendor ID=45454`*&#x200B;和協力廠商使用者ID：

例如增量檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

例如完整檔案：

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 傳出資料檔案內容：語法和引數 {#outbound-contents-syntax}

說明用來在輸出資料檔案中組織資訊的必要欄位、語法和慣例。 根據這些規格格式化您的資料。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>此檔案中的樣式元素（`monospaced text`、*斜體*、括弧`[ ]` `( )`等）表示程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

### 語法

資料檔案中的欄位會以下列順序顯示：

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 參數

此表格會列出定義資料檔案內容的變數。

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
   <td colname="col2"> <p>由<span class="keyword"> Audience Manager </span>指派的不重複使用者識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>以空格分隔UUID和區段資料 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>訪客所屬的區段ID。 請使用逗號分隔多個區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>使用者被取消資格的區段ID。 請使用逗號分隔多個區段。 進行完整同步時，您可以忽略已移除的區段，因為資料檔案將包含使用者目前區段的完整清單。 通常，您會想要瞭解使用者所屬的區段，而非使用者已從中移除的區段。 另請參閱<a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples">傳出資料檔案名稱：語法和範例</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 範例：基本檔案格式

正確格式化的資料檔案可能類似於以下範例。 此檔案專案表示使用者符合區段24、26和27的資格。 必要時，`UUID`和區段ID會以空格分隔。 另一個空格會分隔區段ID集。 在此範例中，使用者屬於區段24、26和27。 這些區段已從區段25和28中移除。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
