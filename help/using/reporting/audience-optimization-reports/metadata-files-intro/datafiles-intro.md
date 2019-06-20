---
description: 資料檔案包含曝光、點按或轉換資料。正確設定格式後，您可以將此資料匯入Audience Manager並在「對象最佳化」報表中檢視。根據本節中的規格格式化您的資料檔案。
seo-description: 資料檔案包含曝光、點按或轉換資料。正確設定格式後，您可以將此資料匯入Audience Manager並在「對象最佳化」報表中檢視。根據本節中的規格格式化您的資料檔案。
seo-title: 觀眾最佳化報表的資料檔案
solution: Audience Manager
title: 觀眾最佳化報表的資料檔案
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15 Fe04 c379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

資料檔案包含曝光、點按或轉換資料。正確設定格式後，您可以將此資料匯入Audience Manager並在「對象最佳化」報表中檢視。根據本節中的規格格式化您的資料檔案。

## 概述 {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. 此程序需要個別的曝光、點按和轉換資料的檔案。請勿將這些事件混合在單一檔案中。

資料檔案必須附有中繼資料檔案。中繼資料檔案內容會將資料檔案資訊與報表功能表中相關、人力可讀標籤相符。For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

下列語法定義格式良好的資料檔案名稱的結構。Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**語法:** <pre><code><i>event type</i>_<i>yyyymdd</i></code></pre>

在檔案名稱中：

* 事件類型指出檔案包含印象、點按或轉換。為每個事件類型建立個別檔案。
* 底線會分隔事件類型和一年日期的時間戳記。
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

根據這些需求，根據下列內容來命名您的資料檔案：

* 曝光資料： <pre><code>impressions_<i>yyyymdd<i>.gz</code></pre>
* 按一下資料： <pre><code>clicks_<i>yyyymdd</i>.gz</code></pre>
* 轉換資料： <pre><code>conversions_<i>yyyymdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

下列語法定義格式良好的資料檔案中的內容結構。Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**語法:** <pre><code><i>header標籤1</i> | <i>header標籤</i> … <i>header標籤n</i> | <i>version</i></code></pre>

在檔案內容中：

* 標題標籤必須依照下表所示順序出現。曝光和點按使用相同的標籤。轉換檔案包含額外標題。
* If you don&#39;t have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. 目前版本為1.1。
* 使用非列印ASCII001字元分隔檔案標題和內容。如果您無法使用ASCII001，請將標題和資料與標籤分隔字元分隔。As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**欄位標籤**

下表列出並說明資料檔案的欄標題。標題區分大小寫，且必須依表格中的順序顯示。除非另有指示，所有資料類型皆為整數(INT)。

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>時間戳記 </p> </td> 
   <td colname="col2"> <p>曝光、點擊或轉換事件的UTC日期和時間。Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告商ID </p> </td> 
   <td colname="col2"> <p>廣告商的資料來源ID或整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>業務單位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促銷活動ID </p> </td> 
   <td colname="col2"> <p>行銷活動 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>創作 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網站ID </p> </td> 
   <td colname="col2"> <p>網站 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>位置ID </p> </td> 
   <td colname="col2"> <p> 來自廣告伺服器的數值位置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序ID </p> </td> 
   <td colname="col2"> <p>插入順序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>Tactic ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>垂直或類別的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數量 </p> </td> 
   <td colname="col2"> <p> 轉換事件中售出的項目數。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>購買或其他轉換金額。資料類型：浮動視窗。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他資料 </p> </td> 
   <td colname="col2"> <p>轉換登陸頁面的URL。資料類型: 字串. </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>轉換類型。指出轉換是否相符。選項包括: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code></code>0：曝光次數 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code></code>1：按一下 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>：未歸因或未知 </li> 
    </ul> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在曝光、點按或轉換資料檔案中每一列結尾處所顯示的必要版本號碼。目前版本為1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. 如需傳送/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

**傳送路徑語法和範例**

資料儲存在Amazon S目錄中每個客戶的個別命名空間中。檔案路徑遵循下列語法。Note, *italics* indicates a variable placeholder. 其他元素是常數或索引鍵，不會變更。

**語法:** <pre><code>…/log_ ingtion/pid= <i>AAM ID<i>/dpid= <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymdd</i></code></pre>

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
   <td colname="col2"> <p>此金鑰值配對包含傳入事件呼叫的資料來源ID。它可識別資料來自於資料，並將該資料系結至支援的中繼資料檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 記錄檔</code> </p> </td> 
   <td colname="col2"> <p> 資料檔案的較高層級目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>file type</i>_<i>yyyymdd</i></code> </p> </td> 
   <td colname="col2"> <p>一個檔案類型名稱，指出它包含何種資料和傳送時間戳記。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例上傳路徑和檔案名稱**

上傳檔案時，路徑類似於：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**檔案處理時間與更新**

資料檔案會每隔一天處理次。

若要更新您的資料，請傳送包含特定日期之所有印象、點按或轉換的檔案。在這種情況下，一天是24小時到下一個午夜的時段。作為最佳實務，您可以使用UTC時間定義您的日間隔。

## 後續步驟 {#next-steps}

檢視命名和建立中繼資料檔案的需求。To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
