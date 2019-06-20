---
description: 常見隱私權和資料相關問題的解答
seo-description: 常見隱私權和資料相關問題的解答
seo-title: 隱私權與資料保留常見問題
solution: Audience Manager
title: 隱私權與資料保留常見問題
uuid: ef558fca-35ff-44f1-8527-f8 be9 f2 c7 e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

常見隱私權和資料相關問題的解答

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Audience Manager如何使用Cookie以及設定Cookie？**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**美國的Audience Manager客戶可以鎖定EU屬性的使用者嗎？**

是。Audience Manager可與擁有國際資產和庫存的客戶合作。歐盟嚴格奉行隱私權法律，但Audience Manager的客戶則是在歐洲使用第一方資料進行受眾鎖定。Audience Manager可支援鎖定歐盟受眾，但您有責任遵守當地隱私權規範。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 資料保留常見問題 {#data-retention-faq}

下表列出不同資料類型和儲存系統的保留期。

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
   <td colname="col2"> <p>120天。 </p> <p> Audience Manager會在最後一次看到Audience Manager平台上的使用者後，從後端伺服器刪除使用者資料。<span class="keyword"> 如果Audience Manager</span> 在這120天的週期內記錄使用者活動，我們將保留此資料120天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge伺服器 </p> </td> 
   <td colname="col2"> <p> 14天。 </p> <p>Audience Manager會在最後一次看到Audience Manager平台上的使用者後14天從我們的Edge伺服器刪除使用者資料。<span class="keyword"> 如果Audience Manager</span> 在這14天的週期內記錄使用者活動，我們將會保留此資料14天。如果使用者在14天後再次開始使用，則第一次新頁面檢視和使用者可操作之間會有延遲。在閒置超過14天後，需要6-18小時才能將完整的描述檔回到邊緣中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始記錄 </p> </td> 
   <td colname="col2"> <p>180天(在無活動180天後移除)。 </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>廣告伺服器記錄檔 </p> </td> 
   <td colname="col2"> <p><b>報告</b> </p> <p>記錄檔最多可保留30天以供報告用途。We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>可操作的記錄檔</b> </p> <p>相符項目和不相符記錄最多可保留30天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM層級描述檔(已驗證的設定檔) </p> </td> 
   <td colname="col2"> <p>非活動CRM層級設定檔(客戶ID)的預設時間(TTL)間隔為24個月。不過，您可以使用Audience Manager UI來減少或延長在一個月到年之間非活動CRM層級設定檔的TTL間隔。建立或編輯跨裝置資料來源時，您可以做到這一點。</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置ID </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶資料饋送(CMS) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. 保留期為天。For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同步化ID之間的映射 </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳入資料 </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳出資料 </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 會傳送給第三方啓動合作夥伴的批次資料。保留期為天。For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

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
   <td colname="col2"> <p>刪除特徵會移除所有過去符合特徵特徵的使用者設定檔中的特徵資格資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>達到特徵限制 </p> </td> 
   <td colname="col2"> <p>我們限制每個使用者個人檔案的100，000個特徵資格。此限制適用於已驗證的設定檔和裝置設定檔。如果使用者個人檔案達到此限制，我們將會優先刪除最舊的特徵資格。 </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

