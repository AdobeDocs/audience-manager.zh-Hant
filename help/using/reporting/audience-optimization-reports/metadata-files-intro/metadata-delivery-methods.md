---
description: 傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-description: 傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。
seo-title: 中繼資料檔案的傳送方法
solution: Audience Manager
title: 中繼資料檔案的傳送方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# 中繼資料檔案的傳送方法{#delivery-methods-for-metadata-files}

傳送或更新中繼資料檔案至您Audience manager帳戶的特殊Amazon S3目錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

## 傳送路徑語法和範例 {#syntax}

資料會儲存在Amazon S3目錄中每個客戶的個別命名空間中。 檔案路徑遵循下列語法。 Note, *italics* indicates a variable placeholder. 方括弧 `[ ]` 表示可選參數。 其他元素是常數，不會變更。

**語法:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是檔案名。 請參閱 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 中繼資料檔案的命名慣例</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案處理時間與更新 {#processing-times}

中繼資料檔案每天處理四次，每隔一定時間。

若要更新中繼資料記錄，請傳送包含新資訊的檔案。 您不需要每次都傳送完整更新。
