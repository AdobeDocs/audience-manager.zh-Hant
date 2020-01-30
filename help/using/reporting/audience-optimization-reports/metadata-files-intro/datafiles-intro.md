---
description: 資料檔案包含曝光、點按或轉換資料。 當格式正確時，您可將此資料匯入Audience Manager，並在「對象最佳化」報表和可操作的記錄檔中使用。 根據本節中的規格格式化資料檔案。
seo-description: 資料檔案包含曝光、點按或轉換資料。 當格式正確時，您可將此資料匯入Audience Manager，並在「對象最佳化」報表和可操作的記錄檔中使用。 根據本節中的規格格式化資料檔案。
seo-title: 對象最佳化報告的資料檔案和可操作的記錄檔
solution: Audience Manager
title: 對象最佳化報告的資料檔案和可操作的記錄檔
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
translation-type: tm+mt
source-git-commit: 776aaad0c063a870ef804d166292228f83575f48

---


# 對象最佳化報告的資料檔案和可操作的記錄檔 {#data-files-for-audience-optimization-reports}

資料檔案包含曝光、點按或轉換資料。 當格式正確時，您可將此資料匯入Audience Manager，以便在「對象最佳化報表」中檢視該資料 [，並透過可操作的記錄檔](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 案使用資料建立特徵 [](/help/using/integration/media-data-integration/actionable-log-files.md)。 依照本節中的這些規格設定資料檔案的格式。

## 概述 {#overview}

正確命名和格式化的資料檔案可讓您將曝光、點按或轉換資料匯入「對象最佳化 [報表」中](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 當您與未整合且您想要在該報表套裝中處理其資料的 [!DNL Audience Manager] 合作夥伴合作時，這項功能十分有用。 此程式需要個別的檔案，才能產生曝光、點按和轉換資料。 請勿將這些事件混合在單一檔案中。

資料檔案必須隨附中繼資料檔案。 中繼資料檔案內容會比對資料檔案資訊與報表選單中相關、人工可讀的標籤。 如需詳細資訊，請參 [閱中繼資料檔案的概述和對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

## 資料檔案的命名慣例 {#naming-conventions}

下列語法定義格式良好的資料檔案名稱的結構。 請注意， *斜體* 表示變數預留位置會依檔案內容而改變。

**語法:** <pre><i>event type</i>_<i>yyyymmdd</i></code></pre>

在檔案名中：

* 事件類型表示檔案包含曝光、點按或轉換。 為每個事件類型建立個別的檔案。
* 底線可分隔事件類型和年月日時間戳記。
* 在上傳之前，請使用gzip壓縮您的檔案，並使用副檔名 `.gz` 儲存檔案。

根據這些要求，請根據資料檔案的內容命名檔案，如下所示：

* 印象資料： <pre>impressions_<i>yyyymmdd</i>.gz</code></pre>
* 按一下資料： <pre>clicks_<i>yyyymmdd</i>.gz</code></pre>
* 轉換資料： <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## 資料檔案的內容格式 {#content-format}

下列語法定義格式良好的資料檔案的內容結構。 注意， *斜體* 表示變數預留位置，並以實際資料檔案中的標籤取代。

**語法:** <pre><i>標題標籤1</i> |標 <i>題標籤2</i> ...標 <i>題標籤n</i> |版 <i>本</i></code></pre>

在檔案內容中：

* 標題標籤必須依順序顯示，如下表所示。 印象和點按使用相同的標籤。 轉換檔案包含額外的標題。
* 如果您沒有特定欄的資料，請在該欄填入 `-1`。

* 檔 *案必須以* 版本號碼結尾。 目前版本為1.1。
* 使用非列印的ASCII 001字元來分隔檔案標題和內容。 如果您無法使用ASCII 001，請使用標籤分隔字元分隔標題和資料。 由於這些是非列印字元，上述語法範例只會顯示 `"|"` 管道以供顯示。

**欄位標籤**

下表列出並說明資料檔案的欄標題。 標題會區分大小寫，且必須依表格中的順序顯示。 除非另有指示，所有資料類型都是整數(INT)。

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
   <td colname="col2"> <p>曝光、點按或轉換事件的UTC日期和時間。 使用格 <code> yyyy-MM-dd HH:mm:ss</code> 式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者ID </p> </td> 
   <td colname="col2"> <p>您網站訪客的ID，也稱為資料提供者唯 <span class="term"> 一使用者ID</span> 或DPUUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告商ID </p> </td> 
   <td colname="col2"> <p>您廣告商的資料來源ID或整合代碼。 </p> </td> 
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
   <td colname="col2"> <p>戰術ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直ID </p> </td> 
   <td colname="col2"> <p>垂直或類別的產業ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數量 </p> </td> 
   <td colname="col2"> <p> 轉換事件中售出的項目數。 </p> <p> <i>僅限轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收入 </p> </td> 
   <td colname="col2"> <p>購買或其他轉換金額。 資料類型：漂浮。 </p> <p> <i>僅限轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>其他資料 </p> </td> 
   <td colname="col2"> <p>轉換登陸頁面的URL。 資料類型: 字串. </p> <p> <i>僅限轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事件類型 </p> </td> 
   <td colname="col2"> <p>轉換類型。 指出轉換是否相符。 選項包括: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 曝光數 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 按一下 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>:非屬性或未知 </li> 
    </ul> <p> <i>僅限轉換資料檔案。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>版本 </p> </td> 
   <td colname="col2"> <p>在曝光、按一下或轉換資料檔案中每一列結尾顯示的必要版本號碼。 目前版本為1.1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料檔案的傳送方法 {#delivery-methods}

將您的印象、點按或轉換資料檔案上傳至您帳戶的Amazon S3目 [!DNL Audience Manager] 錄。 如需傳送／目錄路徑、檔案處理時間和更新的相關資訊，請參閱本節。

>[!IMPORTANT]
>
> 請連絡您的Audience manager顧問或客戶服務，以開始並設 [!DNL Amazon S3] 定資料檔案的目錄。

**傳送路徑語法和範例**

資料會儲存在目錄中每位客戶的個別命名空 [!DNL Amazon S3] 間中。 檔案路徑遵循下列語法。 Note, *italics* indicates a variable placeholder. 其他元素是常數或鍵，不會變更。

**語法:** <pre>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/檔案類型 <i>_</i><i>yyyymmdd</i></code></pre>

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
   <td colname="col2"> <p>此金鑰值配對包含在事件呼叫中傳入的資料來源ID。 它會識別資料來源的機構，並將該資料系結至支援的中繼資料檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 資料檔案的更高層級目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>一種檔案類型名稱，它指示包含的資料類型和傳送時間戳。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**上傳路徑和檔案名稱範例**

上傳檔案時，路徑看起來類似：

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**檔案處理時間與更新**

資料檔案每天會以定期間隔處理四次。

若要更新資料，請傳送包含特定日期所有印象、點按或轉換的檔案。 在此例中，一天是從午夜到下一個午夜的24小時時段。 作為最佳做法，您可能希望使用UTC時間定義您的日間隔。

## 後續步驟 {#next-steps}

檢視命名和建立中繼資料檔案的需求。 若要開始，請參閱中 [繼資料檔案的概述和對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。
