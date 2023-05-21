---
description: 介紹用於基於檔案的ID同步的必需欄位、語法和命名約定。 根據這些規範命名和組織檔案內容。
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: ID 同步檔案的名稱和內容要求
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---

# ID 同步檔案的名稱和內容要求 {#name-and-content-requirements-for-id-synchronization-files}

介紹用於基於檔案的ID同步的必需欄位、語法和命名約定。 根據這些規範命名和組織檔案內容。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)指明代碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../../reference/code-style-elements.md)。

## 檔案名語法和示例 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID檔案名包含以下必需和可選元素：

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
   <td colname="col2"> <p>將檔案標識為ID同步檔案的靜態前置詞。 當將設備ID與其他設備ID或客戶ID(DPUUID)匹配時，請使用此前置詞。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>將檔案標識為基於人員的目標的ID同步檔案的靜態前置詞。 在將客戶ID(DPUUID)與基於人員的目標的散列電子郵件地址匹配時，請使用此前置詞。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>主資料提供程式ID是檔案名中DPID的父ID。 此外，資料檔案中的第一用戶ID與主ID相對應。 後續DPID是屬於主節點的其他標識符。 同步將檔案名中的DPID映射到檔案中的UUID。</p> <p>此DPID只能包含設備IDAAM，如UUID、GAID、IDFA等。 它不能包含DPUUID。 這樣做可能導致同步不正確。</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>資料提供程式ID。 這些ID表示與主DPID關聯的實體或資料源。 同步將檔案名中的DPID映射到檔案中的UUID。 </p> <p>檔案名中的DPID數必須與資料檔案中的UUID數相匹配。 例如，假設您的檔案名包含主DPID和3個DPID。 資料檔案必須包括4列相應的UUID，格式如下文檔案內容部分所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10位UNIX時間戳（秒）。 時間戳有助於使每個檔案名唯一。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常的完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大檔案拆分為多個小檔案時使用。 這有助於提高處理時間。 該數字指示您正在發送的原始檔案的哪個部分。 請參見下面的檔案名示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定使用可選的gzip壓縮對檔案進行壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 檔案名示例

以下示例顯示格式正確的檔案名。 您的檔案名可能看起來類似。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 有關基於人員的目標的ID同步檔案命名（c2c前置詞），請參見 [工作流A — 基於所有聯機活動和離線資料的個性化](../../../features/destinations/people-based-destinations-workflow-combined.md) 或 [工作流B — 基於僅離線資料的個性化](../../../features/destinations/people-based-destinations-workflow-offline.md)。

## 檔案內容語法和示例 {#file-content-syntax}

ID檔案的內容包括以下元素：

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

檔案包含用戶ID([!DNL UUID])。 在每行中，用頁籤分隔ID。 以下示例顯示了格式正確的ID檔案。 你的內容可能看起來很相似。

```
abc123 def456 ghi789 xyz987
```

### 檔案內容注意事項 {#considerations}

建立入站檔案時，確保第一列僅填充了設備ID，如 [!DNL AAM UUID]。 [!DNL GAID]。 [!DNL IDFA]等等。 請參閱 [Audience Manager中ID的索引](../../../reference/ids-in-aam.md) 的子菜單。

>[!IMPORTANT]
>
>不使用 [DPUUID](../../../reference/ids-in-aam.md) 列中。 這樣做可能導致同步不正確。

## 同步將DPUUID與UUID匹配 {#sync-matches-dpuuids-uuids}

ID同步檔案的目的是同步 [DPUUID](../../../reference/ids-in-aam.md) 使用 [!DNL Audience Manager] UUID。 同步映射 [!DNL DPUUID]來自主人 [!DNL DPID] 及其相關 [!DNL DPID]至 [!DNL Audience Manager] [!DNL UUID]s將ID放在檔案名和正文中的位置決定了這些標識符如何相互映射。 例如，請使用下面所示的兩個示例檔案：

* **檔案1:** `adobe_id_0_12345_1476312152.sync`

* **檔案2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

給定示例名稱和內容，ID將以下方式映射在一起：

**檔案1** ( [下載示例檔案](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 =Adobe Audience ManagerUUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TRJ6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

步驟1:ID同步進程將同步 [!DNL DPUUID]從 [!DNL DPID] 12345 [!DNL Audience Manager] [!DNL UUID]的下界。 請注意 [!DNL DPID] 檔案名中的&quot;0&quot;表示 [!DNL Audience Manager] [!DNL UUID]s
<br/>

**檔案2** ( [下載示例檔案](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TRJ6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

步驟2:這樣 [!DNL DPUUID]從 [!DNL DPID] 12345已在步驟1與Audience Manager同步 [!DNL UUID]s此ID同步將執行的是同步 [!DNL DPUUID]從 [!DNL DPID] 小行星67890 [!DNL UUID]從步驟1開始。

<br/>

## 其他格式要求 {#other-format-reqs}

用戶ID不能：

* 在ID本身中具有頁籤。 制表符僅用於在資料檔案中分離單個ID。
* 包含個人身份資訊([!UICONTROL PII])。
* 使用 [!DNL URL] 編碼。 僅傳遞未編碼的ID。

任何以制表符或空格結尾的行都不會被處理或實現。 作為規則，確保清除行末。
