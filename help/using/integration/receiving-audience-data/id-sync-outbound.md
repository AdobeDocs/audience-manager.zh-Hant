---
description: 說明初始HTTP呼叫中用來同步Audience manager與協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。
seo-description: 說明初始HTTP呼叫中用來同步Audience manager與協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。
seo-title: 出站資料傳輸的ID同步
solution: Audience Manager
title: 出站資料傳輸的ID同步
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# 出站資料傳輸的ID同步{#id-synchronization-for-outbound-data-transfers}

說明初始呼叫中用來同步 `HTTP` Audience manager和協力廠商資料提供者之間使用者ID的語法和參數。 在嘗試進行第一個ID同步之前，請連絡您的Adobe Audience Manager顧問。

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i></code> </td> 
   <td colname="col2">資料提供者的唯一ID(由 <span class="keyword"> Audience Manager指派</span>)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i></code> </td> 
   <td colname="col2"> 唯一使用者ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i></code> </td> 
   <td colname="col2">內嵌巨集 <code> ${DD_UUID}的編碼URL重新導向</code> 。 <p><b></b> 注意：僅在資料提供者開始呼叫時新增。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr可以是</code> 0（GDPR不適用）或1（GDPR適用）。</p><p><b>注意:</b> <ul><li>ID <code>同步URL中</code> ，與啟 <code>動合作夥伴逐漸推出gdpr和gdpr_connency</code> 參數。 請參閱Audience Manager Plug-in for IAB TCF中支援IAB TCF <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">的啟動合作夥伴。</a></li><li>此參數只能與 <code>gdpr_connency一起使用。</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_connency=&lt;ENCODED STRING&gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_connence</code> 是URL安全的base64編碼GDPR同意字串(請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>)。</p><p><b></b> 注意：此參數只能與 <code>gdpr搭配使用</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [資料收集伺服器(DCS)API方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [資料收集元件](../../reference/system-components/components-data-collection.md)

