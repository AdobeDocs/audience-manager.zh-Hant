---
description: 每當處理傳入的伺服器對伺服器檔案時，會透過電子郵件傳送回執給合作夥伴解決方案，如果已設定，則會傳送回執給合作夥伴。
seo-description: 每當處理傳入的伺服器對伺服器檔案時，會透過電子郵件傳送回執給合作夥伴解決方案，如果已設定，則會傳送回執給合作夥伴。
seo-title: 傳入處理後傳送給合作夥伴的範例訊息
solution: Audience Manager
title: 傳入處理後傳送給合作夥伴的範例訊息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# 傳入處理後傳送給合作夥伴的範例訊息{#sample-message-to-partners-after-inbound-processing}

每當處理傳 [!UICONTROL Server-to-Server] 入檔案時，收據會透過電子郵件傳送給合作夥伴解決方案，如果已設定，則會傳送給合作夥伴。

<!-- r_inbound_message.xml -->

以下範例是範例電子郵件訊息。 消息下表說明了消息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>寄件者：aam-noreply@adobe.com </b> </p> <p> <b>主旨：Adobe Audience Manager伺服器對伺服器的處理結果：</b> </p> <p> <b>親愛的Adobe合作夥伴：(ID:7)</b><b></b> </p> <p> <b>我們已收到您的Adobe Audience Manager伺服器對伺服器檔案傳送</b> </p> <p> <b></b> 檔案名： <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>收到的記錄：40669900</b> </p> <p><b>格式錯誤：0</b> </p> <p> <b>無效的AAM ID:112 </b> </p> <p> <b>沒有相符的AAM ID:0 </b> </p> <p> <b>未實現特徵：26730823 </b> </p> <p> <b>已處理的記錄：40669900 </b> </p> <p> <b>儲存記錄：13938958 </b> </p> <p> <b>裝置總數：21 </b> </p> <p> <b>總信號：918878926 </b> </p> <p> <b>未使用信號總數：660348376 </b> </p> <p> <b>已實現特徵總數：258086908 </b> </p> <p> <b>已移除特徵總數：0 </b> </p> <p> <b>總特徵數驗證失敗：0 </b> </p> <p> <b>具有未通過驗證的特徵的用戶總數：0 </b> </p> <p> <b>工作開始時間：2018-05-17 18:07:49 </b> </p> <p> <b>工作結束時間：2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含與收到的電子郵件中各行對應的行。

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折線圖 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名稱 </td> 
   <td colname="col2"> <p>Adobe為此合作夥伴收到並一起處理的所有傳入檔案清單。 在先前的範例電子郵件訊息中，合作夥伴ID為7，資料擁有者ID為901。 </p> <p>尾數(1,2,3...)是客戶或傳入配銷商新增的分割數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收到的記錄 </td> 
   <td colname="col2"> <p>Adobe在所有檔案中收到的記錄總數。 在大多數情況下，這應該是傳入檔案中的行數總計。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式錯誤 </td> 
   <td colname="col2"> <p>不符合預期格式的行數。 入站任務無法識別這些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無效的AAM ID </td> 
   <td colname="col2"> <p>不符合預期38位元格式的Audience Manager UUID數。 或者，檔案中傳送的Audience Manager UUID不是數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無相符的AAM ID </td> 
   <td colname="col2"> <p>Audience manager找不到相符UUID的使用者總數。 這些檔案尚未同步ID，因此Audience manager無法尋找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未實現特徵 </td> 
   <td colname="col2"> <p>行上沒有任何訊號對應至Audience manager特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已處理的記錄 </td> 
   <td colname="col2"> <p>Audience manager處理的記錄總數。 在大多數情況下，此數字應與「收到的記錄」相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存記錄 </td> 
   <td colname="col2"> <p>導致資料載入系統的記錄數=記錄已處理——格式錯誤——無效的AAM ID —— 無符合的AAM ID —— 無特徵已實現。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 裝置總數 </td> 
   <td colname="col2"> <p>已將資料載入到系統的設備數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總信號 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的訊號總數（處理記錄中的金鑰／值配對總數）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用信號總數 </td> 
   <td colname="col2"> <p>所有傳入檔案（未對應至Audience manager特徵的索引鍵／值配對）中所有使用者的未使用訊號總數。 在大多數情況下，這表示Audience manager沒有為訊號定義規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已實現特徵總數 </td> 
   <td colname="col2"> <p>根據訊號，所有傳入檔案中所有使用者的Audience manager特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已移除的特徵總數 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的移除特徵總數。 對於完整同步，如果使用者在先前執行中具有特性，但在目前執行中沒有，就會發生此情況。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總特徵數驗證失敗 </td> 
   <td colname="col2"> <p>代表不屬於在檔案名稱中宣告之資料來源的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有未通過驗證的特徵的用戶總數 </td> 
   <td colname="col2"> <p>具有未通過驗證的特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作開始時間 </td> 
   <td colname="col2"> <p>入站作業開始的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作結束時間 </td> 
   <td colname="col2"> <p>入站作業結束的時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>