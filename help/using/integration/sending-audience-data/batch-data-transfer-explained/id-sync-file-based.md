---
description: 說明用於檔案ID同步的必填欄位、語法和命名慣例。根據這些規格，命名並組織您的檔案內容。
seo-description: 說明用於檔案ID同步的必填欄位、語法和命名慣例。根據這些規格，命名並組織您的檔案內容。
seo-title: ID 同步檔案的名稱和內容要求
solution: Audience Manager
title: ID 同步檔案的名稱和內容要求
uuid: bfe42af9-9149-4da3-830e-f227 c4 e610 c
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# ID 同步檔案的名稱和內容要求 {#name-and-content-requirements-for-id-synchronization-files}

說明用於檔案ID同步的必填欄位、語法和命名慣例。根據這些規格，命名並組織您的檔案內容。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本文件中指出程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID檔案名稱包含下列必要項目和選擇性元素：

`adobe_id_`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>靜態首碼，可識別檔案為ID檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTDPID</i></code> </td> 
   <td colname="col2"> 主資料提供者ID是檔案名稱中DPIDs的父ID。此外，資料檔案中的第一個使用者ID會對應至主ID。後續的DPIDs是屬於主版的其他識別碼。同步會將檔案名稱中的DPID對應至檔案中的UUID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。這些ID代表與主DPID相關聯的實體或資料來源。同步會將檔案名稱中的DPID對應至檔案中的UUID。 </p> <p>檔案名稱中的DPIDD數目必須符合資料檔案中的UUID數目。例如，假設您的檔案名稱包含主DPID和3DPIDs。您的資料檔案必須包含個對應的UUID欄，格式如下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>時間戳記</i></code> </td> 
   <td colname="col2"> <p>10位數，UNIX時間戳記，秒數。時間戳記可讓每個檔案名稱唯一。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常、完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。將大型檔案分割為多個較小檔案時使用。這有助於改善處理時間。數字表示您要傳入的原始檔案部分。請參閱下面的檔案名稱範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定使用選擇性的gzip壓縮壓縮您的檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 檔案名稱範例

下列範例顯示格式正確的檔案名稱。您的檔案名稱看起來可能類似。

<ul class="simplelist"> 
 <li> <code> adobe_ id_111_222_333_444_444_145441414.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
</ul>

## File Content Syntax and Examples {#file-content-syntax}

ID檔案的內容包含下列元素：

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs ([!DNL UUID]). 在每一列中，將ID與標籤分開。下列範例顯示正確格式的ID檔案。您的內容看起來類似。

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the [DPUUIDs](../../../reference/ids-in-aam.md) from your own Data Sources with [!DNL Audience Manager] UUIDs. Synchronization maps the [!DNL DPUUID]s from the master [!DNL DPID] and its related [!DNL DPID]s to the [!DNL Audience Manager] [!DNL UUID]s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. 例如，請使用此處顯示的兩個範例檔案：

* **檔案1：**`adobe_id_0_12345_1476312152.sync`

* **檔案2：**`adobe_id_12345_67890_1476312876.sync`

<br/>

根據範例名稱和內容，ID會一起對應：

**檔案(**[下載範例檔案](assets/adobe_id_0_12345_1476312152.sync))

| DPID0= Adobe Audience Manager UUID | DPID12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2KZKopkFfayAagwBayQwhQQXL-TTRJ6 E4 NJR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAF4D4Gb4Lg_ T5jk_ f7rdecQns9WFNA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017Prypid8ZFHKeE-GE034 LI-53Jde0 UcCyCivD0 A2 OLM |
| 66552757407517449462805881945288602094 | XYZ3017QVBDDD-BljS28 dpXQique3_55 BVQQJMLWRegju2 M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60KuhPocka_ EK-BTCN2 u1 Hyvaue0 rd412 tsBycmd |

Step 1: the ID sync process will sync the [!DNL DPUUID]s from [!DNL DPID] 12345 with the [!DNL Audience Manager] [!DNL UUID]s in the left column. Note that the [!DNL DPID] "0" in the file name represents [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**檔案(**[下載範例檔案](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2KZKopkFfayAagwBayQwhQQXL-TTRJ6 E4 NJR38 | 4598060374 |
| XYZ3017BBR4DAF4D4Gb4Lg_ T5jk_ f7rdecQns9WFNA7h70 | 4581274262 |
| XYZ3017Prypid8ZFHKeE-GE034 LI-53Jde0 UcCyCivD0 A2 OLM | 4392434426 |
| XYZ3017QVBDDD-BljS28 dpXQique3_55 BVQQJMLWRegju2 M | 2351382994 |
| XYZ3017q9r60KuhPocka_ EK-BTCN2 u1 Hyvaue0 rd412 tsBycmd | 4601584763 |

Step 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been synced in step 1 with the Audience Manager [!DNL UUID]s. What this ID sync will do is sync the [!DNL DPUUID]s from [!DNL DPID] 67890 with the Audience Manager [!DNL UUID]s from step 1.

<br/>

## Other Format Requirements {#other-format-reqs}

使用者ID無法：

* 在ID本身中擁有標籤。標籤僅用於分隔資料檔案中的個別ID。
* Contain personally identifiable information ([!UICONTROL PII]).
* Use [!DNL URL] encoding. 僅傳入未編碼ID。

任何以標籤或空格結尾的行都不會加以處理或實現。作為規則，請確定您已清除行結尾。