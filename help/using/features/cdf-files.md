---
description: 有關客戶資料饋送(CDF)檔案的基本資訊以及有關如何開始的說明。 如果您有興趣接收CDF檔案或僅希望獲得更多資訊，請從此處開始。
keywords: 第二方資料；第二方資料；第二方資料；第二方資料
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: 客戶資料摘要
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

有關 [!UICONTROL Customer Data Feed] ([!UICONTROL CDF])檔案和有關如何開始的說明。 如果您有興趣接收 [!UICONTROL CDF] 檔案或只是想要更多資訊。

## 檔案內容和用途 {#file-contents-purpose}

[!UICONTROL CDF] 檔案包含的資料與 [!DNL Audience Manager] 事件呼叫 (`/event`) 傳送至我們伺服器的資料相同。包括用戶ID等資料， [!UICONTROL trait IDs]。 [!UICONTROL segment IDs]，以及事件調用捕獲的所有其他參數。 內部 [!DNL Audience Manager] 系統將事件資料處理到 [!UICONTROL CDF] 檔案，其內容組織為按設定順序顯示的欄位。 [!DNL Audience Manager] 嘗試生成 [!UICONTROL CDF] 每小時歸檔，並將它們儲存在一個安全、特定於客戶的儲存桶中 [!DNL Amazon S3] 伺服器。 我們提供這些檔案，以便您能夠 [!DNL Audience Manager] 超出用戶介面限制的資料。

>[!IMPORTANT]
>
>使用CDF檔案時請注意以下限制：
>
>* 在設定CDF檔案傳送之前，請確保您具有第三方資料提供商對導出第三方特徵的適當權限。 Audience Manager當前不支援用戶介面中向第三方資料提供程式請求CDF檔案傳遞導出權限的功能，因此請獨立聯繫他們。
>* 你不該 [!UICONTROL CDF] 檔案作為代理來監視頁流量、協調報表差異或計費等。


## 快速入門 {#getting-started}

沒有要啟動的自助服務進程 [!UICONTROL CDF] 檔案傳遞。 聯繫您 [!DNL Audience Manager] 咨詢顧問或客戶服務開始。 在實施過程中， [!DNL Audience Manager] 代表：

* 設定 [!DNL Amazon S3] 儲存桶。
* 提供只讀 [!DNL S3] 檔案儲存儲存桶的身份驗證憑據。 您將無法查看或訪問屬於其他客戶的目錄和檔案。

