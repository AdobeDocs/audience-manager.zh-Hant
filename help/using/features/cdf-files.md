---
description: 客戶資料摘要(CDF)檔案的基本資訊以及如何開始的指示。 如果您想要接收CDF檔案或只是想要詳細資訊，請從這裡開始。
keywords: 第二方資料；第二方；第二方資料；第二方資料
seo-description: 客戶資料摘要(CDF)檔案的基本資訊以及如何開始的指示。 如果您想要接收CDF檔案或只是想要詳細資訊，請從這裡開始。
seo-title: 客戶資料摘要
solution: Audience Manager
title: 客戶資料摘要
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: 客戶資料摘要
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 4%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

關於[!UICONTROL Customer Data Feed]([!UICONTROL CDF])檔案的基本資訊以及如何開始的說明。 如果您想要接收[!UICONTROL CDF]檔案，或只是想要詳細資訊，請從這裡開始。

## 檔案內容和用途{#file-contents-purpose}

[!UICONTROL CDF] 檔案包含的資料與 [!DNL Audience Manager] 事件呼叫 (`/event`) 傳送至我們伺服器的資料相同。這包括使用者ID、[!UICONTROL trait IDs]、[!UICONTROL segment IDs]等資料，以及事件呼叫所擷取的所有其他參數。 內部[!DNL Audience Manager]系統將事件資料處理為[!UICONTROL CDF]檔案，其中內容按照設定順序排列為以欄位。 [!DNL Audience Manager] 會嘗試每小時 [!UICONTROL CDF] 產生檔案，並將檔案儲存在伺服器上安全、客戶專屬的貯 [!DNL Amazon S3] 體中。我們提供這些檔案，以便您能夠處理[!DNL Audience Manager]資料，而不受用戶介面的限制。

>[!IMPORTANT]
>
>使用CDF檔案時，請注意下列限制：
>
>* 在設定CDF檔案傳送之前，請確定您擁有來自協力廠商資料提供者的適當權限，以匯出協力廠商特徵。 Audience Manager目前不支援向第三方資料提供者要求CDF檔案傳送匯出權限的使用者介面功能，因此請單獨聯絡他們。
>* 您不應將[!UICONTROL CDF]檔案當作代理來監控頁面流量、調解報表差異或進行帳單等。


## 快速入門 {#getting-started}

沒有可啟動[!UICONTROL CDF]檔案傳送的自助程式。 請連絡您的[!DNL Audience Manager]顧問或客戶服務以開始使用。 實作期間，您的[!DNL Audience Manager]代表將：

* 設定您的[!DNL Amazon S3]儲存貯體。
* 為檔案儲存貯體提供唯讀[!DNL S3]驗證憑證。 您將無法查看或訪問屬於其他客戶的目錄和檔案。

