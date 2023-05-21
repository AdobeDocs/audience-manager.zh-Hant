---
description: 每當處理入站伺服器到伺服器檔案時，都會通過電子郵件將回執發送給合作夥伴解決方案，如果配置了，還會發送給合作夥伴。
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: 傳入處理後傳送給合作夥伴的範例訊息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 2%

---

# 傳入處理後傳送給合作夥伴的範例訊息{#sample-message-to-partners-after-inbound-processing}

每當入站 [!UICONTROL Server-to-Server] 處理檔案，通過電子郵件將回執發送給合作夥伴解決方案，如果配置了，將回執發送給合作夥伴。

<!-- r_inbound_message.xml -->

以下示例是電子郵件示例。 消息下表描述了消息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>發件人：aam-noreply@adobe.com </b> </p> <p> <b>主題：Adobe Audience Manager伺服器到伺服器處理結果：</b> </p> <p> <b>親愛的Adobe合作夥伴：(ID:7)</b> <b></b> </p> <p> <b>我們已收到您的Adobe Audience Manager伺服器到伺服器檔案交付</b> </p> <p> <b>檔案名：</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>收到的記錄：40669900</b> </p> <p><b>格式錯誤：0</b> </p> <p> <b>無效AAMID:112 </b> </p> <p> <b>無匹配AAMID:0 </b> </p> <p> <b>沒有發現任何特性：26730823 </b> </p> <p> <b>已處理的記錄：40669900 </b> </p> <p> <b>儲存的記錄：13938958 </b> </p> <p> <b>設備總數：21 </b> </p> <p> <b>總信號：918878926 </b> </p> <p> <b>未使用信號總數：660348376 </b> </p> <p> <b>已實現的總特徵：258086908 </b> </p> <p> <b>刪除的特徵總數：0 </b> </p> <p> <b>未通過驗證的總特徵數：0 </b> </p> <p> <b>具有未通過驗證的特徵的用戶總數：0 </b> </p> <p> <b>作業開始時間：2018-05-17 18:07:49 </b> </p> <p> <b>作業結束時間：2018-05-17 18:45:02</b> </p> </td> 
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
   <td colname="col2"> <p>Adobe為此合作夥伴接收並一起處理的所有入站檔案的清單。 在上一個示例電子郵件中，合作夥伴ID為7，資料所有者ID為901。 </p> <p>尾數(1,2,3......)是客戶或入站分發伺服器添加的拆分編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已收到的記錄 </td> 
   <td colname="col2"> <p>所有檔案中收到的記錄Adobe總數。 在大多數情況下，這應是入站檔案中的行總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式錯誤 </td> 
   <td colname="col2"> <p>與預期格式不匹配的行數。 入站作業無法識別這些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無效AAMID </td> 
   <td colname="col2"> <p>與預期的38位格式不匹配的Audience ManagerUUID的數量。 或者檔案中發送的Audience ManagerUUID不是數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無匹配AAMID </td> 
   <td colname="col2"> <p>Audience Manager找不到匹配UUID的用戶總數。 這些檔案尚未同步ID，因此Audience Manager無法查找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未實現任何特性 </td> 
   <td colname="col2"> <p>記錄數，其中行上的任何信號均不映射為Audience Manager特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已處理的記錄 </td> 
   <td colname="col2"> <p>已處理的記錄Audience Manager總數。 在大多數情況下，此數字應與「已接收記錄」相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存的記錄 </td> 
   <td colname="col2"> <p>導致資料載入到系統中的記錄數=已處理記錄 — 格式錯誤 — 無效AAMID — 無匹配AAMID — 未實現特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設備總數 </td> 
   <td colname="col2"> <p>將資料載入到系統中的設備數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總信號 </td> 
   <td colname="col2"> <p> 所有入站檔案中所有用戶的信號總數（已處理記錄中的密鑰/值對總數）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用信號總數 </td> 
   <td colname="col2"> <p>所有入站檔案(未映射到Audience Manager特徵的密鑰/值對)中所有用戶的未使用信號總數。 在大多數情況下，這意味著Audience Manager沒有為信號定義規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已實現性狀總數 </td> 
   <td colname="col2"> <p>所有入站檔案中所有用戶基於信號的Audience Manager特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 刪除的特徵總數 </td> 
   <td colname="col2"> <p> 所有入站檔案中所有用戶刪除的特徵總數。 對於完整同步，如果用戶在上次運行中具有該特性，但在當前運行中不具有該特性，則會發生這種情況。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未通過驗證的總特徵 </td> 
   <td colname="col2"> <p>表示不屬於在檔案名中聲明的資料源的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有未通過驗證的特徵的用戶總數 </td> 
   <td colname="col2"> <p>具有未通過驗證的特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作業開始時間 </td> 
   <td colname="col2"> <p>入站作業啟動的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作業結束時間 </td> 
   <td colname="col2"> <p>入站作業結束的時間。 </p> </td> 
  </tr> 
 </tbody> 
</table>
