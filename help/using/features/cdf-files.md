---
description: 客戶資料摘要(CDF)檔案的基本資訊，以及入門說明。 如果您有興趣接收CDF檔案或只是想要更多資訊，請從這裡開始。
keywords: 第二方資料；第二方；第二方資料；第二方
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: 客戶資料摘要
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有關[!UICONTROL Customer Data Feed] ([!UICONTROL CDF])檔案的基本資訊，以及如何開始使用的說明。 如果您有興趣接收[!UICONTROL CDF]個檔案或只是想要更多資訊，請從這裡開始。

## 檔案內容和用途 {#file-contents-purpose}

[!UICONTROL CDF]檔案包含的資料與[!DNL Audience Manager]事件呼叫(`/event`)傳送至我們伺服器的資料相同。 這包括使用者ID、[!UICONTROL trait IDs]、[!UICONTROL segment IDs]等資料，以及事件呼叫所擷取的所有其他引數。 內部[!DNL Audience Manager]系統將事件資料處理為[!UICONTROL CDF]檔案，其內容已整理到以設定順序出現的欄位中。 [!DNL Audience Manager]嘗試每小時產生[!UICONTROL CDF]個檔案，並將它們儲存在[!DNL Amazon S3]伺服器上安全、特定於客戶的貯體中。 我們會提供這些檔案，讓您能夠不受使用者介面的限制使用[!DNL Audience Manager]資料。

>[!IMPORTANT]
>
>使用CDF檔案時，請注意下列限制：
>
>* 設定CDF檔案傳送之前，請確定您擁有來自協力廠商資料提供者的適當許可權，可匯出協力廠商特徵。 Audience Manager目前不支援使用者介面中的功能，無法向協力廠商資料提供者要求CDF檔案傳遞匯出許可權，因此請單獨聯絡他們。
>* 您不應該使用[!UICONTROL CDF]檔案當做Proxy來監視頁面流量、調解報告差異或計費等。

## 快速入門 {#getting-started}

沒有自助式處理程式可啟動[!UICONTROL CDF]檔案傳遞。 請連絡您的[!DNL Audience Manager]顧問或客戶服務以開始使用。 實施期間，您的[!DNL Audience Manager]代表將：

* 設定您的[!DNL Amazon S3]儲存貯體。
* 提供唯讀的[!DNL S3]驗證認證給您的檔案儲存貯體。 您將無法檢視或存取其他客戶的目錄和檔案。

