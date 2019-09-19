---
description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
keywords: DPID;DPUUID;CID;UUID;uid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid
seo-description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
seo-title: Audience Manager中ID的索引
solution: Audience Manager
title: Audience Manager中ID的索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Audience Manager中ID的索引{#index-of-ids-in-audience-manager}

請參閱本檔案以取得Adobe Audience Manager ID的完整清單。

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 名稱和說明 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> Unique User ID </b> </p> <p> Audience manager與其互動的每個裝置建立關聯的38位數 <span class="keyword"> 的裝置ID</span> 。 每當您在Audience Manager UI中看到提及獨特使用者時，請考慮這個ID。<p><span class="keyword"> Audience Manager</span> 嘗試將此ID儲存為「demdex.net」第三方網域中的Cookie。</p> </p> <p>在事件呼叫中，Audience Manager UUID會以d_uuid訊號傳送。 </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>組織 ID</b> </p> <p>這是公司在註冊Experience cloud時所提供的ID。 若要瞭解如何尋找您公司的組織ID，請閱讀「組織與帳戶 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> 連結</a> 」，並向下捲動至「尋找組織ID」。</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>合作夥伴ID</b> </p> <p> PID是Audience manager中的公司 <span class="keyword"> ID</span>。 <span class="keyword"> Audience Manager</span> 將imsOrgId與PID關聯。 </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID、MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Experience Cloud ID（ECID，舊有縮寫MID或MCID）是從您的組織ID和 <span class="keyword"> Audience Manager</span> Unique User ID以數學方式衍生而來。 只要這些ID保持不變，為特定使用者產生正確的ECID就只是數學問題。 使用相同的組織ID和Audience Manager UUID時，您每次都會取得相同的ECID值。 您可以在Cookie和Experience Cloud ID檔案中 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 閱讀更多有關ECID的資訊</a> 。 </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>特徵ID</b> </p> <p>特徵ID可唯一識別 <span class="keyword"> Audience Manager環境中的特徵</span> 。 「特徵ID」會指派給使用者介面(UI)中的每個特徵。 </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>區段ID </b> </p> <p>區段ID可唯一識別 <span class="keyword"> Audience Manager環境中的區段</span> 。 區段ID會指派給UI中的每個區段。 </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>舊有區段ID </b> </p> <p>此ID可唯一識別 <span class="keyword"> Audience Manager環境中的區段</span> 。 舊有區段ID會指派給UI中的每個區段。 </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>目標ID </b> </p> <p>「目標ID」可唯一識別 <span class="keyword"> Audience Manager環境中的目標</span> 。 ID會指派給UI中的每個目標。 </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>資料來源ID（也稱為資料提供者ID）</b> </p> <p>「資料來源ID」是ID或特徵的命名空間。 ID會指派給UI中的每個資料來源（資料提供者）。 </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>資料提供者唯一使 </b> 用者ID( <b>亦稱為CRM ID)</b> </p> <p>第三方ID。 這是您在自己的CRM系統中識別使用者的ID。 您可以將DPUUID與 <span class="keyword"> Audience Manager</span> UUID同步，也可以在ID同步程式中從不同的 <span class="wintitle"> Data Sources</span> (DPID)同步DPUUID <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"></a>。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>請參閱上述的DPUUID。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>客戶ID，客戶ID整合代碼</b> </p> <p> <b>CID和CID_IC金鑰值配對會取代 <a href="../reference/cid.md"> DPID和DPUUID</a>。</b> 它們提供與DPID和DPUUID相同的函式，但效率更高，因為它們在單一索引鍵值對中包含資料提供者ID和使用者ID（或整合程式碼）。 </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>瑞達</li>
      <li>女傭</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>裝置廣告ID</b> </p> <p>要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 </p> </td> 
   <td colname="col3"> <p>IDFA、GAID、Roku ID、Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>裝置廣告ID - IDFA - iOS裝置</b> </p> <p> <b>IDFA</b> ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行iOS作業系統的裝置。 </p> </td> 
   <td colname="col3"> <p> 格式嚴格由32個大 <i>寫</i> 16進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>裝置廣告ID - GAID - android裝置</b> </p> <p><b>GAID</b> ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行Android作業系統的裝置。 </p> </td> 
   <td colname="col3"> <p>格式嚴格由32個小 <i>寫</i> 、十六進位數字組成，以5個組顯示，用連字元分隔，格式為8-4-4-4-12，共36個字元。 </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku串流裝置</b> </p> <p><b>GAID</b> RIDA ID是Roku裝置製造商提供的串流裝置識別碼。</p> </td>
   <td colname="col3"> <p>格式嚴格由32個小 <i>寫</i> 、十六進位數字組成，以5個組顯示，用連字元分隔，格式為8-4-4-4-12，共36個字元。 </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft廣告ID - MAID - Windows 10裝置</b> </p> <p><b>MAID</b> ID是Windows 10依每個裝置、每個使用者而產生的裝置識別碼。</p> </td>
   <td colname="col3"> <p>MAID的格式為字母數字字串。</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung裝置</b> </p> Samsung DUID是Samsung TV提供的裝置識別碼。</p> </td>
   <td colname="col3"> <p>Samsung DUID的格式為英數字串。</p></td>
  </tr>
 </tbody> 
</table>