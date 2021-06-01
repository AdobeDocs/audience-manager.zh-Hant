---
description: 說明初始HTTP呼叫中使用的語法和參數，以同步Audience Manager與協力廠商資料提供者之間的使用者ID。 嘗試進行第一個ID同步前，請先聯絡您的Adobe Audience Manager顧問。
seo-description: 說明初始HTTP呼叫中使用的語法和參數，以同步Audience Manager與協力廠商資料提供者之間的使用者ID。 嘗試進行第一個ID同步前，請先聯絡您的Adobe Audience Manager顧問。
seo-title: 傳出資料傳輸的 ID 同步
solution: Audience Manager
title: 傳出資料傳輸的 ID 同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: 傳出資料傳輸
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 12%

---

# 傳出資料傳輸的 ID 同步{#id-synchronization-for-outbound-data-transfers}

說明初始`HTTP`呼叫中使用的語法和參數，用於同步Audience Manager與第三方資料提供者之間的使用者ID。 嘗試進行第一個ID同步前，請先聯絡您的Adobe Audience Manager顧問。

<!-- c_id_sync_out.xml -->

## ID同步的用途

ID同步是傳出、非同步資料傳輸程式的第一步。 在此步驟中，[!DNL Audience Manager]和供應商會比較並比對其各自網站訪客的ID。 例如，[!DNL Audience Manager]客戶可能依ID 123了解使用者。 不過，您的資料合作夥伴可以透過ID 456識別此使用者。 同步過程允許[!DNL Audience Manager]和資料供應商協調這些不同的ID，並標識其各自系統中的用戶。 完成後，[!DNL Audience Manager]和第三方資料提供者應該會為我們網路上看到的每個唯一使用者擁有對應的ID。

## URL語法

在ID交換中，格式正確的[!DNL URL]字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 參數

傳入ID同步呼叫的[!DNL URL]應包含下表所述的變數。

>[!NOTE]
>
>將斜體內容取代為實際參數值。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">資料提供者的唯一ID(由<span class="keyword">Audience Manager</span>指派)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 不重複使用者ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">內嵌巨集<code> ${DD_UUID}</code>的編碼URL重新導向。 <p><b>注意：</b> 僅在資料提供者起始呼叫時新增。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可為0（GDPR不適用）或1（GDPR適用）。</p><p><b>注意:</b> <ul><li><code>gdpr</code>和<code>gdpr_consent</code>參數正在與啟用合作夥伴的ID同步URL中逐步推出。 請參閱適用於IAB TCF的「Audience Manager外掛程式」中的支援IAB TCF的啟用合作夥伴。</a><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners"></a></li><li>此參數只能搭配使用 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是URL安全base64編碼GDPR同意字串（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>）。</p><p><b>注意：</b> 此參數只能與搭配使 <code>gdpr</code>用。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [資料收集伺服器 (DCS) API 方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
* [資料收集元件](../../reference/system-components/components-data-collection.md)

