---
description: 常見隱私權和資料相關問題的解答
seo-description: 常見隱私權和資料相關問題的解答
seo-title: ' 隱私權與資料保留常見問題'
solution: Audience Manager
title: 隱私權與資料保留常見問題
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

常見隱私權和資料相關問題的解答

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>請造訪 [Adobe隱私權中心](https://www.adobe.com/privacy.html) ，以取得詳細資訊。

**Audience manager如何使用Cookie及其設定的Cookie?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**美國的Audience manager客戶是否可將EU屬性的使用者鎖定在目標？**

是。Audience manager可與擁有國際屬性和庫存的客戶合作。 歐盟有嚴格的隱私權法，但Audience manager的客戶使用第一方資料來鎖定歐洲的受眾。 Audience manager可支援針對歐盟受眾的定位，但您有責任遵守當地的隱私權規定。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 資料保留常見問題 {#data-retention-faq}

下表列出了不同資料類型和儲存系統的保留時間。

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料類型、源或儲存 </th> 
   <th colname="col2" class="entry"> 資料保留期 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>後端伺服器 </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience manager會在上次在Audience manager平台上看到使用者120天後，從我們的後端伺服器刪除使用者資料。 如果 <span class="keyword"> Audience Manager</span> 在此120天週期內記錄使用者活動，我們會再將此資料保存120天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>邊緣伺服器 </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience manager會在上次在Audience manager平台上看到使用者14天後，從我們的邊緣伺服器刪除使用者資料。 如果 <span class="keyword"> Audience Manager</span> 在此14天週期內記錄使用者活動，我們將會再將此資料保存14天。 如果使用者在14天後再次啟用，則第一個新頁面檢視與使用者變成可操作的時間會延遲。 閒置超過14天後，需要6-18小時才能將完整的描述檔送回邊緣中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw logs </p> </td> 
   <td colname="col2"> <p>180天（在180天無活動後移除）。 </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>報告</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>可操作的記錄檔</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager UI to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs ( IDFA, GAID) follow the cadence described in the first two rows, back-end servers and edge servers.<a href="../reference/ids-in-aam.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶資料饋送(CDF) </p> </td> 
   <td colname="col2"> <p>CDF檔案包含的資料與 <span class="keyword"> Audience Manager</span> (/event)事件呼叫(/event)傳送至我們伺服器的資料相同。 保留期為8天。 For more details about CDF, please refer to  CDF Intro and  CDF FAQ.<a href="../features/cdf-files.md"></a><a href="../faq/faq-cdf.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同步ID之間的映射 </p> </td> 
   <td colname="col2"> <p>Audience Manager Cookie ID <a href="../features/administration/usage-limits.md#id-mapping-limits"> (</a> Audience Manager Unique User ID或AAM UUID<a href="../reference/ids-in-aam.md"></a>)與第三方Cookie ID之間ID映射的期限限制為120天。 每次在Audience manager網路上看到Audience Manager cookie時，ID對應的期限都會重設。 最新的ID對應同步會保留至相關 <a href="../reference/ids-in-aam.md">Audience Manager唯一使用者ID(AAM UUID)的有效期</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳入資料 </p> </td> 
   <td colname="col2"> <p>這是您透過FTP傳送至 <span class="keyword"> Audience Manager</span> ，或直接傳送至 <span class="keyword"> Amazon S3目錄的傳入資料</span> 。 請參閱傳入 <a href="../faq/faq-inbound-data-ingestion.md"> 客戶資料擷取常見問答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出站資料 </p> </td> 
   <td colname="col2"> <p>This is the batch data that  Audience Manager sends to third party activation partners. <span class="keyword"></span>保留期為8天。 有關出站資料的詳細資訊，請參閱出站批 <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> 次傳輸</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特徵限定資料保留 {#trait-qual}

下表列出特徵資格的保留選項。

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特徵操作 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>刪除特徵 </p> </td> 
   <td colname="col2"> <p>刪除特徵會從過去符合特徵的所有使用者設定檔中移除特徵資格資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已達到特徵限制 </p> </td> 
   <td colname="col2"> <p>我們為每個使用者個人檔案設定100,000個特徵資格限制。 此限制適用於已驗證的設定檔和裝置設定檔。 如果使用者設定檔達到此限制，我們會先入先出地刪除最舊的特徵資格。 </p> <p>如需詳細資訊，請閱讀我們的 <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> 特徵資格限制</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

