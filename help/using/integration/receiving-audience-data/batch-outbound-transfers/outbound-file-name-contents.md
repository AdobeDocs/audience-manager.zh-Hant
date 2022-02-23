---
description: 描述用於命名出站資料檔案的必需欄位、語法和約定。
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: 出站資料檔案名語法和示例
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 6%

---

# 傳出資料檔案名稱：語法與範例{#outbound-data-file-name-syntax-and-examples}

描述用於命名出站資料檔案的必需欄位、語法和約定。

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`。 *斜體*&#x200B;括弧 `[ ]` `( )`等) 指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 語法和檔案名元素 {#syntax-file-name}

出站檔案名包含以下元素。 以下所有元素都是可選的。

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 參數

該表定義出站資料檔案名中的元素。

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>指資料傳輸方法。 傳輸方法包括： </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP — 使用SFTP傳輸 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> AmazonS3 </span>  — 轉接至 <span class="keyword"> AmazonAWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>目標ID。 </p> <p>在 <span class="keyword"> Audience Manager </span>，目標是可映射目標段的整合實例。 客戶可以有多個目標，具體取決於業務需求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>資料提供程式或資料源ID。 此ID標識檔案內容中存在的用戶ID的類型。 最常見的用戶ID鍵是： </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google廣告商ID </span> （原始，無散列） </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple廣告商ID </span> （原始，無散列） </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">供應商ID — 第三方用戶ID(Web/Cookie) </li> 
     </ul> </p> <p>如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html">全域資料來源</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 來自第三方平台的客戶標識符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>同步模式是一個宏佔位符，它根據同步類型將標籤添加到檔案名中。 同步類型包括完全和增量。 它們將以 <code> iter </code> 或 <code> full </code>。 </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>:指示「迭代」或增量同步。 增量檔案僅包含自上次同步以來收集的新資料。 </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>:表示「完全」同步。 完全同步的檔案包含自上次同步以來收集的舊資料和任何新資料。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>UTC時區中13位UNIX時間戳（毫秒）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>整數。 標識已拆分為多個部件的檔案的一部分，以改進處理時間。 數字指示資料所屬的原始檔案的哪個部分。</p>  <p>如果拆分大小小於100個部分，則整數必須至少長3位數，前面必須有零。</p>  <p>原始檔案將沒有任何拆分編號。 第一個拆分檔案將以001結束。 請參見以下示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案名示例 {#file-name-examples}

### 方案1

檔案已發送到 [!DNL Amazon S3] 位置，使用 *`PID_ALIAS="XYZCustomer"`* 和 [!DNL Google Advertiser IDs] 的子菜單。

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

檔案已發送到 [!DNL FTP] 位置，沒有 *`PID_ALIAS`* 和 [!DNL Apple Advertiser IDs] 檔案內容中：

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

**方案3**:檔案已發送到 [!DNL FTP] 位置，使用 *`PID_ALIAS="XYZCustomer"`* 檔案內容中具有第三方用戶ID( *`Vendor ID=45454`*):

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

## 出站資料檔案內容：語法和參數 {#outbound-contents-syntax}

描述用於組織出站資料檔案中資訊的必填欄位、語法和約定。 根據這些規格格式化資料。

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>樣式元素(`monospaced text`。 *斜體*&#x200B;括弧 `[ ]` `( )`等) 指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

### 語法

資料檔案中的欄位按以下順序顯示：

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
   <td colname="col2"> <p>由分配的唯一用戶ID <span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>將UUID和段資料分隔為空格 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>訪問者所屬的段ID。 用逗號分隔多個段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>取消用戶資格的段ID。 用逗號分隔多個段。 通過完全同步，可以忽略刪除的段，因為資料檔案將包含用戶當前段的完整清單。 通常，您希望瞭解用戶所屬的段，而不是從中刪除的段。 另請參閱 <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 出站資料檔案名：語法和示例 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 示例：基本檔案格式

格式正確的資料檔案可能與以下示例類似。 此檔案條目表示用戶符合段24、26和27的條件。 根據需要，空格分隔 `UUID` 和段ID。 另一個空格分隔段ID集。 在本例中，用戶屬於段24、26和27。 從25和28節中刪除了。

```
59767559181262060060278870901087098252  24,26,27  25,28
```
