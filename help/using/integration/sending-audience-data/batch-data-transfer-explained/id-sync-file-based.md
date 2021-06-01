---
description: 說明用於檔案式ID同步的必要欄位、語法和命名慣例。 根據這些規範命名和組織檔案內容。
seo-description: 說明用於檔案式ID同步的必要欄位、語法和命名慣例。 根據這些規範命名和組織檔案內容。
seo-title: ID 同步檔案的名稱和內容要求
solution: Audience Manager
title: ID 同步檔案的名稱和內容要求
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: 傳入資料傳輸
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 6%

---

# ID 同步檔案的名稱和內容要求 {#name-and-content-requirements-for-id-synchronization-files}

說明用於檔案式ID同步的必要欄位、語法和命名慣例。 根據這些規範命名和組織檔案內容。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法和示例{#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID檔案名稱包含下列必要和選用元素：

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>靜態首碼，可將檔案識別為ID同步檔案。 在將裝置ID與其他裝置ID或客戶ID(DPUUID)相符時，請使用此首碼。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>靜態首碼，可將檔案識別為以人物為基礎的目的地的ID同步檔案。 比對客戶ID(DPUUID)與以人物為基礎的目的地的雜湊電子郵件地址時，請使用此首碼。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>主資料提供者ID是檔案名稱中DPID的父ID。 此外，資料檔案中的第一個使用者ID與主ID對應。 後續的DPID是屬於主要的其他識別碼。 同步會將檔案名稱中的DPID對應至檔案中的UUID。</p> <p>此DPID只能包含裝置ID，例如AAM UUID、GAID、IDFA等。 其不能包含DPUUID。 這麼做可能會導致同步錯誤。</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 這些ID代表與主DPID相關聯的實體或資料來源。 同步會將檔案名稱中的DPID對應至檔案中的UUID。 </p> <p>檔案名稱中的DPID數量必須與資料檔案中的UUID數量相符。 例如，假設您的檔案名稱包含主DPID和3個DPID。 您的資料檔案必須包含4個對應的UUID欄，格式如下方檔案內容一節所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10位數、UNIX時間戳記（以秒為單位）。 時間戳記有助於讓每個檔案名稱都是唯一的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常的完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案分割為多個較小檔案時使用。 這有助於改善處理時間。 數字表示您要傳入的原始檔案的哪個部分。 請參閱下方的檔案名稱範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定以選用的gzip壓縮來壓縮您的檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 檔案名稱範例

以下示例顯示了格式正確的檔案名稱。 您的檔案名稱看起來可能類似。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 如需以人物為基礎的目的地的ID同步檔案命名（c2c首碼），請參閱[工作流程A — 以所有線上活動為基礎並結合離線資料的個人化](../../../features/destinations/people-based-destinations-workflow-combined.md)或[工作流程B — 以僅限離線資料為基礎的個人化](../../../features/destinations/people-based-destinations-workflow-offline.md)。

## 檔案內容語法和範例{#file-content-syntax}

ID檔案的內容包含下列元素：

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

檔案包含使用者ID([!DNL UUID])。 在每一列中，以索引標籤分隔ID。 以下範例顯示格式正確的ID檔案。 您的內容看起來可能類似。

```
abc123 def456 ghi789 xyz987
```

### 檔案內容考量事項 {#considerations}

建立入站檔案時，請確定第一欄只填入裝置ID，例如[!DNL AAM UUID]、[!DNL GAID]、[!DNL IDFA]等。 如需Audience Manager支援之ID的詳細說明，請參閱[Audience Manager中的ID索引](../../../reference/ids-in-aam.md) 。

>[!IMPORTANT]
>
>請勿在第一欄上使用[DPUUIDs](../../../reference/ids-in-aam.md)。 這麼做可能會導致同步錯誤。

## 同步將DPUUID與UUID {#sync-matches-dpuuids-uuids}匹配

ID同步檔案的用途是使用[!DNL Audience Manager] UUID從您自己的資料來源同步[ DPUUID](../../../reference/ids-in-aam.md)。 同步將主[!DNL DPID]及其相關[!DNL DPID]s的[!DNL DPUUID]s映射到[!DNL Audience Manager] [!DNL UUID]s。將ID放在檔案名稱和內文中的位置，決定了這些識別碼彼此對應的方式。 例如，取用以下所示的兩個範例檔案：

* **檔案1:** `adobe_id_0_12345_1476312152.sync`

* **檔案2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

根據範例名稱和內容，ID會如下對映：

**檔案1** ( [下載範例檔案](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

步驟1:ID同步程式將從[!DNL DPID] 12345與左欄的[!DNL Audience Manager] [!DNL UUID]s同步[!DNL DPUUID]s。 請注意，檔案名稱中的[!DNL DPID] &quot;0&quot;代表[!DNL Audience Manager] [!DNL UUID]s。
<br/>

**檔案2** ( [下載範例檔案](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

步驟2:步驟1中已將[!DNL DPID] 12345的[!DNL DPUUID]s與Audience Manager[!DNL UUID]s同步。此ID同步的作用是從[!DNL DPID] 67890將[!DNL DPUUID]s與步驟1的Audience Manager[!DNL UUID]s同步。

<br/>

## 其他格式要求{#other-format-reqs}

用戶ID不能：

* ID本身有索引標籤。 索引標籤僅用於在資料檔案中區隔個別ID。
* 包含個人識別資訊([!UICONTROL PII])。
* 使用[!DNL URL]編碼。 僅傳入未編碼的ID。

任何以制表符或空格結尾的列都不會被處理或實現。 請務必清除列的結尾。
