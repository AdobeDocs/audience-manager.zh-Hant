---
description: 重疊報表達 100 萬筆記錄上限時，您可以要求此報表的 .csv 檔案。當您看到「發生意外錯誤」消息時，報告可能已達到此限制。 請與客戶服務部門聯繫，請求壓縮的.csv檔案，您可以導入該檔案並在自己的資料庫系統中使用該檔案。 檔案可用於段到段、段到特徵和特徵到特徵的重疊報告。
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: 重疊報表的 CSV 檔案
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 7%

---

# 重疊報表的 CSV 檔案{#csv-files-for-overlap-reports}

重疊報表達 100 萬筆記錄上限時，您可以要求此報表的 .csv 檔案。當您看到「發生意外錯誤」消息時，報告可能已達到此限制。 請與客戶服務部門聯繫，請求壓縮的.csv檔案，您可以導入該檔案並在自己的資料庫系統中使用該檔案。 檔案可用於段到段、段到特徵和特徵到特徵的重疊報告。

## 檔案名元資料 {#file-name-metadata}

下表列出並說明了重疊.csv檔案中使用的檔案命名約定和檔案副檔名。 在這些範例中，*斜體字*&#x200B;代表變數預留位置。

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元資料元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檔案 擴展 </p> </td> 
   <td colname="col2"> <p>重疊報告檔案壓縮後具有 <code> .gz</code> 檔案副檔名。 必須添加 <code> .csv</code> 解壓縮後擴展到檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> <p>檔案名語法： </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">段到段檔案： <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">段到特徵檔案： <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">特性到特性檔案： <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期範圍 </p> </td> 
   <td colname="col2"> <p>報表的日期範圍是5位ID，包括： </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> 為期7天的報告。 </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> 30天的報告。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多個檔案 </p> </td> 
   <td colname="col2"> <p>如果報表包含多個檔案，我們將增加檔案名中的最後一個數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>範例 </p> </td> 
   <td colname="col2"> <p>單個報表的檔案名示例： </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">單個7天檔案： <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">單個30天檔案： <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>包含多個檔案的報告的檔案名示例： </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案內容 {#file-contents}

在檔案中，字串資料用雙引號括起來。 請參閱下面的模擬資料。 已截斷此項，以簡化和適合螢幕。

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## 段到段報表記錄 {#segment-segment-records}

您的資料檔案 [段對段重疊報表](segment-segment-overlap-report.md) 包含以下記錄。

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>與基線段比較的段的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>要與基線段比較的段的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>基線段的ID。 基線段是要與其他段比較的段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>要與其他段比較的基線段的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以獲得7天和30天回顧間隔的報告。 的 <code> rangeid</code> 與下面所示的時間間隔相對應。 </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>:7天 </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>:30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>報表的處理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>與基線段比較的段中的唯一用戶數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>基線段中唯一用戶的數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>基線段與選定進行比較的其他段之間唯一用戶重疊的總計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>基線段和選定進行比較的其他段之間唯一用戶的重疊百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 段到特性報表記錄 {#segment-trait-records}

您的資料檔案 [段到特徵重疊報表](segment-trait-overlap-report.md) 包含以下記錄。

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>特徵ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>特徵名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式ID。 ID包括： </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以獲得7天和30天回顧間隔的報告。 的 <code> rangeid</code> 與下面所示的時間間隔相對應。 </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>:7天 </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>:30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>報表的處理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>所選段中的唯一用戶數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>特徵中的唯一用戶數。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>所選段和特徵之間共用的唯一用戶數。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>在特徵和段之間重疊的唯一用戶百分比。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>在段和特徵之間重疊的單個用戶百分比。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特質對特質報告記錄 {#trait-trait-records}

您的資料檔案 [特性與特性重疊報告](trait-trait-overlap-report.md) 包含以下記錄。

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 標籤 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>你比較的特徵的ID和基線特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>你比較的特徵的名稱和基線特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>基線特性的ID。 基線特徵是你想要與其他特徵比較的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>您正在比較的基線特性的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式ID。 ID包括： </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>您可以獲得7天和30天回顧間隔的報告。 的 <code> rangeid</code> 與下面所示的時間間隔相對應。 </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>:7天 </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>:30天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>報表的處理日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間共用的唯一用戶數。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>基本特性中的唯一用戶數。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間共用的唯一用戶數。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>重疊在所選特徵之間的唯一用戶百分比。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間重疊的單個用戶百分比。 在UI報告中，當您懸停在熱度映射結果中的某個特性上時，此數字將出現在彈出窗口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>
