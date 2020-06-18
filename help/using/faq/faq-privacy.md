---
description: 常見隱私權與資料相關問題的解答。
seo-description: 常見隱私權與資料相關問題的解答。
seo-title: 隱私權與資料保留常見問題集
solution: Audience Manager
title: 隱私權與資料保留常見問題集
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 96%

---


# 隱私權與資料保留常見問題集{#privacy-and-data-retention-faq}

常見隱私權與資料相關問題的解答。

<!-- faq_privacy.xml -->

## 隱私權常見問題集 {#privacy-faq}

>[!TIP]
>
>如需詳細資訊，請造訪 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)。

**Audience Manager 如何使用 Cookie？會設定哪些 Cookie？**

請參閱 [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)。

**美國的 Audience Manager 客戶是否可將目標定位為歐盟屬性的使用者？**

是。Audience Manager 可與擁有國際屬性和詳細目錄的客戶合作。歐盟的隱私權法箱剛嚴格，不過 Audience Manager 有客戶使用第一方資料將目標定位為歐洲的受眾。Audience Manager 可支援對歐盟受眾進行目標定位，但您有責任遵守當地的隱私權法規。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 資料保留常見問題集 {#data-retention-faq}

下表列出不同資料類型和儲存系統的保留時間。

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料類型、來源或儲存空間 </th> 
   <th colname="col2" class="entry"> 資料保留期 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>後端伺服器 </p> </td> 
   <td colname="col2"> <p>120 天。 </p> <p> Audience Manager 會於上次在 Audience Manager 平台上看到使用者的 120 天後，從我們的後端伺服器上刪除該使用者的資料。如果 <span class="keyword"> Audience Manager</span> 在此 120 天週期內有記錄使用者活動，便會再將此資料保存 120 天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>邊緣伺服器 </p> </td> 
   <td colname="col2"> <p> 14 天。 </p> <p>Audience Manager 會於上次在 Audience Manager 平台上看到使用者的 14 天後，從我們的邊緣伺服器上刪除該使用者的資料。如果 <span class="keyword"> Audience Manager</span> 在此 14 天週期內有記錄使用者活動，便會再將此資料保存 14 天。如果使用者在 14 天後再次進入作用中狀態，則第一個新頁面檢視與使用者變成可操作的時間之間會出現延遲。閒置超過 14 天後，需要 6 到 18 個小時才能將完整的設定檔送回邊緣中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始記錄檔 </p> </td> 
   <td colname="col2"> <p>180 天 (180 天無活動後移除)。 </p> <p>原始記錄檔是邊緣伺服器收到的資料 (透過 HTTP 呼叫或來自傳入 <span class="keyword"> Audience Manager</span> 的已上線檔案)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告伺服器記錄檔 </p> </td> 
   <td colname="col2"> <p><b>報表</b> </p> <p>記錄檔會保留最多 30 天以用於製作報表。我們不會在後端儲存空間中保存不相符的記錄 (亦即訪客的廣告伺服器 ID 與 <span class="keyword"> Audience Manager</span> ID 之間沒有任何 ID 同步的記錄檔)，而 <span class="keyword"> Amazon S3</span> 中儲存的相符記錄會保留最多 30 天。 </p> <p><b>可操作的記錄檔</b> </p> <p>相符和不相符的記錄檔都可保留最多 30 天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 層級設定檔 (已驗證的設定檔) </p> </td> 
   <td colname="col2"> <p>非作用中 CRM 層級設定檔 (客戶 ID) 的預設存留時間 (TTL) 間隔為 24 個月。不過，您可以使用Audience Manager使用者介面，將非作用中CRM層級設定檔的TTL間隔縮短或延長一個月至五年。 您可以在建立或編輯跨裝置資料來源時完成此操作。</p> <p>如需詳細資訊，請參閱<a href="../features/profile-merge-rules/merge-rules-start.md#settings">建立跨裝置資料來源</a>中的「資料來源設定」。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 ID </p> </td> 
   <td colname="col2"> <p>行動裝置 ID (<a href="../reference/ids-in-aam.md"> IDFA、GAID</a>) 的保留條件遵循前兩列、後端伺服器和邊緣伺服器中所述的順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶資料摘要 (CDF) </p> </td> 
   <td colname="col2"> <p>CDF 檔案包含的資料與 <span class="keyword">Audience Manager</span> 事件呼叫 (/event) 傳送至我們伺服器的資料相同。保留期為 8 天。有關 CDF 的更多詳細資訊，請參閱 <a href="../features/cdf-files.md">CDF 簡介</a>和 <a href="../faq/faq-cdf.md">CDF 常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已同步 ID 之間的對應 </p> </td> 
   <td colname="col2"> <p>Audience Manager Cookie ID (<a href="../reference/ids-in-aam.md">Audience Manager 不重複使用者 ID 或 AAM UUID</a>) 與第三方 Cookie ID 之間的 <a href="../features/administration/usage-limits.md#id-mapping-limits">ID 對應</a>有效期限上限為 120 天。每次在 Audience Manager 網路上看到 Audience Manager Cookie 時，ID 對應的有效期限都會重設。最新的 ID 對應同步會保留至與 <a href="../reference/ids-in-aam.md">Audience Manager 不重複使用者 ID (AAM UUID)</a> 相關聯的有效期限。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳入資料 </p> </td> 
   <td colname="col2"> <p>這是您透過 FTP 傳送至 <span class="keyword"> Audience Manager</span>，或直接傳送至 <span class="keyword"> Amazon S3</span> 目錄的傳入資料。請參閱<a href="../faq/faq-inbound-data-ingestion.md">傳入客戶資料擷取常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳出資料 </p> </td> 
   <td colname="col2"> <p>這是 <span class="keyword">Audience Manager</span> 傳送給第三方啟用合作夥伴的批次資料。保留期為 8 天。如需更多傳出資料的詳細資訊，請參閱<a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">傳出批次傳輸</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特徵資格資料保留 {#trait-qual}

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
   <td colname="col2"> <p>刪除特徵會從過去符合特徵資格的所有使用者設定檔中移除特徵資格資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已達特徵數上限 </p> </td> 
   <td colname="col2"> <p>我們設下了每個使用者設定檔 100,000 個特徵資格的限制。此上限適用於已驗證的設定檔和裝置設定檔。如果使用者設定檔達到此上限，我們會根據先進先出原則刪除最舊的特徵資格。 </p> <p>如需詳細資訊，請閱讀<a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">特徵資格限制</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