檔案通知和 [!UICONTROL CDF] 檔案將出現在 [!DNL S3] 當它們準備下載時儲存。 您負責監視和下載分配的檔案 [!DNL S3] 的子菜單。 請參閱[客戶資料摘要檔案處理通知](#cdf-file-processing-notifications)。

## 後續步驟 {#next-steps}

以下各節和 [客戶資料源常見問題](../faq/faq-cdf.md) 可以幫助您更熟悉此服務。

## [!UICONTROL Customer Data Feed] 定義的內容 {#cdf-defined}

列出並定義 [!UICONTROL CDF] 按外觀順序排列。 定義包括資料類型，但此資訊不是 [!UICONTROL CDF] 的子菜單。

>[!IMPORTANT]
>
>CDF配置中預設排除事件像素。 如果希望將事件像素包括在CDF檔案中，請確保在客戶保護請求中指定。 每個事件像素將作為CDF檔案中的唯一行填充。

## 定義 {#definitions}

A [!UICONTROL CDF] 檔案包含下面定義的部分或全部欄位。 有關內部檔案組織的資訊，請參見 [客戶資料饋送檔案結構](#cdf-file-structure)。

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
   <td colname="col2"> <p>時間戳 </p> </td> 
   <td colname="col3"> <p>CDF檔案由 <span class="wintitle"> 資料收集伺服器</span> (DCS)。 時間戳使用 <i>yyyy-mm-dd hh:mm:ss</i> 格式，並在UTC時區中設定。 </p> <p> <p>注：事件時間 <i>不是</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">頁面事件或事件的時間自行調用，儘管它可能接近這些時間。 </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">與檔案名中的DCS小時相關。 另請參見 <a href="#different-processing-times"> 客戶資料饋送檔案名時間和檔案內容時間……</a>。 </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>這是 <span class="wintitle"> 唯一用戶ID</span> (UUID)，是站點訪問者的38位設備ID。 也請參閱 <a href="../reference/ids-in-aam.md">Audience Manager 內的 ID 索引</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>數值 </p> </td> 
   <td colname="col3"> <p>觸發ID同步的容器的ID。 僅當在 <i>d_nsid</i> 欄位。 否則，CDF檔案中將不包含預設值0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>數字陣列 </p> </td> 
   <td colname="col3"> <p>一組特性ID，包含訪問者在事件調用中實現（限定）的所有特性。 </p> <p>請注意，陣列可以包含訪問者以前已通過此事件調用確認的特徵，以及通過此事件調用重新確認這些特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>數字陣列 </p> </td> 
   <td colname="col3"> <p>一組段ID，包含訪問者在事件調用中實現（限定）的所有段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>捕獲所有參數（變數、ID、鍵值對、設備通告ID等）的字串 在事件呼叫中傳入。 </p> <p>縮寫示例： </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>引用頁的未編碼URL（如果有）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>在事件調用中捕獲的訪問者的IP地址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>的 <span class="keyword"> Experience Cloud</span> 分配給站點訪問者的ID(MID)。 另請參見 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和AdobeExperience Platform標識服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>數字陣列 </p> </td> 
   <td colname="col3"> <p>一組段ID，包含先前實現的段和訪問者限定的新段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>數字陣列 </p> </td> 
   <td colname="col3"> <p>一組第一和第三方特性ID，包含訪問者自上次生成資料饋送以來所限定的先前實現的特性和新特性。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案結構 {#cdf-file-structure}

列出並定義 [!UICONTROL CDF] 的子菜單。 這包括資料序列、欄位分隔符和分隔符、資料檔案映射和示例檔案。

## 資料欄位標識符和序列 {#identifiers-and-sequence}

[!UICONTROL CDF] 檔案不包含已標籤的列或欄位標題。 相反， [!UICONTROL CDF] 檔案定義欄位和陣列，但不打印 [!DNL ASCII] 字元。 另外， [!UICONTROL CDF] 檔案按特定順序列出每個欄位和陣列。 瞭解欄位標識符和順序將幫助您正確分析檔案。

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF檔案元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>欄位分隔符和分隔符 </p> </td> 
   <td colname="col2"> <p>這些非打印字元定義CDF檔案的元素和結構： </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a(ASCII) <code> 001</code> 或 <code> ^A</code>)使用非打印空間指示器分隔各個欄位中的資料。 </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b(ASCII) <code> 002</code> 或 <code> ^B</code>)分離資料和陣列和請求參數。 </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c(ASCII) <code> 003</code> 或 <code> ^C</code>)定義鍵值對。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位序列 </p> </td> 
   <td colname="col2"> <p> <p>重要提示： <span class="keyword"> Audience Manager</span> 保留在將來版本中將新欄位添加到CDF檔案末尾的權利。 這意味著檔案分析系統的技術設計不應假定列數固定（儘管它可能假定現有列的順序固定）。</p> </p> <p>CDF檔案中的資料按如下所示的順序顯示。/N可能會代替這些欄位中的任何一個，表示空值。</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">事件時間 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">裝置 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">容器 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">已實現的特性 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">已實現的段 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">要求參數 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 位址 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud設備ID（或MID）。 另請參見 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Adobe Experience Platform身份服務</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">所有段 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">所有特徵 </li> 
     </ol> </p> <p>有關欄位說明，請參見 <a href="#cdf-defined"> 已定義客戶資料饋送內容</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 檔案映射 {#cdf-file-map}

[!UICONTROL CDF] 檔案資料按如下所示的順序顯示。

![](assets/sequence-map.png)

## 識別陣列

在 [!UICONTROL CDF] 檔案以開頭和結尾 `Ctrl + a` 欄位分隔符。 這使陣列中的第一個元素看起來像獨立資料欄位。 例如， [!UICONTROL traits] 陣列開始於 `^A1234`。 陣列分隔符和ID `^B5678` 在此條目後。 因此，你可能會忍不住認為，在已實現的 [!UICONTROL traits] 陣列為ID 5678(因為它以 `^B`)。 但情況並非如此，因此您需要熟悉資料檔案的順序和結構。 即使實現 [!UICONTROL trait] 陣列(或 [!UICONTROL CDF] 檔案)開頭 `^A`，檔案中外觀或位置的順序定義陣列的開始。 並且，陣列中的第一元素總是通過 `^A`。

## 示例 [!UICONTROL CDF] 檔案 {#sample-file}

示例 [!UICONTROL CDF] 檔案可能與以下內容類似。 我們已在此示例中插入換行符，以幫助它適應頁面。

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 檔案命名約定 {#cdf-naming-conventions}

下面的部分列出並定義 [!UICONTROL CDF] 檔案名。

## [!UICONTROL CDF] 檔案名：語法和示例 {#cdf-file-name}

典型 [!UICONTROL CDF] 檔案名包含下面列出的元素。 注意， *斜體* 指示變數佔位符：

### 語法

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### 範例

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

在 [!DNL S3] 儲存桶，檔案按合作夥伴ID([!UICONTROL PID])、日和小時。

## [!UICONTROL CDF] 定義的檔案名元素 {#cdf-file-name-elements}

下表列出並定義 [!UICONTROL CDF] 檔案名。

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
   <td colname="col2"> <p>這是AmazonS3伺服器上CDF檔案的預設根儲存桶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>保存CDF檔案的只讀S3儲存桶的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>處理檔案的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>以24小時表示並在UTC時區中設定的時間值。 另請參見 <a href="#different-processing-times"> 客戶資料饋送檔案名時間和檔案內容時間……</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>你的搭檔ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>標識檔案序列的值。 序列增量如下：0_0_0,0_1_0,0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip檔案副檔名。 CDF檔案被gzip壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案處理通知 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 寫 `.info` 檔案 [!DNL S3] 目錄，通知您 [!UICONTROL Customer Data File] ([!UICONTROL CDF])已準備好下載。 的 `.info` 檔案也包括 [!DNL JSON] 格式化元資料，關於您的 [!UICONTROL CDF] 的子菜單。 有關此通知檔案使用的語法和欄位的資訊，請查看本節。

## 示例資訊檔案 {#sample-info-file}

每個 `.info` 檔案包含 `Files` 和 `Totals` 的子菜單。 的 `Files` 節包含一個陣列，該陣列保存每個小時檔案的特定度量。 的 `Totals` 部分包含所有 [!UICONTROL CDF] 檔案。 您的 `.info` 檔案可能與以下示例類似。

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

## 定義的資訊檔案欄位 {#info-file-fields-defined}

下表列出並定義 [!UICONTROL CDF] `.info` 的子菜單。

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
   <td colname="col2"> <p>啟動包含有關CDF檔案的元資料的陣列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>AmazonS3 ETag 連字元後面的數字顯示在多部件上載期間用於生成檔案的部件數。 的 <code> ETag</code> 與檔案的MD5校驗和不相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>檔案名。 請參閱 <a href="#cdf-naming-conventions"> 客戶資料源檔案命名約定</a>。 </p> </td> 
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
   <td colname="col2"> <p>啟動包含有關所有CDF檔案的聚合資料的對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>資料可用的日期。 使用 <i>yyyy-mm-dd</i> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>資料可用的小時數。 使用UTC時區中設定的24小時格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>該日期的所有CDF檔案的總大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>上載到S3目錄的檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 檔案名時間和檔案內容時間不同 {#different-processing-times}

您 [!UICONTROL CDF] 檔案包含檔案名和檔案內容中的時間戳。 這些時間戳記錄相同事件的不同進程 [!UICONTROL CDF] 的子菜單。 在同一檔案的名稱和內容中看到不同的時間戳的情況並不少見。 瞭解每個時間戳有助於避免在處理此資料或嘗試按時間排序時出現的常見錯誤。

## 定位 [!UICONTROL CDF] 檔案時間戳 {#locating-timestamps}

[!UICONTROL CDF] 檔案在兩個不同位置記錄的時間不同。

![](assets/cdf-timestamp.png)

## 理解時間戳的區別 {#understanding-timestamps}

下表提供了有關您的 [!UICONTROL CDF] 檔案時間戳以及有關如何正確使用它們的資訊。

| 時間戳位置 | 說明 |
|--- |--- |
| 檔案名稱 | 您的時間戳 [!DNL CDF] 檔案名標籤 [!DNL Audience Manager] 已開始準備檔案以供傳遞。 此時間戳在 [!DNL UTC] 時區。 它使用 `hour=` 參數，時間格式為2位小時，以24小時表示。 此時間可以不同於檔案內容中記錄的事件時間。 使用時 [!DNL CDF] 檔案，有時你會發現 [!DNL S3] 桶在特定小時內是空的。 空桶裝置可以表示以下任一種：<ul><li>沒有那個小時的資料。 </li><li> 我們的伺服器負載很重，無法處理特定小時的檔案。 當伺服器趕上時，它會將本應放在較早時段檔案中的檔案放入具有稍後時間值的儲存桶中。 例如，在18小時儲存桶中出現本應在17小時儲存桶中的檔案時，您會看到這一點(帶 `hour=18` 的子菜單。 在這種情況下，伺服器可能在17小時內開始處理您的檔案，但無法在該時間間隔內完成。 相反，檔案會被推入到下一個小時時段。</li></ul><br>**重要**:不要使用檔案名時間戳按時間對事件進行分組。 如果需要按時間分組，請使用 `EventTime` 檔案內容中的時間戳。 |
| 檔案內容 | 您的時間戳 [!DNL CDF] 檔案內容標籤 [!DNL Data Collection Servers] 已開始處理檔案。 此時間戳在 [!DNL UTC] 時區。 它使用 `EventTime` 欄位，其格式為 *`yyyy-mm-dd hh:mm:ss`*。 此時間接近頁面上事件的實際時間，但可能與檔案名中的小時指示器不同。 <br> **提示**:與 `hour=` 在檔案名中，您可以使用 `EventTime` 按時間分組資料。 |

>[!MORELIKETHIS]
>
>* [客戶資料摘要常見問題集](../faq/faq-cdf.md)

