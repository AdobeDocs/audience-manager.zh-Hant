---
description: S狀態目錄會保留.info檔案，其中包含有關上傳檔案的成功資訊和失敗資訊。檔案包含JSON格式的資料，狀態為狀態產生陣列。
seo-description: S狀態目錄會保留.info檔案，其中包含有關上傳檔案的成功資訊和失敗資訊。檔案包含JSON格式的資料，狀態為狀態產生陣列。
seo-title: 中繼資料檔案的狀態更新
solution: Audience Manager
title: 中繼資料檔案的狀態更新
uuid: 56a8e88a-41da-4d51-a21 e-2e-2ca7 fa2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Status Updates for Metadata Files{#status-updates-for-metadata-files}

The S3 status directory holds a `.info` file with success and failure information about your uploaded files. 檔案包含JSON格式的資料，狀態為狀態產生陣列。

`.info` 檔案的內容類似於此範例。

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

## Metadata Key-Value Pairs Defined {#key-value-pairs}

The following tables list and define the keys in the `Files` and `Summary` sections of a metadata status file.

**檔案陣列中的索引鍵**

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
   <td colname="col2"> <p>包含處理失敗的簡短說明。處理成功時，此欄位為空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>檔案大小為位元組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>The MD 5 checksum for the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>The name of the metadata file uploaded to your <code> meta</code> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PhotosatatType</code> </p> </td> 
   <td colname="col2"> <p>檔案包含之資料類型的人類可讀名稱。這是以檔案名稱中的子ID為基礎。 </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 父項</code> </p> </td> 
   <td colname="col2"> <p>檔案包含之資料類型的人類可讀名稱。這是以檔案名稱中的父ID為基礎。 </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 狀態</code> </p> </td> 
   <td colname="col2"> <p>傳回描述中繼資料檔案處理狀態的個文字值： </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> 成功</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> 失敗</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**摘要物件中的索引鍵**

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
   <td colname="col2"> <p>File processing date in <code><i>yyyy-mm-dd</i></code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>傳回一整天中描述所有檔案處理狀態的文字值： </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> 成功</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> 失敗</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> number失敗</code> </p> </td> 
   <td colname="col2"> <p>未成功處理的檔案數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> numberSuccess</code> </p> </td> 
   <td colname="col2"> <p>成功處理的檔案數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>傳回處理開始時間的人類可讀時間戳記。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> processingTimeX</code> </p> </td> 
   <td colname="col2"> <p>處理開始時間的UNIX時間戳記。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalByteSize</code> </p> </td> 
   <td colname="col2"> <p>當天所有中繼資料檔案的位元組總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> totalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>當天處理的所有檔案總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