檔案通知和[!UICONTROL CDF]檔案將在準備下載時顯示在您的[!DNL S3]儲存貯體中。 您負責從指派的[!DNL S3]目錄監視和下載檔案。 請參閱[客戶資料摘要檔案處理通知](#cdf-file-processing-notifications)。

## 後續步驟 {#next-steps}

以下各節和[客戶資料摘要常見問題集](../faq/faq-cdf.md)可協助您更熟悉此服務。

## [!UICONTROL Customer Data Feed] 定義的內容  {#cdf-defined}

按外觀順序列出並定義[!UICONTROL CDF]檔案中的資料元素和陣列。 定義包含資料類型，但此資訊不屬於[!UICONTROL CDF]檔案。

## 定義 {#definitions}

[!UICONTROL CDF]檔案包含以下定義的部分或全部欄位。 如需內部檔案組織的相關資訊，請參閱[客戶資料摘要檔案結構](#cdf-file-structure)。

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
   <td colname="col3"> <p><span class="wintitle">資料收集伺服器</span>(DCS)處理CDF檔案的時間。 時間戳記使用<i>yyyy-mm-dd hh:mm:ss</i>格式，並以UTC時區設定。 </p> <p> <p>注意：事件時間<i>不是</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">頁面事件或事件本身呼叫的時間，雖然可能接近這些時間。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">檔案名稱中的DCS小時相關。 另請參閱<a href="#different-processing-times">客戶資料摘要檔案名稱時間和檔案內容時間……</a>。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>這是<span class="wintitle">不重複使用者ID</span>(UUID)，這是網站訪客的38位數裝置ID。 也請參閱 <a href="../reference/ids-in-aam.md">Audience Manager 內的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>數值 </p> </td> 
   <td colname="col3"> <p>觸發ID之容器的ID會同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>特徵ID陣列，包含訪客在事件呼叫中實現（符合資格）的所有特徵。 </p> <p>請注意，陣列可包含訪客之前已符合資格的特徵，以及透過此事件呼叫重新符合資格的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID的陣列，包含訪客在事件呼叫中實現（符合資格）的所有區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>擷取所有參數（變數、ID、索引鍵值配對、裝置廣告ID等）的字串 在事件呼叫時傳入。 </p> <p>簡短範例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>反向連結頁面的未編碼URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>在事件呼叫中擷取之訪客的IP位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>指派給網站訪客的<span class="keyword">Experience Cloud</span> ID(MID)。 另請參閱<a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和AdobeExperience PlatformIdentity服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>區段ID的陣列，包含先前實現的區段和訪客符合資格的新區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>數值陣列 </p> </td> 
   <td colname="col3"> <p>第一方和第三方特徵ID的陣列，包含訪客自上次產生資料摘要以來符合資格的先前實現特徵和新特徵。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案結構  {#cdf-file-structure}

列出並定義[!UICONTROL CDF]檔案的資料結構。 這包括資料序列、欄位分隔字元和分隔符號、資料檔案映射和範例檔案。

## 資料欄位標識符和序列{#identifiers-and-sequence}

[!UICONTROL CDF] 檔案不包含標示為的欄或欄位標題。相反，[!UICONTROL CDF]檔案定義了具有非打印[!DNL ASCII]字元的欄位和陣列。 此外，[!UICONTROL CDF]檔案還按特定順序列出每個欄位和陣列。 了解欄位識別碼和順序有助於正確剖析檔案。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF檔案元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>欄位分隔符號和分隔字元 </p> </td> 
   <td colname="col2"> <p>這些非列印字元定義CDF檔案的元素和結構： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a（ASCII <code> 001</code>或<code> ^A</code>）用非打印空間指示器分隔單個欄位中的資料。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b（ASCII <code> 002</code>或<code> ^B</code>）可分隔資料和陣列及請求參數。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c（ASCII <code> 003</code>或<code> ^C</code>）定義鍵值對。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位順序 </p> </td> 
   <td colname="col2"> <p> <p>重要：<span class="keyword">Audience Manager</span>保留在未來版本中新增欄位至CDF檔案結尾的權利。 這表示檔案解析系統的技術設計不應假設固定列數（儘管它可能假設現有列的順序固定）。 </p> </p> <p>CDF檔案中的資料會依下列順序顯示。 </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件時間 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">裝置 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已實現的特徵 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已實現區段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">要求參數 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 位址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud裝置ID（或MID）。 另請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有區段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特徵 </li> 
     </ol> </p> <p>如需欄位說明，請參閱<a href="#cdf-defined">定義的客戶資料摘要內容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 檔案圖  {#cdf-file-map}

[!UICONTROL CDF] 檔案資料會依下列順序顯示。

![](assets/sequence-map.png)

## 識別陣列

[!UICONTROL CDF]檔案中的陣列以`Ctrl + a`欄位分隔符開頭和結尾。 這會使陣列中的第一個元素看起來像獨立資料欄位。 例如，實現的[!UICONTROL traits]陣列以`^A1234`開頭。 陣列分隔字元和ID `^B5678`遵循此項。 因此，您可能會想到已實現[!UICONTROL traits]陣列中的第一個元素是ID 5678（因為它以`^B`開頭）。 但情況並非如此，因此您必須熟悉資料檔案的順序和結構。 即使實現的[!UICONTROL trait]陣列中的第一個元素（或[!UICONTROL CDF]檔案中的任何其他陣列）以`^A`開頭，檔案中的外觀或位置順序仍定義陣列的開頭。 而且，陣列中的第一個元素總是通過`^A`與前一個條目分離。

## 範例[!UICONTROL CDF]檔案{#sample-file}

範例[!UICONTROL CDF]檔案看起來可能類似於以下內容。 我們已在此範例中插入分行，以協助其符合頁面大小。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 檔案命名慣例  {#cdf-naming-conventions}

以下各節列出並定義[!UICONTROL CDF]檔案名中的元素。

## [!UICONTROL CDF] 檔案名：語法和範例  {#cdf-file-name}

典型的[!UICONTROL CDF]檔案名包含下列元素。 注意， *斜體*&#x200B;表示變數預留位置：

### 語法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### 範例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

在您的[!DNL S3]儲存貯體中，檔案會依合作夥伴ID([!UICONTROL PID])、日和小時以升序排序。

## [!UICONTROL CDF] 定義的檔案名元素  {#cdf-file-name-elements}

下表列出並定義[!UICONTROL CDF]檔案名中的元素。

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案名元素 </th> 
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
   <td colname="col2"> <p>唯讀儲存CDF檔案的S3儲存貯體名稱。 </p> </td> 
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
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>內部<span class="keyword">Audience Manager</span>進程ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip檔案副檔名。 CDF檔案會壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案處理通知  {#cdf-file-processing-notifications}

[!DNL Audience Manager] 將檔 `.info` 案寫入 [!DNL S3] 目錄，以告知您的( [!UICONTROL Customer Data File] )[!UICONTROL CDF]準備好下載的時間。`.info`檔案還包含有關[!UICONTROL CDF]檔案內容的[!DNL JSON]格式化元資料。 請參閱本節，了解此通知檔案使用的語法和欄位的相關資訊。

## 範例資訊檔案{#sample-info-file}

每個`.info`檔案都包含`Files`和`Totals`區段。 `Files`區段包含一個陣列，內含每個每小時檔案的特定度量。 `Totals`區段包含特定日期內所有[!UICONTROL CDF]檔案的匯總量度。 `.info`檔案的內容看起來可能類似於以下示例。

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

## 定義的資訊檔案欄位{#info-file-fields-defined}

下表列出並定義[!UICONTROL CDF] `.info`檔案中的元素。

### 檔案對象

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
   <td colname="col2"> <p>啟動包含CDF檔案相關元資料的陣列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag。 連字型大小後面的數字會顯示在多部分上傳期間用於建立檔案的部件數量。 <code> ETag</code>與檔案的MD5校驗和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>檔案名。 請參閱<a href="#cdf-naming-conventions">客戶資料摘要檔案命名慣例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>每個檔案的索引號。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 總計對象

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
   <td colname="col2"> <p>啟動包含所有CDF檔案匯總資料的對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>資料可用的日期。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>資料可用的小時。 使用UTC時區中設定的24小時格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>該日期所有CDF檔案的總大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上傳至S3目錄的檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案名稱時間和檔案內容時間不同  {#different-processing-times}

您的[!UICONTROL CDF]檔案包含檔案名和檔案內容中的時間戳。 這些時間戳記會為相同的[!UICONTROL CDF]檔案記錄不同的事件進程。 同一檔案的名稱和內容中會出現不同時間戳記，這種情況並不罕見。 了解每個時間戳記有助於您避免處理此資料或嘗試依時間排序時的常見錯誤。

## 找到[!UICONTROL CDF]檔案時間戳{#locating-timestamps}

[!UICONTROL CDF] 檔案在2個不同位置記錄的時間不同。

![](assets/cdf-timestamp.png)

## 了解時間戳記之間的差異{#understanding-timestamps}

下表提供關於[!UICONTROL CDF]檔案時間戳的其他詳細資訊，以及如何正確使用這些時間戳的資訊。

| 時間戳記位置 | 說明 |
|--- |--- |
| 檔案名稱 | [!DNL CDF]檔案名稱中的時間戳記會標籤[!DNL Audience Manager]開始準備要傳送的檔案的時間。 此時間戳記設定在[!DNL UTC]時區中。 它使用`hour=`參數，以24小時表示法將時間格式化為2位數小時。 此時間可能與檔案內容中記錄的事件時間不同。 使用[!DNL CDF]檔案時，有時您會發現您的[!DNL S3]貯體在特定小時內為空。 空貯體表示可能表示下列其中一項：<ul><li>那個鐘頭沒有資料。 </li><li> 我們的伺服器負載很重，無法處理特定小時的檔案。 當伺服器追上時，會將原本應在先前時間貯體中的檔案放入具有稍後時間值的貯體中。 例如，當應位於17小時儲存貯體的檔案出現在18小時儲存貯體中時（檔案名稱中為`hour=18`），您就會看到這個訊息。 在這種情況下，伺服器可能在17小時內開始處理您的檔案，但在該時間間隔內無法完成。 相反地，檔案會推送至下一個每小時時段。</li></ul><br>**重要**:請勿使用檔案名稱時間戳記依時間分組事件。如果需要按時間分組，請在檔案內容中使用`EventTime`時間戳記。 |
| 檔案內容 | [!DNL CDF]檔案內容中的時間戳記會標籤[!DNL Data Collection Servers]開始處理檔案的時間。 此時間戳記設定在[!DNL UTC]時區中。 它使用`EventTime`欄位，時間格式為&#x200B;*`yyyy-mm-dd hh:mm:ss`*。 此時間接近頁面上事件的實際時間，但可能與檔案名稱中的小時指標不同。<br> **提示**:與檔案 `hour=` 名稱中的時間戳記不同，您可以 `EventTime` 使用依時間分組資料。 |

>[!MORELIKETHIS]
>
>* [客戶資料摘要常見問題集](../faq/faq-cdf.md)

