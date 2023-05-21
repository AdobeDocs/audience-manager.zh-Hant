---
description: 描述初始HTTP調用中用於在Audience Manager和第三方資料提供程式之間同步用戶ID的語法和參數。 在嘗試首次ID同步之前，請與Adobe Audience Manager顧問聯繫。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: 傳出資料傳輸的 ID 同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 11%

---

# 傳出資料傳輸的 ID 同步{#id-synchronization-for-outbound-data-transfers}

描述初始中使用的語法和參數 `HTTP` 調用以在Audience Manager和第三方資料提供程式之間同步用戶ID。 在嘗試首次ID同步之前，請與Adobe Audience Manager顧問聯繫。

<!-- c_id_sync_out.xml -->

## ID同步的用途

ID同步是出站非同步資料傳輸過程中的第一步。 在這一步， [!DNL Audience Manager] 供應商將各自站點訪問者的ID進行比較和匹配。 例如， [!DNL Audience Manager] 客戶可能通過ID 123瞭解用戶。 但是，您的資料合作夥伴可以識別ID為456的此用戶。 同步過程允許 [!DNL Audience Manager] 以及資料供應商，以協調這些不同的ID並識別各自系統中的用戶。 完成後， [!DNL Audience Manager] 第三方資料提供商應為我們網路上看到的每個唯一用戶擁有相應的ID。

## URL語法

在ID交換中，格式正確 [!DNL URL] 字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 參數

的 [!DNL URL] 對於入站ID同步調用，應包含下表中描述的變數。

>[!NOTE]
>
>用實際參數值替換斜體內容。

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
   <td colname="col2">資料提供程式的唯一ID(由 <span class="keyword"> Audience Manager</span>)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 唯一用戶ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">帶宏的編碼URL重定向 <code> ${DD_UUID}</code> 嵌入其中。 <p><b>注：</b> 僅在資料提供程式啟動調用時添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p><p><b>注意:</b> <ul><li>的 <code>gdpr</code> 和 <code>gdpr_consent</code> 參數正在與激活夥伴在ID同步URL中逐漸展開。 請參閱中支援IAB TCF的激活合作夥伴 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience ManagerIAB TCF插件。</a></li><li>此參數只能與 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是URL安全的base64編碼的GDPR同意字串(請參見 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規範</a>)。</p><p><b>注：</b> 此參數只能與 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [資料收集伺服器 (DCS) API 方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [資料收集元件](../../reference/system-components/components-data-collection.md)

