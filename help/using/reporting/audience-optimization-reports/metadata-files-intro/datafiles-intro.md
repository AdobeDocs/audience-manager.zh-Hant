---
description: 資料檔案包含曝光、點按或轉換資料。 格式正確後，您可將此資料匯入Audience Manager，並用於Audience Optimization報表和可操作的記錄檔。 依照本節中的規格設定資料檔案的格式。
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: 受眾最佳化報表的資料檔案和可操作的記錄檔
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 受眾最佳化報表的資料檔案和可操作的記錄檔 {#data-files-for-audience-optimization-reports}

資料檔案包含曝光、點按或轉換資料。 格式正確後，您可將此資料匯入Audience Manager，以在 [Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 並透過 [可操作的記錄檔](/help/using/integration/media-data-integration/actionable-log-files.md). 依照本節中的這些規範設定資料檔案的格式。

## 概述 {#overview}

命名正確且格式正確的資料檔案，可讓您將曝光數、點按次數或轉換資料匯入 [Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). 這在與未整合的合作夥伴合作時很有用 [!DNL Audience Manager] 而您想要使用該報表套裝中的資料。 此程式需要個別的檔案，才能顯示曝光、點按和轉換資料。 請勿將這些事件混合在單一檔案中。

資料檔案必須附有中繼資料檔案。 元資料檔案內容將資料檔案資訊與報告菜單中相關、人類可讀的標籤匹配。 如需詳細資訊，請參閱 [中繼資料檔案的概述與對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## 資料檔案的命名慣例 {#naming-conventions}

以下語法定義格式良好的資料檔案名稱的結構。 注意， *斜體* 指示根據檔案內容而更改的變數佔位符。

**語法:** <pre><i>事件類型</i>_<i>yyyymmdd</i></code></pre>

在檔案名中：

* 事件類型表示檔案包含曝光數、點按或轉換。 為每個事件類型建立個別檔案。
* 底線可分隔事件類型和年月日時間戳記。
* 在上傳之前，請使用gzip壓縮您的檔案，並使用 `.gz` 副檔名。

根據這些需求，請根據資料檔案的內容為其命名，如下所示：

* 曝光資料： <pre>曝光次數_<i>yyyymmdd</i>.gz</code></pre>
* 按一下資料： <pre>點按次數_<i>yyyymmdd</i>.gz</code></pre>
* 轉換資料： <pre>轉換_<i>yyyymmdd</i>.gz</code></pre>

## 資料檔案的內容格式 {#content-format}

下列語法定義格式良好的資料檔案中的內容結構。 注意， *斜體* 指出變數預留位置，並以實際資料檔案中的標籤取代。

**語法:** <pre><i>標題標籤1</i> | <i>標題2</i> ... <i>標題標籤n</i> | <i>版本</i></code></pre>

在檔案內容中：

* 標題標籤必須依順序顯示，如下表所示。 曝光次數和點按次數使用相同的標籤。 轉換檔案包含額外的標題。
* 如果您沒有特定欄的資料，請在該欄位中填入 `-1`.

* 檔案 *必須* 以版本號結尾。 目前版本為1.1。
* 以非打印ASCII 001字元分隔檔案標題和內容。 如果您無法使用ASCII 001，請以索引標籤分隔字元分隔標題和資料。 由於這些是非列印字元，上方的語法範例顯示縱線字元 `"|"` 僅供顯示之用。

**欄位標籤**

下表列出並說明資料檔案的欄標題。 標題區分大小寫，且必須依表格中的順序顯示。 除非另有指示，否則所有資料類型均為整數(INT)。

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
   <td colname="col2"> <p>曝光、點按或轉換事件的UTC日期和時間。 使用 <code> yyyy-MM-dd HH:mm:ss</code> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>網站訪客的ID，亦稱為 <span class="term"> 資料提供者不重複使用者ID</span> 或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告商 — ID </p> </td> 
   <td colname="col2"> <p>廣告商的資料來源ID或整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>業務單位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
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
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> 來自廣告伺服器的數值位置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>插入訂單ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>戰術ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>垂直或類別的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數量 </p> </td> 
   <td colname="col2"> <p> 轉換事件中銷售的項目數。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>購買或其他轉換金額。 資料類型：漂浮。 </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他資料 </p> </td> 
   <td colname="col2"> <p>轉換登錄頁面的URL。 資料類型: 字串. </p> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件類型 </p> </td> 
   <td colname="col2"> <p>轉換類型。 指出轉換是否相符。 選項包括: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 曝光數 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 按一下 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:未歸因或未知 </li> 
    </ul> <p> <i>僅適用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>顯示在曝光、點按或轉換資料檔案中每一列結尾的必要版本號碼。 目前版本為1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料檔案的傳送方法 {#delivery-methods}

將您的曝光數、點按或轉換資料檔案上傳至Amazon S3目錄，以供您 [!DNL Audience Manager] 帳戶。 如需傳遞/目錄路徑、檔案處理時間和更新的相關資訊，請參閱本區段。

>[!IMPORTANT]
>
> 請連絡您的Audience Manager顧問或客戶服務，以開始並設定 [!DNL Amazon S3] 資料檔案的目錄。

**傳遞路徑語法與範例**

資料會儲存在 [!DNL Amazon S3] 目錄。 檔案路徑遵循下列語法。 注意， *斜體* 表示變數預留位置。 其他元素為常數或索引鍵，不會變更。

**語法:** <pre>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>檔案類型</i>_<i>yyyymmdd</i></code></pre>

下表定義檔案傳送路徑中的每個元素。

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
   <td colname="col2"> <p>這是目錄儲存路徑的開始。 設定完畢後，您會收到完整路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此機碼值組包含您的 <span class="keyword"> Audience Manager</span> 客戶ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此機碼值組包含在事件呼叫中傳入的資料來源ID。 它會識別資料的來源機構，並將該資料連結至支援的中繼資料檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 資料檔案的較高級別目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一種檔案類型名稱，可指出其包含的資料類型和傳送時間戳記。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上傳路徑和檔案名稱範例**

上傳檔案時，路徑看起來會類似這樣：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**檔案處理時間和更新**

每天會處理資料檔案四次，定期間。

若要更新資料，請傳入包含特定日期所有曝光數、點按或轉換的檔案。 在此案例中，一天是從午夜1點到下一點的24小時期間。 最佳實務是，您可能想使用UTC時間來定義日間隔。

## 後續步驟 {#next-steps}

檢閱命名和建立中繼資料檔案的需求。 若要開始使用，請參閱 [中繼資料檔案的概述與對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
