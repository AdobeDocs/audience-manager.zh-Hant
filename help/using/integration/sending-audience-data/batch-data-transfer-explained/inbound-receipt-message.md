---
description: 每當處理傳入的伺服器對伺服器檔案時，收據會透過電子郵件傳送至合作夥伴解決方案，如果已設定，則會傳送給合作夥伴。
seo-description: 每當處理傳入的伺服器對伺服器檔案時，收據會透過電子郵件傳送至合作夥伴解決方案，如果已設定，則會傳送給合作夥伴。
seo-title: 傳入處理後給合作夥伴的範例訊息
solution: Audience Manager
title: 傳入處理後給合作夥伴的範例訊息
uuid: 69e3a8b3-8445-4f4c-8005-1a9ff15ae19a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

以下範例為範例電子郵件訊息。訊息下方的表格說明訊息中的各種行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>寄件者：aam-noreply@adobe.com </b> </p> <p> <b>主旨：Adobe Audience Manager Server-To-Server處理結果：</b> </p> <p> <b>親愛的Adobe合作夥伴：(ID：7)</b><b></b> </p> <p> <b>我們已收到您的Adobe Audience Manager Server-To-Server檔案傳送</b> </p> <p> <b>檔案名稱：</b><i></i> </p> <p> <b> s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368806402. sync</b> </p> <p> <b> s3n://&lt;<i>bucket_ name&gt;</i>/2018-05-16/ ftp_ dpm_7_901_13686520202. sync </b> </p> <p> <b>s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784404804804. sync </b> </p> <p> <b>s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368806403400640.sync </b> </p> <p> <b>s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784802. sync </b> </p> <p> <b>s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784803. sync </b> </p> <p> <b>s3n://&lt;<i>bracket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368806404404404. sync</b> </p> <p> <b>收到的記錄：40669900</b> </p> <p><b>格式錯誤：0</b> </p> <p> <b>無效的AAM ID：112 </b> </p> <p> <b>無相符的AAM ID：0 </b> </p> <p> <b>未實現特徵：26730823 </b> </p> <p> <b>已處理記錄：40669900 </b> </p> <p> <b>儲存的記錄：13938958 </b> </p> <p> <b>總裝置：21 </b> </p> <p> <b>總訊號：91887926 </b> </p> <p> <b>未使用的訊號總數：660348376 </b> </p> <p> <b>整體實現特性：258086908 </b> </p> <p> <b>移除的特性總計：0 </b> </p> <p> <b>總計特徵失敗：0 </b> </p> <p> <b>具有無法驗證之特性的使用者總數：0 </b> </p> <p> <b>工作開始時間：2018-05-1718：07：49 </b> </p> <p> <b>工作結束時間：2018-05-1718：45：02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含對應電子郵件訊息中行的行。

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
   <td colname="col2"> <p>Adobe收到Adobe收到之所有傳入檔案的清單。在先前的範例電子郵件訊息中，合作夥伴ID為7，資料擁有者ID為901。 </p> <p>尾數(1,2…)是客戶或傳入經銷商新增的分割數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收到記錄 </td> 
   <td colname="col2"> <p>Adobe在所有檔案中收到的記錄總數。在大多數情況下，這應該是傳入檔案中的總行數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式錯誤 </td> 
   <td colname="col2"> <p>不符合預期格式的行數。傳入的工作無法辨識這些線條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無效的AAM ID </td> 
   <td colname="col2"> <p>不符合預期38位數格式的Audience Manager UUID數目。或在檔案中傳送的Audience Manager UUID不是數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 無相符AAM ID </td> 
   <td colname="col2"> <p>Audience Manager找不到相符UUID的使用者總數。這些檔案尚未同步ID，因此Audience Manager無法查閱UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未實現特徵 </td> 
   <td colname="col2"> <p>行上所有訊號不會對應至Audience Manager特徵的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 處理記錄 </td> 
   <td colname="col2"> <p>Audience Manager處理的記錄總數。在大多數情況下，此數字應與「收到的記錄」相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存的記錄 </td> 
   <td colname="col2"> <p>導致資料載入系統=記錄處理的記錄數的記錄數-格式錯誤-無效AAM ID-無比對AAM ID-沒有任何特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 裝置總數 </td> 
   <td colname="col2"> <p>資料載入系統的裝置數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訊號總計 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者的訊號總數(處理記錄中的索引鍵/值配對總數)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用的總訊號 </td> 
   <td colname="col2"> <p>所有傳入檔案中所有使用者未使用的信號總數(未對應至Audience Manager特徵的索引鍵/值配對)。在大多數情況下，這表示Audience Manager沒有為訊號定義的規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實現的特性總計 </td> 
   <td colname="col2"> <p>Audience Manager的特徵，適用於所有傳入檔案的所有使用者根據訊號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 移除的特性總計 </td> 
   <td colname="col2"> <p> 所有傳入檔案中所有使用者移除之特性的總次數。若為完整同步，則會發生此情況：使用者在先前執行中具有特徵，但不在目前執行中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 總特徵無法驗證 </td> 
   <td colname="col2"> <p>代表檔案名稱中宣告之資料來源的特徵數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有無法驗證之特性的使用者總數 </td> 
   <td colname="col2"> <p>驗證失敗的記錄數。 </p> </td> 
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