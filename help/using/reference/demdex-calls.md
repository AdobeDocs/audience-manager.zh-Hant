---
description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域並從中接收資料。 Adobe似乎正在與不同尋常的第三方網域合作，但事實並非如此。 本節說明demdex.net呼叫中的元素。
seo-description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域並從中接收資料。 Adobe似乎正在與不同尋常的第三方網域合作，但事實並非如此。 本節說明demdex.net呼叫中的元素。
seo-title: 瞭解向 Demdex 網域進行的呼叫
solution: Audience Manager
title: 瞭解向 Demdex 網域進行的呼叫
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 12%

---


# 瞭解向 Demdex 網域進行的呼叫{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 以及Adobe Experience Platform Identity Service會呼叫demdex.net網域並從中接收資料。 Adobe似乎正在與不同尋常的第三方網域合作，但事實並非如此。 本節說明呼叫中的 `demdex.net` 元素。

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. 它反映 <span class="keyword"> Audience Manager</span>的原始、贏取前名稱(<span class="keyword"> Demdex</span>)。 <span class="keyword"> Adobe</span> 在 <span class="keyword"> 2011年收購Demdex</span> ，並將該公司重新命名為 <span class="keyword"> Audience Manager</span>。 很難變更此網域，因為它與 <span class="keyword"> Audience Manager</span>、 <span class="wintitle"></span>ID服務以及我們已安裝的使用者群緊密相連。 請參閱 <a href="../overview/aam-overview.md#history-and-background"> 歷史與背景</a>。 </p> <p>您可能會看到附加在舊 <code> demdex.net</code> 呼叫的其他字首( <code> dcs.demdex.net</code>如 <code> fast.demdex.net</code>，等等)。 不論首碼為何，呼叫 <code><i>something</i>.demdex.net</code> 一律為對 <span class="keyword"> Adobe</span> ，而非對未知或可疑的第三方網域的呼叫。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 是「資料提供者 <span class="wintitle"> 符合」的縮寫</span>。 It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. 這是您從Audience Manager或 <code> demdex.net</code><span class="keyword"> ID</span> 服務看到的最常見呼叫 <span class="wintitle"></span>。 </p> <p><span class="wintitle"> DPM呼叫基</span> 礎知識： </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span></b>: 來自 <span class="wintitle"> Audience Manager的</span> DPM <span class="keyword"> 呼叫會將資料傳送至資料收集伺服器</span> 和快取設定檔 <span class="wintitle"></span><span class="wintitle"></span>伺服器。 請參閱<a href="../reference/system-components/components-data-collection.md">資料收集元件</a>。 </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID服務</span></b>: 來自 <span class="wintitle"> ID服務的</span><span class="wintitle"></span> DPM呼叫是對訪客ID的請求。 請參 <a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> 閱Cookie和Adobe Experience Platform Identity Service</a><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> ，以及Adobe Experience Platform Identity Service如何請求和設定ID</a>。 </li> 
     </ul> </p> <p> <p>注意：  <span class="wintitle"> ID服務</span> ，客戶可以變更網 <span class="wintitle"> 域名稱中的DPM</span> 前置詞。 請參 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> 閱audienceManager Server和audienceManagerServerSecure</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)

