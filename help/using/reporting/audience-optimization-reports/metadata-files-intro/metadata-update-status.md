---
description: S3狀態目錄包含。info檔案，內含您已上傳檔案的成功與失敗資訊。 檔案包含JSON格式的資料，其狀態結果為陣列。
seo-description: S3狀態目錄包含。info檔案，內含您已上傳檔案的成功與失敗資訊。 檔案包含JSON格式的資料，其狀態結果為陣列。
seo-title: 中繼資料檔案的狀態更新
solution: Audience Manager
title: 中繼資料檔案的狀態更新
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 中繼資料檔案的狀態更新{#status-updates-for-metadata-files}

S3狀態目錄包含一個檔案， `.info` 內含您已上傳檔案的成功與失敗資訊。 檔案包含JSON格式的資料，其狀態結果為陣列。

您檔案的內 `.info` 容看起來類似此範例。

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## 定義的元資料鍵值對 {#key-value-pairs}

下表列出並定義中繼資料狀態檔 `Files` 案 `Summary` 中和區段的索引鍵。

**檔案陣列中的鍵**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 說明</code> </p> </td> 
   <td colname="col2"> <p>包含處理失敗原因的簡短說明。 處理成功時，此欄位為空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>上傳至中繼目錄之中繼資料檔案的MD 5 <code> 校驗</code> 和。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 檔案名稱</code> </p> </td> 
   <td colname="col2"> <p>上傳至中繼目錄的中繼資料檔案 <code> 名稱</code> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 中繼資料類型</code> </p> </td> 
   <td colname="col2"> <p>您檔案所含資料類型的可讀名稱。 它以檔案名稱中的子ID為基礎。 </p> <p>請參閱 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 中繼資料檔案的命名慣例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 父代</code> </p> </td> 
   <td colname="col2"> <p>您檔案所含資料類型的可讀名稱。 它以檔案名稱中的父ID為基礎。 </p> <p>請參閱 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 中繼資料檔案的命名慣例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 狀態</code> </p> </td> 
   <td colname="col2"> <p>傳回2個文字值，說明中繼資料檔案的處理狀態： </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> 成功</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> 失敗</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**摘要對象中的鍵**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 日</code> </p> </td> 
   <td colname="col2"> <p>yyyy-mm-dd格式 <code><i>的檔案處理日期</i></code> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>傳回2個文字值，說明整天所有檔案的處理狀態： </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> 成功</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> 失敗</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>未成功處理的檔案數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>成功處理的檔案數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>傳回處理開始時間的可人讀時間戳記。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>用於處理開始時間的UNIX時間戳記。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>當天所有中繼資料檔案的位元組總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>當天處理的所有檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
