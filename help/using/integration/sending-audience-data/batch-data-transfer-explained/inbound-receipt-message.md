---
description: 每當處理傳入的伺服器對伺服器檔案時，系統都會透過電子郵件將回條傳送給合作夥伴解決方案，並傳送給合作夥伴（若已設定）。
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: 傳入處理後傳送給合作夥伴的範例訊息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# 傳入處理後傳送給合作夥伴的範例訊息{#sample-message-to-partners-after-inbound-processing}

每當處理輸入[!UICONTROL Server-to-Server]檔案時，會透過電子郵件將收據傳送給合作夥伴解決方案，若已設定，則傳送給合作夥伴。

<!-- r_inbound_message.xml -->

以下範例是範例電子郵件訊息。 訊息下方的表格說明訊息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>來自： aam-noreply@adobe.com </b> </p> <p> <b>主旨： Adobe Audience Manager伺服器對伺服器處理結果： </b> </p> <p> <b>親愛的Adobe夥伴： （識別碼：7）</b> <b></b> </p> <p> <b>我們已收到您的Adobe Audience Manager伺服器對伺服器檔案傳遞</b> </p> <p> <b>檔案名稱：</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>已接收的記錄： 40669900</b> </p> <p><b>格式錯誤： 0</b> </p> <p> <b>無效的AAM識別碼： 112 </b> </p> <p> <b>沒有相符的AAM ID： 0 </b> </p> <p> <b>未實現任何特徵： 26730823 </b> </p> <p> <b>個處理的記錄： 40669900 </b> </p> <p> <b>儲存的記錄： 13938958 </b> </p> <p> <b>裝置總數： 21 </b> </p> <p> <b>訊號總數： 918878926 </b> </p> <p> <b>未使用的訊號總數： 660348376 </b> </p> <p> <b>已實現特徵總數： 258086908 </b> </p> <p> <b>移除的特徵總數： 0 </b> </p> <p> <b>已失敗驗證的特徵總數： 0 </b> </p> <p> <b>具有驗證失敗之特徵的使用者總數： 0 </b> </p> <p> <b>工作開始時間： 2018-05-17 18:07:49 </b> </p> <p> <b>工作結束時間： 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含與已接收電子郵件訊息中的行對應的列。

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
   <td colname="col2"> <p>Adobe為此合作夥伴收到且一起處理的所有傳入檔案清單。 在上一個範例電子郵件訊息中，合作夥伴ID為7，資料擁有者ID為901。 </p> <p>機尾編號(1,2，3...)是客戶或入站分銷商新增的分割編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已收到的記錄 </td> 
   <td colname="col2"> <p>Adobe在所有檔案中接收的記錄總數。 在大多數情況下，這應該是傳入檔案中的總行數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式錯誤 </td> 
   <td colname="col2"> <p>不符合預期格式的行數。 傳入工作無法識別這些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AAM ID無效 </td> 
   <td colname="col2"> <p>不符合預期38位數格式的Audience ManagerUUID數量。 或者檔案中傳送的Audience ManagerUUID不是數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 沒有相符的AAM ID </td> 
   <td colname="col2"> <p>Audience Manager找不到相符UUID的使用者總數。 這些檔案尚未進行ID同步，因此Audience Manager無法查詢UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未實現任何特徵 </td> 
   <td colname="col2"> <p>折線圖上沒有任何訊號對應至Audience Manager特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已處理的記錄 </td> 
   <td colname="col2"> <p>Audience Manager處理的記錄總數。 在大多數情況下，此數字應該與「收到的記錄」相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存的記錄 </td> 
   <td colname="col2"> <p>將資料載入系統的記錄數=處理的記錄 — 格式錯誤 — 無效的AAM ID — 沒有相符的AAM ID — 未實現特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 裝置總數 </td> 
   <td colname="col2"> <p>資料已載入系統的裝置數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訊號總數 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的訊號總數（已處理記錄中的索引鍵/值組總數）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用的訊號總數 </td> 
   <td colname="col2"> <p>所有傳入檔案(未對應至Audience Manager特徵的索引鍵/值組)中所有使用者的未使用訊號總數。 在大多數情況下，這表示Audience Manager並未定義訊號的規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已實現特徵總數 </td> 
   <td colname="col2"> <p>根據訊號的所有傳入檔案中所有使用者的Audience Manager特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已移除特徵總數 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的已移除特徵總數。 對於完整同步，如果使用者在上次執行中有特徵，但在目前執行中沒有，則會發生這種情況。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 驗證失敗的特徵總數 </td> 
   <td colname="col2"> <p>代表不屬於在檔案名稱中宣告之資料來源的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有驗證失敗之特徵的使用者總數 </td> 
   <td colname="col2"> <p>具有驗證失敗之特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作開始時間 </td> 
   <td colname="col2"> <p>傳入工作開始的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作結束時間 </td> 
   <td colname="col2"> <p>傳入工作結束的時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>
