---
description: 說明在Audience Manager與第三方資料供應商之間，初始HTTP呼叫中用來同步化使用者ID的語法和參數。請先洽詢您的Adobe Audience Manager顧問，然後再嘗試進行第一次ID同步。
seo-description: 說明在Audience Manager與第三方資料供應商之間，初始HTTP呼叫中用來同步化使用者ID的語法和參數。請先洽詢您的Adobe Audience Manager顧問，然後再嘗試進行第一次ID同步。
seo-title: 傳出資料傳輸的ID同步
solution: Audience Manager
title: 傳出資料傳輸的ID同步
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. 請先洽詢您的Adobe Audience Manager顧問，然後再嘗試進行第一次ID同步。

<!-- c_id_sync_out.xml -->

## ID同步的目的

ID同步是傳出、非同步資料傳輸程序的第一步。In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. 不過，您的資料合作夥伴可以識別此使用者ID456。The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## URL語法

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 參數

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>使用實際參數值取代斜體內容。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; DOCUMENT_ ID&gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; DOCUMENT_ UUID&gt;</i></code> </td> 
   <td colname="col2"> 唯一使用者ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL&gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>注意：</b> 僅在資料提供者開始呼叫時才新增。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr=&lt;0|&gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可能為(GDPR不適用)或1(GDPR適用)。</p><p><b>注意:</b> <ul><li><code>gdpr</code> 和 <code>gdpr_ conseption</code> 參數正逐漸以ID同步URL與啓動合作夥伴同步。See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ conseption=&lt;編碼String&gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ conseption</code> 是URL安全的base64編碼GDPR許可字串(請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>)。</p><p><b>注意：</b> 此參數只能與 <code>gdpr搭配使用</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [資料收集伺服器(DCS) API方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [資料收集元件](../../reference/system-components/components-data-collection.md)

