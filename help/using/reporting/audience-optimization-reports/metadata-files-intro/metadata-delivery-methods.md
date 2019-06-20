---
description: 傳送或更新中繼資料檔案，方法是將它們傳送至Amazon Manager帳戶的特殊Amazon S目錄。如需傳送/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-description: 傳送或更新中繼資料檔案，方法是將它們傳送至Amazon Manager帳戶的特殊Amazon S目錄。如需傳送/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-title: 中繼資料檔案的傳送方法
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017dc562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

傳送或更新中繼資料檔案，方法是將它們傳送至Amazon Manager帳戶的特殊Amazon S目錄。如需傳送/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

## Delivery Path Syntax and Examples {#syntax}

資料儲存在Amazon S目錄中每個客戶的個別命名空間中。檔案路徑遵循下列語法。Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. 其他元素是常數且不會變更。

**語法:**
<pre><code>…/log_ ingseption/pid=<i>AAM ID</i>/dpid= <i>d_ src</i>/[meta| status]/ <i>yyyynddd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

下表定義了檔案傳送路徑中的每個元素。

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ inggestion/</code> </p> </td> 
   <td colname="col2"> <p>這是目錄儲存路徑的開始。在設定一切時，您將會獲得完整的路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>此金鑰值配對包含傳入事件呼叫的資料來源ID。資料來源ID是將檔案中所有內容與其所屬的實際資料相關聯的值。 </p> <p>例如，假設您具有ID123和「廣告商Creative A」一個名稱。因為事件呼叫只會傳入中繼資料檔案中包含「廣告商Creative A」的ID。促銷活動和創意屬於資料來源。資料來源ID是關聯這些項目，並讓我們將檔案內容精確關聯至事件呼叫中傳送的ID。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> 狀態</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> 是檔案上傳/儲存目錄。 </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> is a path to a directory that hold success or fails information about your processed files.After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. 狀態檔案包含JSON物件中的資料。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>yyyymdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是檔案名稱。See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例上傳與狀態路徑**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

中繼資料檔案會在一天內正常處理次。

若要更新中繼資料記錄，只需傳送包含新資訊的檔案。您不需要每次都傳送完整更新。
