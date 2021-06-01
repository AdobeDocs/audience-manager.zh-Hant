---
description: 說明初始HTTP呼叫中使用的語法和參數，以同步供應商與Audience Manager之間的使用者ID。 將資料分類法傳送至Audience Manager後，即可開始進行ID同步。
seo-description: 說明初始HTTP呼叫中使用的語法和參數，以同步供應商與Audience Manager之間的使用者ID。 將資料分類法傳送至Audience Manager後，即可開始進行ID同步。
seo-title: 傳入資料傳輸的 ID 同步
solution: Audience Manager
title: 傳入資料傳輸的 ID 同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: 傳入資料傳輸
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 8%

---

# 傳入資料傳輸的 ID 同步 {#id-synchronization-for-inbound-data-transfers}

說明初始`HTTP`呼叫中使用的語法和參數，以同步供應商與[!DNL Audience Manager]之間的用戶ID。 將資料分類法傳送至[!DNL Audience Manager]後，即可開始進行ID同步。

ID同步是傳入、非同步資料傳輸程式的第一步。 在此步驟中，[!DNL Audience Manager]和供應商會比較並比對其各自網站訪客的ID。 例如，[!DNL Audience Manager]客戶可能依ID 123了解使用者。 不過，您的資料合作夥伴可以透過ID 456識別此使用者。 同步過程允許[!DNL Audience Manager]和資料供應商協調這些不同的ID，並標識其各自系統中的用戶。 完成後，[!DNL Audience Manager]和您的第三方合作夥伴應該會為我們網路上看到的每個唯一使用者擁有對應的ID。

您可以使用下列方法將資料傳入[!DNL Audience Manager]:

* [ID同步HTTP要求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣告ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件內嵌影像進行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步`HTTP`請求{#id-sync-http}

在ID交換中，格式正確的[!DNL URL]字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>內容提供者的唯一ID(由<span class="keyword">Audience Manager</span>指派)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL（百分比）編碼表示您的不重複使用者ID。 除了編碼保留的ASCII字元外，任何非ASCII字元都應根據UTF-8字元編碼表進行百分比編碼。 </p> <p>如需詳細資訊，請參閱<a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a>網站。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>內嵌巨集<code> ${DD_UUID}</code>的編碼URL重新導向。 </p> <p>注意： 僅在內容提供者起始呼叫時新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果您使用適用於IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此參數。</a></p> <p><code> gdpr</code> 可為0（GDPR不適用）或1（GDPR適用）。 </p> <p> <b>注意：</b> 此參數只能與搭配使 <code>gdpr_consent</code>用。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果您使用適用於IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此參數。</a></p> <p><code>gdpr_consent</code> 是URL安全base64編碼GDPR同意字串（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>）。 </p> <p> <b>注意：</b> 此參數只能與搭配使 <code>gdpr</code>用。</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 事件 {#declared-id-event}

如需詳細資訊，請參閱[宣告ID](../../../features/declared-ids.md)。

## 從電子郵件嵌入映像{#id-sync-email-image}進行ID同步

透過電子郵件影像比對ID的格式與上述相同。 但請注意，電子郵件中的影像必須啟用才能運作。 這可能會影響透過電子郵件進行的ID同步，因為大部分的郵件系統預設會停用影像。

>[!MORELIKETHIS]
>
>* [資料收集元件](../../../reference/system-components/components-data-collection.md)

