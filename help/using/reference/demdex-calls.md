---
description: Audience Manager 及 Experience Cloud ID 服務會從 demdex.net 網域呼叫和接收資料。Adobe可能會與不尋常的第三方網域合作，但事實並非如此。本節說明demdex. net呼叫中的元素。
seo-description: Audience Manager 及 Experience Cloud ID 服務會從 demdex.net 網域呼叫和接收資料。Adobe可能會與不尋常的第三方網域合作，但事實並非如此。本節說明demdex. net呼叫中的元素。
seo-title: 瞭解傳至 Demdex 網域的呼叫
solution: Audience Manager
title: 瞭解傳至 Demdex 網域的呼叫
uuid: c06DAE3a-f169-4712-80fb-d6 d448 dce51 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 瞭解傳至 Demdex 網域的呼叫{#understanding-calls-to-the-demdex-domain}

Audience Manager 及 Experience Cloud ID 服務會從 demdex.net 網域呼叫和接收資料。Adobe可能會與不尋常的第三方網域合作，但事實並非如此。本節說明demdex. net呼叫中的元素。

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 呼叫元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. It reflects <span class="keyword"> Audience Manager</span>'s original, pre-acquisition name (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> 於2011年收購 <span class="keyword"> Demdex</span> ，並將該公司重新品牌為 <span class="keyword"> Audience Manager</span>。It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. See <a href="../overview/aam-overview.md#history-and-background"> History and Background</a>. </p> <p>You may see other prefixes attached to legacy <code> demdex.net</code> calls (e.g., <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Regardless of the prefix, a call to <code><i>something</i>.demdex.net</code> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 是 <span class="wintitle"> 資料提供者符合</span>的縮寫。It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. This is the most common <code> demdex.net</code> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> DPM</span> 呼叫基本功能： </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>：Audience Manager的 <span class="wintitle"> DPM</span><span class="keyword"> 呼叫會</span> 傳送資料至 <span class="wintitle"> 資料收集伺服器</span> 和 <span class="wintitle"> 描述檔快取伺服器</span>。See <a href="../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> ID服務</span></b>：來自ID服務的 <span class="wintitle"> DPM</span><span class="wintitle"> 呼叫</span> 是訪客ID的請求。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Experience Cloud ID Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server and audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [Experience Cloud ID 服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