當檔案通知和[!UICONTROL CDF]檔案準備下載時，它們將會顯示在您的[!DNL S3]儲存貯體中。 您負責監視及下載您指派的[!DNL S3]目錄中的檔案。 請參閱[客戶資料摘要檔案處理通知](#cdf-file-processing-notifications)。

## 後續步驟 {#next-steps}

以下章節及[客戶資料摘要常見問題集](../faq/faq-cdf.md)可協助您更熟悉此服務。

## 已定義[!UICONTROL Customer Data Feed]內容 {#cdf-defined}

依照外觀順序，列出並定義[!UICONTROL CDF]檔案中的資料元素和陣列。 定義包含資料型別，但此資訊不是[!UICONTROL CDF]檔案的一部分。

>[!IMPORTANT]
>
>CDF設定中預設會排除事件畫素。 如果您想要在CDF檔案中包含事件畫素，請務必在傳送給客戶服務的請求中指定。 在CDF檔案中，每個事件畫素都會填入為唯一的列。

## 定義 {#definitions}

[!UICONTROL CDF]檔案包含下面定義的部分或全部欄位。 如需內部檔案組織的相關資訊，請參閱[客戶資料摘要檔案結構](#cdf-file-structure)。

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
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>時間戳記 </p> </td> 
   <td colname="col3"> <p><span class="wintitle">資料收集伺服器</span> (DCS)處理CDF檔案的時間。 時間戳記使用<i>yyyy-mm-dd hh:mm:ss</i>格式，且設定為UTC時區。 </p> <p> <p>注意：事件時間<i>不是</i>： <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">頁面事件或事件呼叫本身的時間，雖然可能接近這些時間。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">與檔案名稱中的DCS時數相關。 另請參閱<a href="#different-processing-times">客戶資料摘要檔案名稱時間和檔案內容時間……</a>。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>這是<span class="wintitle">不重複使用者ID</span> (UUID)，這是您網站訪客的38位數裝置識別碼。 另請參閱Audience Manager</a>中的<a href="../reference/ids-in-aam.md">識別碼索引。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>數值 </p> </td> 
   <td colname="col3"> <p>引發ID同步的容器的ID。 只有在您於網站實作的<i>d_nsid</i>欄位中設定容器ID時，才會填入此欄位。 否則，預設值0將不會包含在CDF檔案中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>一個特徵ID陣列，包含訪客在事件呼叫中變現（符合資格）的所有特徵。 </p> <p>請注意，陣列可包含訪客之前已符合資格的特徵，以及訪客透過此事件呼叫重新符合資格的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID陣列，包含訪客在事件呼叫中實現（符合）的所有區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>擷取所有引數（變數、ID、機碼值組、裝置廣告ID等）的字串。 已傳入事件呼叫。 </p> <p>簡短範例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>反向連結頁面的未編碼URL （如果有的話）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>訪客在事件呼叫中擷取的IP位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>指派給網站訪客的<span class="keyword">Experience Cloud</span> ID (MID)。 另請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hant" format="https" scope="external"> Cookie與AdobeExperience Platform識別服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>一個區段ID陣列，包含訪客符合資格的先前實現區段和新區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特徵ID陣列，包含訪客自上次產生資料摘要以來符合資格之先前實現的特徵和新特徵。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]檔案結構 {#cdf-file-structure}

列出並定義[!UICONTROL CDF]檔案的資料結構。 這包括資料順序、欄位分隔符號和分隔符號、資料檔案對映和範例檔案。

## 資料欄位識別碼和順序 {#identifiers-and-sequence}

[!UICONTROL CDF]個檔案未包含標示的欄或欄位標題。 相反，[!UICONTROL CDF]檔案會定義具有非列印[!DNL ASCII]字元的欄位和陣列。 此外，[!UICONTROL CDF]檔案會以特定順序列出每個欄位和陣列。 瞭解欄位識別碼和順序將有助於您正確剖析檔案。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF檔案元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>欄位分隔符號和分隔符號 </p> </td> 
   <td colname="col2"> <p>這些非列印字元定義CDF檔案的元素和結構： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a （ASCII <code> 001</code>或<code> ^A</code>）以非列印空間指示器分隔個別欄位中的資料。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b （ASCII <code> 002</code>或<code> ^B</code>）將資料與陣列及要求引數分開。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c （ASCII <code> 003</code>或<code> ^C</code>）定義機碼值組。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位順序 </p> </td> 
   <td colname="col2"> <p> <p>重要： <span class="keyword">Audience Manager</span>保留在未來發行版本中新增欄位至CDF檔案結尾的權利。 這表示檔案剖析系統的技術設計不應假設欄數固定（但現有欄可能會假設順序固定）。</p> </p> <p>CDF檔案中的資料會以下列順序顯示。/N可以出現在這些欄位中，代表空值。</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件時間 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">裝置 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已實現的特徵 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已實現的區段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">要求參數 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 位址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud裝置ID （或MID）。 另請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hant" format="https" scope="external"> Cookie與Adobe Experience Platform Identity服務</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有區段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特徵 </li> 
     </ol> </p> <p>如需欄位說明，請參閱<a href="#cdf-defined">已定義的客戶資料摘要內容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF]檔案地圖 {#cdf-file-map}

[!UICONTROL CDF]檔案資料會以下列順序顯示。

![](assets/sequence-map.png)

## 識別陣列

[!UICONTROL CDF]檔案中的陣列以`Ctrl + a`欄位分隔符號開始和結束。 這會使陣列中的第一個元素看起來像獨立資料欄位。 例如，已實現的[!UICONTROL traits]陣列以`^A1234`開頭。 陣列分隔符號和識別碼`^B5678`會依循此專案。 因此，您可能會認為已實現的[!UICONTROL traits]陣列中的第一個元素識別碼5678 （因為它以`^B`開頭）。 但事實並非如此，因此您需要熟悉資料檔案的順序和結構。 即使已實現的[!UICONTROL trait]陣列中的第一個元素（或[!UICONTROL CDF]檔案中的任何其他陣列）以`^A`開頭，檔案中的外觀順序或位置定義陣列的開頭。 而且，陣列中的第一個元素一律會以`^A`與前一個專案分開。

## 範例[!UICONTROL CDF]檔案 {#sample-file}

範例[!UICONTROL CDF]檔案可能類似於以下內容。 我們在此範例中插入分行符號，以協助它符合頁面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed]檔案命名慣例 {#cdf-naming-conventions}

以下區段列出並定義您[!UICONTROL CDF]檔案名稱中的元素。

## [!UICONTROL CDF]檔案名稱：語法和範例 {#cdf-file-name}

一般[!UICONTROL CDF]檔案名稱包含下列專案。 注意，*斜體*&#x200B;表示變數預留位置：

### 語法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### 範例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

在您的[!DNL S3]儲存貯體中，檔案會依合作夥伴ID ([!UICONTROL PID])、日和小時以遞增順序排序。

## 已定義[!UICONTROL CDF]個檔案名稱元素 {#cdf-file-name-elements}

下表列出並定義[!UICONTROL CDF]檔案名稱中的專案。

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名稱元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>這是Amazon S3伺服器上CDF檔案的預設根儲存貯體。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>儲存CDF檔案的唯讀S3儲存貯體名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>處理檔案的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小時標籤法表示並以UTC時區設定的時間值。 另請參閱<a href="#different-processing-times">客戶資料摘要檔案名稱時間和檔案內容時間……</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>您的合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>識別檔案序列的值。 序列增量如下： 0_0_0 、 0_1_0 、 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip副檔名。 CDF檔案會進行gzip壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]個檔案處理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager]會將`.info`檔案寫入您的[!DNL S3]目錄，以便在您的[!UICONTROL Customer Data File] ([!UICONTROL CDF])準備下載時通知您。 `.info`檔案也包含有關[!UICONTROL CDF]檔案內容的[!DNL JSON]格式化中繼資料。 請參閱本節，瞭解此通知檔案使用的語法和欄位。

