---
description: 傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-description: 傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-title: 中繼資料檔案的傳送方法
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

## 傳送路徑語法和範例 {#syntax}

資料會儲存在Amazon S3目錄中每個客戶的個別命名空間中。 檔案路徑遵循下列語法。 Note, *italics* indicates a variable placeholder. 方括弧 `[ ]` 表示可選參數。 其他元素是常數，不會變更。

**語法:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/yyyymmdd <i>_</i>parent ID_ <i></i><i>child ID</i></code></pre>

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
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>這是目錄儲存路徑的開始。 一切就緒後，您將獲得完整的路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此金鑰值配對包含您的 <span class="keyword"> Audience Manager</span> 客戶ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此金鑰值配對包含在事件呼叫中傳入的資料來源ID。 資料來源ID是將檔案中所有內容與其所屬實際資料系結的值。 </p> <p>例如，假設您有ID為123的創意素材，且名稱為「廣告商創意A」。 當事件呼叫只傳遞在ID中時，您必須在中繼資料檔案中包含「廣告商創意A」。 促銷活動和創意素材屬於資料來源。 資料來源ID是這些連結的原因，可讓我們將檔案內容精確關聯至事件呼叫時傳送的ID。 瞭解 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> 事件呼叫ID如何決定檔案名稱、內容和傳送路徑</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> 狀態</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> 是檔案上傳／儲存目錄。 </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> 是目錄的路徑，其中包含有關已處理檔案的成功或失敗資訊。 處理完檔案後，您會看到具有 <code> yyymmdd</code> timestamp標題 <code> 的。info</code> 檔案。 狀態檔案包含JSON物件中的資料。 請參 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> 閱中繼資料檔案的狀態更新</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是檔案名。 請參閱 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 中繼資料檔案的命名慣例</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上傳和狀態路徑範例**

若要上傳中繼資料檔案或 [檢查其狀態](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md)，檔案路徑看起來會類似下列：

* 上傳路徑： `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* 處理狀態路徑： `/log_ingestion/pid=1234/dpid=567/status/20150827.info`。

## 檔案處理時間與更新 {#processing-times}

中繼資料檔案每天處理四次，每隔一定時間。

若要更新中繼資料記錄，請傳送包含新資訊的檔案。 您不需要每次都傳送完整更新。
