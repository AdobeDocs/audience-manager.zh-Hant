---
description: 請參閱本文件以取得完整的Adobe Audience Manager ID清單。
keywords: DPID；DPUUID；CID；UUID；uuid；uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid
seo-description: 請參閱本文件以取得完整的Adobe Audience Manager ID清單。
seo-title: Audience Manager中ID的索引
solution: Audience Manager
title: Audience Manager中ID的索引
uuid: 292185ec-7c6a-414b-ab17-800c21 cb1 f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Audience Manager中ID的索引{#index-of-ids-in-audience-manager}

請參閱本文件以取得完整的Adobe Audience Manager ID清單。

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
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> 獨特使用者ID </b> </p> <p> <span class="keyword"> Audience Manager</span> 與每個與其互動的裝置相關聯的數字38位數裝置ID。每當您在Audience Manager UI中看到對獨特使用者的提及時，請考慮此ID。<p><span class="keyword"> Audience Manager</span> 嘗試將此ID儲存為「demdex. net」第三方網域中的Cookie。</p> </p> <p>Audience Manager UUID會在事件呼叫中傳送，作為d_ uuid訊號。 </p> </td> 
   <td colname="col3"> <p><code> demdex=079552616528032901402302505272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>imsOrgID </p> </td> 
   <td colname="col2"> <p> <b>組織 ID</b> </p> <p>這是公司在註冊Experience Cloud時提供的ID。若要瞭解如何找到公司的組織ID，請閱讀 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> 組織和帳戶連結</a> 並向下捲動以尋找組織ID。</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>合作夥伴ID</b> </p> <p> PID是Audience Manager中 <span class="keyword"> 的公司ID</span>。<span class="keyword"> Audience Manager</span> 會將iOS ID關聯至PID。 </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID、MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Experience Cloud ID(ECID、舊版縮寫MID或MCID)是以數學方式從您的組織ID和 <span class="keyword"> Audience Manager</span> 獨特使用者ID中衍生出來。只要這些ID維持不變，為特定使用者產生適當的ECID就只是數學問題。使用相同的組織ID和Audience Manager UUID，每次都能獲得相同的EID值。您可以在 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookie和Experience Cloud ID</a> 文件中閱讀更多有關ECID的資訊。 </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>特徵ID</b> </p> <p>特徵ID可唯一識別 <span class="keyword"> Audience Manager</span> 環境中的特徵。使用者介面(UI)中會指派特徵ID給每個特徵。 </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>區段ID </b> </p> <p>區段ID可唯一識別 <span class="keyword"> Audience Manager</span> 環境中的區段。區段ID會指派給UI中的每個區段。 </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cSegID </p> </td> 
   <td colname="col2"> <p> <b>舊版區段ID </b> </p> <p>此ID可唯一識別 <span class="keyword"> Audience Manager</span> 環境中的區段。「舊版區段ID」會指派給UI中的每個區段。 </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destiD </p> </td> 
   <td colname="col2"> <p> <b>目的地ID </b> </p> <p>目標ID可唯一識別 <span class="keyword"> Audience Manager</span> 環境中的目的地。ID會指派給UI中的每個目的地。 </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>資料來源ID(也稱為資料提供者ID)</b> </p> <p>「資料來源ID」是ID或特徵的名稱空間。ID會指派給UI中的每個資料來源(資料提供者)。 </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>資料提供者唯一使用者ID( </b><b>也稱為CRM ID)</b> </p> <p>第三方ID。這是您在自己的CRM系統中識別使用者的ID。您可以將DPUUID與 <span class="keyword"> Audience Manager</span> UUID同步，而且您可以在ID同步程序中，從不同 <span class="wintitle"> 的Data Sources</span><a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> (DPIDs)同步DPUUID</a>。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>請參閱上方的DPUUID。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID、CID_ IC </p> </td>
   <td colname="col2"> <p> <b>客戶ID、客戶ID整合代碼</b> </p> <p> <b>CID和CID_ IC金鑰-值對 <a href="../reference/cid.md"> 取代DPID和DPUUID</a>。</b> 它們提供與DPID和DPUUID相同的功能，但較有效率，因為它們包含資料供應商ID和使用者ID(或整合程式碼)，以單一索引鍵值配對。 </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7clib7feb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>裝置廣告ID</b> </p> <p>要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 </p> </td> 
   <td colname="col3"> <p>IDFA、GAID、Roku ID、Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>裝置廣告ID- IDFA- iOS裝置</b> </p> <p> <b>IDFA</b> ID是行動裝置識別碼，由裝置製造商提供。這些ID代表執行iOS作業系統的裝置。 </p> </td> 
   <td colname="col3"> <p> 格式嚴格由32 <i>個大寫</i> 十六進位數字組成，顯示於五個群組並以連字號分隔，格式為8-4-4-4-12，總共36個字元。 </p> <p><code> AEBE52E7-03EE-455A-B3 C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>裝置廣告ID- GAID- Android裝置</b> </p> <p><b>GAID</b> ID是行動裝置識別碼，由裝置製造商提供。這些ID代表執行Android作業系統的裝置。 </p> </td> 
   <td colname="col3"> <p>格式嚴格由32 <i>個小寫</i> 十六進位數字組成，顯示於五個群組並以連字號分隔，格式為8-4-4-4-12，總共36個字元。 </p> <p> <code> e4fe9bde-ca0-47b6-908d-ffba3 fa184 f</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku- RIDA- Roku串流裝置</b> </p> <p><b>GAID</b> RIDDA ID是Roku裝置製造商提供的串流裝置識別碼。</p> </td>
   <td colname="col3"> <p>格式嚴格由32 <i>個小寫</i> 十六進位數字組成，顯示於五個群組並以連字號分隔，格式為8-4-4-4-12，總共36個字元。 </p> <p> <code> fcp2a29c-315a-5e6b-bedered-d889 ba19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID- MAID- Windows10裝置</b> </p> <p><b>MAID</b> ID是依每一裝置(每位使用者)產生的Windows10裝置識別碼。</p> </td>
   <td colname="col3"> <p>MAID格式格式為英數字串。</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID- Samsung裝置</b> </p> Samsung DuID是Samsung TV提供的裝置識別碼。</p> </td>
   <td colname="col3"> <p>Samsung DuID格式格式為英數字串。</p></td>
  </tr>
 </tbody> 
</table>