## 範例資訊檔案 {#sample-info-file}

每個`.info`檔案都包含`Files`和`Totals`區段。 `Files`區段包含一個陣列，內含每個每小時檔案的特定量度。 `Totals`區段包含特定日期所有[!UICONTROL CDF]檔案的彙總量度。 `.info`檔案的內容可能類似於以下範例。

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

## 已定義的資訊檔案欄位 {#info-file-fields-defined}

下清單格列出並定義[!UICONTROL CDF] `.info`檔案中的專案。

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
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>啟動包含CDF檔案中繼資料的陣列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小（位元組）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 連字型大小後面的數字顯示了在多部分上傳期間用來建置檔案的部分的數量。 <code> ETag</code>與檔案的MD5總和檢查碼不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>檔案名稱。 請參閱<a href="#cdf-naming-conventions">客戶資料摘要檔案命名慣例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
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
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>啟動包含所有CDF檔案之彙總資料的物件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>資料可用的日期。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>資料可用的小時。 使用UTC時區設定的24小時格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>該日期所有CDF檔案的總大小，以位元組為單位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上傳至S3目錄的檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]檔案名稱時間和檔案內容時間不同 {#different-processing-times}

您的[!UICONTROL CDF]檔案在檔案名稱和檔案內容中包含時間戳記。 這些時間戳記會針對相同的[!UICONTROL CDF]檔案記錄不同的事件程式。 在同一個檔案的名稱和內容中看到不同的時間戳記是很常見的現象。 瞭解每個時間戳記可協助您在處理此資料或嘗試依時間排序資料時，避免常見錯誤。

## 找到[!UICONTROL CDF]個檔案時間戳記 {#locating-timestamps}

[!UICONTROL CDF]個檔案記錄時間在2個不同位置不同。

![](assets/cdf-timestamp.png)

## 瞭解時間戳記之間的差異 {#understanding-timestamps}

下表提供有關您的[!UICONTROL CDF]檔案時間戳記的更多詳細資料，以及如何正確使用這些時間戳記的資訊。

| 時間戳記位置 | 說明 |
|--- |--- |
| 檔案名稱 | [!DNL CDF]檔案名稱中的時間戳記會標示[!DNL Audience Manager]開始準備傳送檔案的時間。 此時間戳記設定在[!DNL UTC]時區。 它使用`hour=`引數，時間格式為24小時表示法的2位數小時。 這個時間可能與檔案內容中記錄的事件時間不同。 處理[!DNL CDF]檔案時，有時您會注意到您的[!DNL S3]貯體在某一小時是空的。 空白貯體表示可能有下列其中一種情況：<ul><li>沒有該特定小時的資料。 </li><li> 我們的伺服器負載過重，在特定小時內無法處理檔案。 當伺服器趕上進度時，會將原本應該放在較早時段檔案中的檔案放入具有較晚時間值的貯體中。 例如，當應在17小時貯體中的檔案出現在18小時貯體中（檔案名稱中包含`hour=18`）時，您會看到此訊息。 在此情況下，伺服器可能會在17小時內開始處理您的檔案，但無法在該時間間隔內完成它。 相反地，檔案會推送至下一個每小時時段。</li></ul><br>**重要**：請勿使用檔案名稱時間戳記，依時間將事件分組。 如果您需要依時間分組，請在檔案內容中使用`EventTime`時間戳記。 |
| 檔案內容 | [!DNL CDF]檔案內容中的時間戳記會標籤[!DNL Data Collection Servers]開始處理檔案的時間。 此時間戳記設定在[!DNL UTC]時區。 它使用`EventTime`欄位，時間格式為&#x200B;*`yyyy-mm-dd hh:mm:ss`*。 這個時間接近頁面上事件的實際時間，但可能不同於檔案名稱中的小時指標。<br> **提示**：與檔案名稱中的`hour=`時間戳記不同，您可以使用`EventTime`依時間將資料分組。 |

>[!MORELIKETHIS]
>
>* [客戶資料摘要常見問題集](../faq/faq-cdf.md)
