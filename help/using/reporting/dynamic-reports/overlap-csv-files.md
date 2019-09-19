---
description: 重疊報表達 100 萬筆記錄上限時，您可以要求此報表的 .csv 檔案。當您看到「發生非預期錯誤」訊息時，報表可能已達到此限制。 請連絡客戶服務以要求壓縮的。csv檔案，您可以匯入該檔案，並在自己的資料庫系統中使用。 檔案可用於區段對區段、區段對特徵和特徵對特徵重疊報表。
seo-description: 重疊報表達 100 萬筆記錄上限時，您可以要求此報表的 .csv 檔案。當您看到「發生非預期錯誤」訊息時，報表可能已達到此限制。 請連絡客戶服務以要求壓縮的。csv檔案，您可以匯入該檔案，並在自己的資料庫系統中使用。 檔案可用於區段對區段、區段對特徵和特徵對特徵重疊報表。
seo-title: 重疊報表的CSV檔案
solution: Audience Manager
title: 重疊報表的CSV檔案
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# CSV Files for Overlap Reports{#csv-files-for-overlap-reports}

重疊報表達 100 萬筆記錄上限時，您可以要求此報表的 .csv 檔案。當您看到「發生非預期錯誤」訊息時，報表可能已達到此限制。 請連絡客戶服務以要求壓縮的。csv檔案，您可以匯入該檔案，並在自己的資料庫系統中使用。 檔案可用於區段對區段、區段對特徵和特徵對特徵重疊報表。

## 檔案名稱中繼資料 {#file-name-metadata}

下表列出並說明重疊。csv檔案中使用的檔案命名慣例和副檔名。 In the examples, *italics* indicates a variable placeholder.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 中繼資料元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檔案 擴充功能 </p> </td> 
   <td colname="col2"> <p>重疊報表檔案會壓縮為gzip，並具有 <code> .gz</code> 副檔名。 解壓縮後，您必 <code></code> 須將。csv副檔名新增至檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> <p>檔案名語法： </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">區段對區段檔案： <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_date范<i>圍</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">區段到特徵檔案： <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_date范<i>圍</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">特徵到特徵檔案： <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_date范<i>圍</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期範圍 </p> </td> 
   <td colname="col2"> <p>報表的日期範圍是5位數的ID，其中包括： </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> ,7天報告。 </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> ,30天報告。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多個檔案 </p> </td> 
   <td colname="col2"> <p>如果報表包含多個檔案，我們會遞增檔案名稱中的最後一位數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>範例 </p> </td> 
   <td colname="col2"> <p>單一報表的檔案名稱範例： </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">單日7天檔案： <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">單一30天檔案： <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>包含多個檔案之報表的檔案名稱範例： </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔案內容 {#file-contents}

在檔案中，字串資料用雙引號括起來。 請參閱以下模擬資料。 這已因為簡短和適合螢幕而截斷。

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## 區段對區段報表記錄 {#segment-segment-records}

區段對區段重疊報 [表的資料檔案包含](segment-segment-overlap-report.md) 下列記錄。

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
   <td colname="col2"> <p>您要比較的區段ID與基準區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>要與基準區段比較的區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>基線段的ID。 基線區段是您要與其他區段比較的區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>要與其他區段比較的基準區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 朗熱</code> </p> </td> 
   <td colname="col2"> <p>您可以取得7和30天回顧間隔的報表。 範圍 <code> EID</code> 對應於下方顯示的時間間隔。 </p> <p> 
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
   <td colname="col2"> <p>您要比較的區段與基準區段中的獨特使用者人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>基線段中的獨特用戶數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>基準區段與其他選擇進行比較之區段之間獨特使用者重疊的總計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>基準區段與其他選擇進行比較的區段之間的獨特使用者重疊百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區段對特徵報表記錄 {#segment-trait-records}

「區段對特徵重疊報 [表」的資料檔案包含](segment-trait-overlap-report.md) 下列記錄。

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
   <td colname="col2"> <p>特徵ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>特徵名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 ID包括： </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 第一方</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 第三方</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供程式</code> </p> </td> 
   <td colname="col2"> <p>資料提供者的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 朗熱</code> </p> </td> 
   <td colname="col2"> <p>您可以取得7和30天回顧間隔的報表。 範圍 <code> EID</code> 對應於下方顯示的時間間隔。 </p> <p> 
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
   <td colname="col2"> <p>所選區段中的獨特使用者數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>特徵中的獨特使用者數。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>在所選區段和特徵之間共用的獨特使用者數目。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>特徵和區段之間重疊的獨特使用者百分比。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>區段和特徵之間重疊的獨特使用者百分比。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特徵對特徵報表記錄 {#trait-trait-records}

「特徵對特徵重 [疊報表」的資料檔案](trait-trait-overlap-report.md) ，包含下列記錄。

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
   <td colname="col2"> <p>您要比較的特徵與基準特徵的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>您要比較的特徵與基準特徵的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>基線特徵的ID。 基線特徵是您要與其他特徵比較的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>您要與其他特徵比較的基準特徵的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 ID包括： </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 第一方</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 第三方</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 資料提供程式</code> </p> </td> 
   <td colname="col2"> <p>資料提供者的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 朗熱</code> </p> </td> 
   <td colname="col2"> <p>您可以取得7和30天回顧間隔的報表。 範圍 <code> EID</code> 對應於下方顯示的時間間隔。 </p> <p> 
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
   <td colname="col2"> <p>在所選特徵之間共用的獨特使用者數。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>基本特徵中的獨特使用者數。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間共用的獨特使用者數。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間重疊的獨特使用者百分比。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>在所選特徵之間重疊的獨特使用者百分比。 在UI報表中，當您將滑鼠指標暫留在熱圖結果中的某個特徵上時，此數字會出現在快顯視窗中。 </p> </td> 
  </tr> 
 </tbody> 
</table>
