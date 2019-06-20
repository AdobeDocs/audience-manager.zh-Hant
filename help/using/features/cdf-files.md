---
description: 有關客戶資料饋送(CMS)檔案的基本資訊，以及如何開始使用的說明。如果您想要接收CMS檔案，或只想瞭解更多資訊，請從此處開始。
keywords: 第二方資料；第二方；第二方資料；第二方
seo-description: 有關客戶資料饋送(CMS)檔案的基本資訊，以及如何開始使用的說明。如果您想要接收CMS檔案，或只想瞭解更多資訊，請從此處開始。
seo-title: 客戶資料饋送
solution: Audience Manager
title: 客戶資料饋送
uuid: a5de1630-2c7a-4862-9ba0-f8643 cd2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you&#39;re interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

[!UICONTROL CDF] 檔案包含 [!DNL Audience Manager] 與事件呼叫( `/event`)傳送至我們伺服器的相同資料。這包括使用者ID、特徵ID、區段ID，以及事件呼叫所擷取的所有其他參數等資料。Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] 嘗試每小時產生 [!UICONTROL CDF] 檔案，並將它們儲存在 [!DNL Amazon S3] 伺服器上安全的客戶專屬貯體中。We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## 快速入門 {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* Set up your [!DNL Amazon S3] storage bucket.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. 您將無法查看或存取屬於其他客戶的目錄和檔案。

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they&#39;re ready for download. You&#39;re responsible for monitoring and downloading files from your assigned [!DNL S3] directory. See [Customer Data Feed File Processing Notifications](#cdf-file-processing-notifications).

## 後續步驟 {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## 定義 {#definitions}

<!-- cdf-contents-defined.xml -->

[!UICONTROL CDF] 檔案包含下面定義的部分或全部欄位。For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 資料類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> 事件時間</code> </p> </td> 
   <td colname="col2"> <p>時間戳記 </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">頁面事件或事件本身的時間，但可能會接近這些時間。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">與檔案名稱中DCS小時有關。See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 裝置</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. 也請參閱 <a href="../reference/ids-in-aam.md">Audience Manager 內的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 容器 ID</code> </p> </td> 
   <td colname="col2"> <p>數值 </p> </td> 
   <td colname="col3"> <p>引發ID同步之容器的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 實作特性</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>一系列特徵ID，其中包含訪客在事件呼叫中實現的所有特性(符合資格)。 </p> <p>請注意，陣列可以包含訪客在此事件中符合資格的特徵，以及其重新符合資格的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 實現區段</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID陣列，其中包含訪客在事件呼叫中實現的所有區段(符合資格)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 要求參數</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>擷取所有參數(變數、ID、索引鍵-值配對等)的字串傳入事件呼叫。 </p> <p>縮短範例： </p> <p> <code> d_ rtbd：json，c_ contextData. a. CarrierName：mobile，c_ contextData. a. adid：92D56353-49C5-431E-B474-FC528 D585810，c_ contextData. a，RunMode：應用程式，c_ contextData. a. DaysSinceLastUpgrade：61，d_ cid_ ic：xid%01EACB6E40-AC65-4012-12FE9-ABD59965 E9 C4%011，c_ contextData. a. PrepressSearchLength：583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 反向連結資料類型</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>反向連結頁面的未編碼URL(如果有的話)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP資料類型</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>在事件呼叫中擷取的訪客IP位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> McDevice </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 所有區段</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID陣列，其中包含先前已實施的區段和訪客適用的新區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 所有特徵</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特徵ID的陣列，其中包含訪客在上次產生的資料饋送後已符合資格的先前實作特性和新特性。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. 其中包括資料順序、欄位分隔字元和分隔符號、資料檔案地圖和範例檔案。

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] 檔案不包含標記的欄或欄位標題。[!UICONTROL CDF] 檔案會改為使用非列印 [!DNL ASCII] 字元定義欄位和陣列。Also, the [!UICONTROL CDF] file lists each field and array in a specific order. 瞭解欄位識別碼和順序可協助您正確剖析檔案。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CMS檔案元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>欄位分隔符號和分隔符號 </p> </td> 
   <td colname="col2"> <p>這些非列印字元定義您CMS檔案的元素和結構： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位順序 </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. 這表示檔案剖析系統的技術設計不應假設為固定欄數(雖然它可能對現有欄具有固定順序)。 </p> </p> <p>CMS檔案中的資料會依照下列順序顯示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件時間 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">裝置 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">實作特性 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">實現區段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">要求參數 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 位址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud裝置ID(或MID)。See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有區段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特徵 </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] 檔案資料會依照下列順序顯示。

![](assets/sequence-map.png)

## 識別陣列

