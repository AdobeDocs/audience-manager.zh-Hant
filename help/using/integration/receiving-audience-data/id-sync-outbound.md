---
description: 說明初始HTTP呼叫中用來同步Audience Manager與協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。
seo-description: 說明初始HTTP呼叫中用來同步Audience Manager與協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。
seo-title: 傳出資料傳輸的 ID 同步
solution: Audience Manager
title: 傳出資料傳輸的 ID 同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 12%

---


# 傳出資料傳輸的 ID 同步{#id-synchronization-for-outbound-data-transfers}

說明初始呼叫中用來同步 `HTTP` Audience Manager與協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。

<!-- c_id_sync_out.xml -->

## ID同步的用途

ID同步是出站、非同步資料傳輸過程的第一步。 在此步驟中， [!DNL Audience Manager] 廠商會比較並比對個別網站訪客的ID。 例如，客戶可 [!DNL Audience Manager] 能依ID 123瞭解使用者。 不過，您的資料合作夥伴可以識別此使用者的ID為456。 同步過程允許 [!DNL Audience Manager] 和資料供應商協調這些不同的ID並標識其各自系統中的用戶。 完成後， [!DNL Audience Manager] 第三方資料提供者應為我們網路上的每個唯一使用者提供對應的ID。

## URL語法

在ID交換中，格式正確的字 [!DNL URL] 串應該如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 參數

您的 [!DNL URL] 傳入ID同步呼叫應包含下表所述的變數。

>[!NOTE]
>
>以實際參數值取代斜體內容。

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
   <td colname="col2">資料提供者的唯一ID(由 <span class="keyword"> Audience Manager指派</span>)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 唯一使用者ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">內嵌巨集的編碼URL重新導 <code> ${DD_UUID}</code> 向。 <p><b>注意：</b> 僅在資料提供者開始呼叫時新增。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p><p><b>注意:</b> <ul><li>與啟 <code>gdpr</code> 動合 <code>gdpr_consent</code> 作夥伴的ID同步URL會逐漸推出和參數。 請參閱Audience Manager Plug-in for IAB TCF中支援IAB TCF <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">的啟動合作夥伴。</a></li><li>此參數只能與 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>注意：</b> 此參數只能與一起使用 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [資料收集伺服器 (DCS) API 方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [資料收集元件](../../reference/system-components/components-data-collection.md)

