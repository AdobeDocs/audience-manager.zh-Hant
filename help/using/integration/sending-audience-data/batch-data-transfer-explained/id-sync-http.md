---
description: 說明在供應商與Audience Manager之間，初始HTTP呼叫中用來同步化使用者ID的語法和參數。ID同步可以在您將資料分類法傳送至Audience Manager後開始。
seo-description: 說明在供應商與Audience Manager之間，初始HTTP呼叫中用來同步化使用者ID的語法和參數。ID同步可以在您將資料分類法傳送至Audience Manager後開始。
seo-title: 傳入資料傳輸的ID同步
solution: Audience Manager
title: 傳入資料傳輸的ID同步
uuid: 037e74a6-acfd-4cef-b693-16b7 a976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. ID同步可以在您將資料分類法傳送至Audience Manager後開始。

<!-- c_id_sync_in.xml -->

ID同步是傳入、非同步資料傳輸程序的第一步。在此步驟中，Audience Manager和廠商會比較和比對其個別網站訪客的ID。For example, an [!DNL Audience Manager] customer may know a user by ID 123. 不過，您的資料合作夥伴可以識別此使用者ID456。The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [ID同步HTTP要求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣告的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件內嵌影像同步ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; DOCUMENT_ ID&gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; DOCUMENT_ UUID&gt;</i></code> </td> 
   <td colname="col2"> <p>URL(百分比)您唯一使用者ID的編碼表示法。除了編碼保留ASCII字元之外，任何非ASCII字元都應根據UTF-8字元編碼表格來編碼。 </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL&gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>注意：僅在內容提供者開始呼叫時才新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr=&lt;0|&gt;</i></code> </td> 
   <td colname="col2"> <p>選填。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> gdpr</code> 可能為(GDPR不適用)或1(GDPR適用)。 </p> <p> <b>注意：</b> 此參數只能與 <code>gdpr_ consensement搭配使用</code>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ conseption=&lt;編碼String&gt;</i></code> </td> 
   <td colname="col2"> <p>選填。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ conseption</code> 是URL安全的base64編碼GDPR許可字串(請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>)。 </p> <p> <b>注意：</b> 此參數只能與 <code>gdpr搭配使用</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

透過電子郵件影像比對ID的格式與上表相同。但請注意，必須啓用電子郵件中的影像才能運作。這可能會影響透過電子郵件同步ID，因為大部分的郵件系統預設會停用影像。

>[!MORE_贊_ this]
>
>* [資料收集元件](../../../reference/system-components/components-data-collection.md)