[!UICONTROL CDF] 檔案中的陣列會以 `Ctrl + a` 欄位分隔符號開始並結束。如此，陣列中的第一個元素就會像獨立資料欄位一樣顯示。For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). 事實並非如此，因此您必須熟悉資料檔案的順序和結構。Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. 我們已插入行，以協助它符合頁面。

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **語法**

<pre><code>s3：loc s bucket name<i></i>/day=<i>yyyy-mm-dd</i>/hour=<i>hh</i>/<i>AAM_ CMS_ partner ID_ AAM程序ID</i>_0.gz</code>
</pre>

* **範例**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

In your [!DNL S3] storage bucket, files are sorted in ascending order by Partner ID ([!UICONTROL PID]), day, and hour.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3：//aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>這是Amazon S伺服器上的CMS檔案的預設根儲存貯體。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>您的S儲存貯體名稱</i></code> </p> </td> 
   <td colname="col2"> <p>保留您的CMS檔案的唯讀S儲存貯體名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>檔案的處理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小時表示並設定UTC時區的時間值。See also, <a href="#different-processing-times"> Customer Data Feed File Name Times and File Content Times...</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>合作夥伴ID</i></code> </p> </td> 
   <td colname="col2"> <p>您的合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip檔案副檔名。已壓縮CMS檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] 將 `.info` 檔案寫入 [!DNL S3] 您的目錄，讓您知道何時 [!UICONTROL Customer Data File] ([!UICONTROL CDF])已準備好下載。`.info` 檔案也包含 [!DNL JSON] 檔案內容的格式中繼資料 [!UICONTROL CDF] 。請參閱本節，以瞭解此通知檔案所使用語法和欄位的相關資訊。

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. `Files` 區段包含一個陣列，可保留每每小時檔案的特定度量。`Totals` 區段包含特定日 [!UICONTROL CDF] 內所有檔案的匯總度量。`.info` 檔案的內容看起來類似下列範例。

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

### 檔案物件

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 檔案</code> </p> </td> 
   <td colname="col2"> <p>啓動包含您的CMS檔案中繼資料的陣列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小為位元組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3eTag。連字號後面的數字會顯示多部分上傳期間用來建立檔案的部分數。<code> eTag</code> 與檔案的MD檢查總和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>檔案名稱。See <a href="#cdf-naming-conventions"> Customer Data Feed File Naming Conventions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSquenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每個檔案的索引編號。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 總計物件

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 總計</code> </p> </td> 
   <td colname="col2"> <p>啓動包含所有CMS檔案之匯總資料的物件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 日</code> </p> </td> 
   <td colname="col2"> <p>資料可用的日期。Uses <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 小時</code> </p> </td> 
   <td colname="col2"> <p>可用資料的小時。使用UTC時區的24小時格式設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalByteSize</code> </p> </td> 
   <td colname="col2"> <p>該日期的所有CMS檔案大小(以位元組為單位)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上傳至您的S目錄的檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

[!UICONTROL CDF] 您的檔案包含檔案名稱和檔案內容中的時間戳記。These timestamps record different event processes for the same [!UICONTROL CDF] file. 在相同檔案的名稱和內容中檢視不同時間戳記並不常見。瞭解每個時間戳記可協助您在處理此資料時避免常見錯誤，或嘗試依時間排序。

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] 檔案在不同位置的時間會不同。

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| 時間戳記位置 | 說明 |
|--- |--- |
| 檔案名稱 | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. 此時間戳記設定於UTC時區中。It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. 此時間可與檔案內容中記錄的事件時間不同。劃分當使用CMS檔案時，有時您會注意到特定小時內的S儲存貯體是空的。空貯體意指以下任一項：<ul><li>該特定小時沒有資料。 </li><li> 我們的伺服器負荷過重，無法處理特定小時的檔案。當伺服器擷取時，會將原本儲存在儲存貯體中的檔案放入儲存時間較久的貯體中。For example, you&#39;ll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). 在這種情況下，伺服器可能會在小時內開始處理您的檔案，但無法在該時間間隔內完成。檔案會改為推送至下一小時的時間貯體。</li></ul><br>**重要**：請勿使用檔案名稱時間戳記來依時間分組事件。If you need to group by time, use the `EventTime` timestamp in the file contents. |
| 檔案內容 | CMS檔案內容中的時間戳記會標示資料收集伺服器開始處理檔案的時間。此時間戳記設定於UTC時區中。It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **秘訣**：與檔案名稱中的 `hour=` 時間戳記不同的是，您可以 `EventTime` 使用時間來分組資料。 |

>[!MORE_贊_ this]
>
>* [客戶資料饋送常見問題](../faq/faq-cdf.md)

