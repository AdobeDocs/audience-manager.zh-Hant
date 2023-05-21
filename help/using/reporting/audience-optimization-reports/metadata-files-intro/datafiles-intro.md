---
description: 資料檔案包含印象、按一下或轉換資料。 格式正確後，您可以將此資料導入Audience Manager，並在Audience Optimization報告和可操作日誌檔案中使用它。 根據本節中的規範設定資料檔案的格式。
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: 受眾最佳化報表的資料檔案和可操作的記錄檔
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 4%

---

# 受眾最佳化報表的資料檔案和可操作的記錄檔 {#data-files-for-audience-optimization-reports}

資料檔案包含印象、按一下或轉換資料。 格式正確後，可將此資料導入Audience Manager，以在 [Audience Optimization報告](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 並通過 [可操作的日誌檔案](/help/using/integration/media-data-integration/actionable-log-files.md)。 根據本節中的這些規範設定資料檔案的格式。

## 概述 {#overview}

通過正確命名和格式化的資料檔案，您可以將印象、按一下或轉換資料 [Audience Optimization報告](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 在與未與整合的合作夥伴合作時，此功能非常有用 [!DNL Audience Manager] 而且你想在報告套件中處理他們的資料。 此過程需要單獨的檔案來記錄、按一下和轉換資料。 不要將這些事件混合到單個檔案中。

資料檔案必須與元資料檔案相伴。 元資料檔案內容將資料檔案資訊與報告菜單中的相關、可人讀標籤匹配。 有關詳細資訊，請參見 [元資料檔案的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

## 資料檔案的命名約定 {#naming-conventions}

以下語法定義格式良好的資料檔案名的結構。 注意， *斜體* 指示根據檔案內容而更改的變數佔位符。

**語法:** <pre><i>事件類型</i>_<i>yyymmd</i></code></pre>

在檔案名中：

* 事件類型表示檔案包含印刷、按一下或轉換。 為每個事件類型建立單獨的檔案。
* 下划線將事件類型和年月日期時間戳分開。
* 在上載之前，請使用gzip壓縮檔案，然後使用 `.gz` 檔案副檔名。

根據這些要求，根據資料檔案的內容命名如下：

* 印象資料： <pre>印象<i>yyymmd</i>.gz</code></pre>
* 按一下資料： <pre>按一下<i>yyymmd</i>.gz</code></pre>
* 轉換資料： <pre>轉換<i>yyymmd</i>.gz</code></pre>

## 資料檔案的內容格式 {#content-format}

以下語法定義格式良好的資料檔案中的內容結構。 注意， *斜體* 指示變數佔位符，並替換為實際資料檔案中的標籤。

**語法:** <pre><i>標題標籤1</i> | <i>標題標籤2</i> ... <i>標題n</i> | <i>版本</i></code></pre>

在檔案內容中：

* 標題標籤必須按下表所示的順序顯示。 印象和點擊使用相同的標籤。 轉換檔案包含額外的標頭。
* 如果沒有特定列的資料，請用 `-1`。

* 檔案 *必須* 以版本號結束。 當前版本為1.1。
* 使用非打印ASCII 001字元分隔檔案頭和內容。 如果不能使用ASCII 001，則使用制表符分隔符分隔標題和資料。 由於這些字元是非打印字元，因此上面的語法示例顯示了管道 `"|"` 僅用於顯示。

**欄位標籤**

下表列出並說明了資料檔案的列標題。 標題區分大小寫，並且必須按順序顯示在表中。 除非另有說明，否則所有資料類型都是整數(INT)。

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>時間戳 </p> </td> 
   <td colname="col2"> <p>UTC的印象、按一下或轉換事件的日期和時間。 使用 <code> yyyy-MM-dd HH:mm:ss</code> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用戶ID </p> </td> 
   <td colname="col2"> <p>站點訪問者的ID，也稱為 <span class="term"> 資料提供程式唯一用戶ID</span> 或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告商ID </p> </td> 
   <td colname="col2"> <p>您的廣告商的資料源ID或整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>業務單位ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>市場活動ID </p> </td> 
   <td colname="col2"> <p>行銷活動 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>創意ID </p> </td> 
   <td colname="col2"> <p>創作 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>站點ID </p> </td> 
   <td colname="col2"> <p>網站 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>放置ID </p> </td> 
   <td colname="col2"> <p> 廣告伺服器的數字放置ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序ID </p> </td> 
   <td colname="col2"> <p>插入順序ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>戰術ID </p> </td> 
   <td colname="col2"> <p>戰術ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>行業垂直或類別的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數量 </p> </td> 
   <td colname="col2"> <p> 在轉換事件中銷售的物料數。 </p> <p> <i>僅用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>採購或其他轉換金額。 資料類型：浮起來。 </p> <p> <i>僅用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他資料 </p> </td> 
   <td colname="col2"> <p>轉換登錄頁的URL。 資料類型: 字串. </p> <p> <i>僅用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件類型 </p> </td> 
   <td colname="col2"> <p>轉換類型。 指示轉換是否匹配。 選項包括: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 曝光 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 按一下 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:未屬性或未知 </li> 
    </ul> <p> <i>僅用於轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在印象、按一下或轉換資料檔案中每行末尾顯示的必需版本號。 當前版本為1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料檔案的傳遞方法 {#delivery-methods}

將您的印象、按一下或轉換資料檔案上載到AmazonS3目錄 [!DNL Audience Manager] 帳戶。 有關傳遞/目錄路徑、檔案處理時間和更新的資訊，請參閱本節。

>[!IMPORTANT]
>
> 與Audience Manager顧問或客戶服務人員聯繫以開始並設定 [!DNL Amazon S3] 的子菜單。

**傳遞路徑語法和示例**

資料儲存在一個獨立的命名空間中，每個客戶都位於 [!DNL Amazon S3] 的子菜單。 檔案路徑遵循下面所示的語法。 注意， *斜體* 指示變數佔位符。 其他元素是常數或鍵，不更改。

**語法:** <pre>.../log_ingestion/pid= <i>IDAAM</i>/dpid= <i>d_src</i>/logs/ <i>檔案類型</i>_<i>yyymmd</i></code></pre>

下表定義了檔案傳遞路徑中的每個元素。

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
   <td colname="col2"> <p>這是目錄儲存路徑的開始。 設定完全時，您將收到完整路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>此鍵值對包含 <span class="keyword"> Audience Manager</span> 客戶ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>此鍵值對包含在事件調用中傳遞的資料源ID。 它標識資料來自的機構，並將資料與支援的元資料檔案關聯起來。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 資料檔案的更高級別目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一種檔案類型名稱，它指示它包含的資料類型和傳遞時間戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例上載路徑和檔案名**

上載檔案時，路徑將類似於以下內容：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**檔案處理時間和更新**

每天處理4次資料檔案，間隔不定。

要更新資料，請發送包含特定日期所有印象、按一下或轉換的檔案。 在這種情況下，一天是從午夜到下一個午夜的24小時。 作為最佳做法，您可能希望使用UTC時間定義日間隔。

## 後續步驟 {#next-steps}

查看命名和建立元資料檔案的要求。 要開始，請參閱 [元資料檔案的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。
