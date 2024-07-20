---
description: 說明初始HTTP呼叫中使用的語法和引數，以便在Audience Manager和第三方資料提供者之間同步使用者ID。 請先連絡您的Adobe Audience Manager顧問，再嘗試進行第一個ID同步作業。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: 傳出資料傳輸的識別碼同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# 傳出資料傳輸的識別碼同步{#id-synchronization-for-outbound-data-transfers}

說明初始`HTTP`呼叫中所使用的語法和引數，以便在Audience Manager和協力廠商資料提供者之間同步使用者ID。 請先連絡您的Adobe Audience Manager顧問，再嘗試進行第一個ID同步作業。

<!-- c_id_sync_out.xml -->

## ID同步的目的

ID同步是外送、非同步資料傳輸程式中的第一個步驟。 在此步驟中，[!DNL Audience Manager]和廠商會比較並比對各自網站訪客的ID。 例如，[!DNL Audience Manager]客戶可能透過識別碼123認識使用者。 不過，您的資料合作夥伴可以使用ID 456識別此使用者。 同步處理可讓[!DNL Audience Manager]和資料廠商調解這些不同的ID，並識別其各自系統中的使用者。 完成後，[!DNL Audience Manager]和協力廠商資料提供者應該對我們網路上看到的每個不重複使用者擁有對應的ID。

## URL語法

在ID交換中，正確格式化的[!DNL URL]字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 參數

傳入ID同步呼叫的[!DNL URL]應包含下表所述的變數。

>[!NOTE]
>
>以實際引數值取代斜體化內容。

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
   <td colname="col2">資料提供者的唯一識別碼(由<span class="keyword">Audience Manager</span>指派)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 不重複使用者識別碼。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">內嵌巨集<code> ${DD_UUID}</code>的編碼URL重新導向。 <p><b>注意：</b>只在資料提供者啟動呼叫時新增。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可為0 （GDPR不適用）或1 （GDPR適用）。</p><p><b>注意:</b> <ul><li><code>gdpr</code>和<code>gdpr_consent</code>引數正在與啟用協力電腦逐步轉出至ID同步URL。 請參閱在<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">適用於IAB TCF的Audience Manager外掛程式中支援IAB TCF的啟用合作夥伴。</a></li><li>此引數只能搭配 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是URL安全base64編碼GDPR同意字串（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>）。</p><p><b>注意：</b>此引數只能與<code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [資料收集伺服器(DCS) API方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [資料收集元件](../../reference/system-components/components-data-collection.md)
