---
description: 每當處理傳入伺服器對伺服器檔案時，都會透過電子郵件傳送回執給合作夥伴解決方案，並（若已設定）傳送給合作夥伴。
seo-description: 每當處理傳入伺服器對伺服器檔案時，都會透過電子郵件傳送回執給合作夥伴解決方案，並（若已設定）傳送給合作夥伴。
seo-title: 傳入處理後傳送給合作夥伴的範例訊息
solution: Audience Manager
title: 傳入處理後傳送給合作夥伴的範例訊息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: 傳入資料傳輸
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---

# 傳入處理後傳送給合作夥伴的範例訊息{#sample-message-to-partners-after-inbound-processing}

每當處理傳入[!UICONTROL Server-to-Server]檔案時，都會透過電子郵件傳送回執給合作夥伴解決方案，並在已設定時傳送給合作夥伴。

<!-- r_inbound_message.xml -->

以下範例是範例電子郵件訊息。 消息下表描述了消息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>開始日期：aam-noreply@adobe.com  </b> </p> <p> <b>主題：Adobe Audience Manager伺服器對伺服器處理結果：</b> </p> <p> <b>親愛的Adobe合作夥伴：(ID:7)</b> <b></b> </p> <p> <b>我們已收到您的Adobe Audience Manager伺服器對伺服器檔案傳送</b> </p> <p> <b>檔案名：</b> <i></i> </p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>收到的記錄：40669900</b> </p> <p><b>格式錯誤：0</b> </p> <p> <b>無效的AAM ID:112  </b> </p> <p> <b>沒有相符的AAM ID:0  </b> </p> <p> <b>未實現特徵：26730823  </b> </p> <p> <b>已處理的記錄：40669900  </b> </p> <p> <b>儲存的記錄：13938958  </b> </p> <p> <b>總設備數：21  </b> </p> <p> <b>總訊號：918878926  </b> </p> <p> <b>未使用的訊號總計：660348376  </b> </p> <p> <b>已實現特徵總數：258086908  </b> </p> <p> <b>移除的特徵總數：0  </b> </p> <p> <b>總特徵驗證失敗：0  </b> </p> <p> <b>具有未通過驗證的特徵的使用者總數：0  </b> </p> <p> <b>作業開始時間：2018-05-17 18:07:49  </b> </p> <p> <b>作業結束時間：2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含與收到的電子郵件中的行相對應的行。

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折線圖 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 檔案名 </td> 
   <td colname="col2"> <p>Adobe為此合作夥伴收到且一起處理的所有入站檔案的清單。 在先前的範例電子郵件訊息中，合作夥伴ID為7，資料擁有者ID為901。 </p> <p>尾部號(1,2,3.....)是客戶或入站經銷商新增的分割號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收到的記錄 </td> 
   <td colname="col2"> <p>所有檔案中接收的記錄Adobe總數。 在大多數情況下，這應為傳入檔案中的行總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式錯誤 </td> 
   <td colname="col2"> <p>不符合預期格式的行數。 入站作業無法識別這些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無效的AAM ID </td> 
   <td colname="col2"> <p>不符合預期的38位數格式的Audience ManagerUUID數。 或檔案中傳送的Audience ManagerUUID不是數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 沒有相符的AAM ID </td> 
   <td colname="col2"> <p>Audience Manager找不到相符UUID的使用者總數。 這些檔案尚未同步ID，因此Audience Manager無法尋找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未實現特徵 </td> 
   <td colname="col2"> <p>線上沒有任何訊號對應至Audience Manager特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已處理的記錄 </td> 
   <td colname="col2"> <p>已處理的記錄Audience Manager總數。 在大多數情況下，此數字應與「已接收記錄」相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存的記錄 </td> 
   <td colname="col2"> <p>導致資料載入到系統中的記錄數=已處理的記錄數 — 格式錯誤 — 無效的AAM ID — 沒有相符的AAM ID — 未實現特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總裝置 </td> 
   <td colname="col2"> <p>已將資料載入到系統中的設備數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總訊號 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的訊號總數（處理記錄中的索引鍵/值組總數）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用的訊號總數 </td> 
   <td colname="col2"> <p>所有傳入檔案(未對應至Audience Manager特徵的索引鍵/值組)中所有使用者未使用的訊號總數。 在大多數情況下，這表示Audience Manager並未為訊號定義規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已實現特徵總數 </td> 
   <td colname="col2"> <p>根據訊號，所有傳入檔案中所有使用者的Audience Manager特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已移除特徵總數 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者已移除特徵的總數。 為獲得完整同步，如果使用者在先前的執行中有特徵，但在目前的執行中沒有，就會發生此情況。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總特徵驗證失敗 </td> 
   <td colname="col2"> <p>代表不屬於檔案名稱中宣告之資料來源的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有未通過驗證的特徵的用戶總數 </td> 
   <td colname="col2"> <p>具有未通過驗證的特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作業開始時間 </td> 
   <td colname="col2"> <p>入站作業開始的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作業結束時間 </td> 
   <td colname="col2"> <p>入站作業結束的時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>
