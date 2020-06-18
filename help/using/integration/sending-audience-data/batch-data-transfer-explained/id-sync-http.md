---
description: 說明初始HTTP呼叫中用來同步廠商和Audience Manager之間使用者ID的語法和參數。 ID同步可在您將資料分類傳送至Audience Manager後開始。
seo-description: 說明初始HTTP呼叫中用來同步廠商和Audience Manager之間使用者ID的語法和參數。 ID同步可在您將資料分類傳送至Audience Manager後開始。
seo-title: 傳入資料傳輸的 ID 同步
solution: Audience Manager
title: 傳入資料傳輸的 ID 同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 7%

---


# 傳入資料傳輸的 ID 同步{#id-synchronization-for-inbound-data-transfers}

說明初始呼叫中用來同步廠商與 `HTTP` 之間使用者ID的語法和參數 [!DNL Audience Manager]。 ID同步可在您將資料分類傳送至之後開始 [!DNL Audience Manager]。

<!-- c_id_sync_in.xml -->

ID同步是傳入、非同步資料傳輸程式的第一步。 在此步驟中， [!DNL Audience Manager] 廠商會比較並比對個別網站訪客的ID。 例如，客戶可 [!DNL Audience Manager] 能依ID 123瞭解使用者。 不過，您的資料合作夥伴可以識別此使用者的ID為456。 同步過程允許 [!DNL Audience Manager] 和資料供應商協調這些不同的ID並標識其各自系統中的用戶。 完成後，您 [!DNL Audience Manager] 的協力廠商合作夥伴應為我們網路上每個獨特使用者提供對應的ID。

您可以使用下列方法將資料匯入 [!DNL Audience Manager]:

* [ID同步HTTP請求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣告的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件內嵌影像進行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步請 `HTTP` 求 {#id-sync-http}

在ID交換中，格式正確的字 [!DNL URL] 串應該如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>內容提供者的唯一ID(由 <span class="keyword"> Audience Manager指派</span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL（百分比）編碼表示您的唯一使用者ID。 除了編碼保留的ASCII字元外，任何非ASCII字元都應根據UTF-8字元編碼表進行百分比編碼。 </p> <p>如需詳細資訊，請參閱 <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online網站</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>內嵌巨集的編碼URL重新導 <code> ${DD_UUID}</code> 向。 </p> <p>注意：  僅在內容提供者開始呼叫時新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果您使用IAB TCF的 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此參數。</a></p> <p><code> gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。 </p> <p> <b>注意：</b> 此參數只能與一起使用 <code>gdpr_consent</code>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果您使用IAB TCF的 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此參數。</a></p> <p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>). </p> <p> <b>注意：</b> 此參數只能與一起使用 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 宣告的ID事件 {#declared-id-event}

如需詳細資訊，請參 [閱宣告的ID](../../../features/declared-ids.md)。

## 從電子郵件內嵌影像進行ID同步 {#id-sync-email-image}

透過電子郵件影像比對ID的格式與上述相同。 但請注意，電子郵件中的影像必須已啟用，才能運作。 這可能會影響透過電子郵件進行的ID同步，因為大部分的郵件系統都預設會停用影像。

>[!MORELIKETHIS]
>
>* [資料收集元件](../../../reference/system-components/components-data-collection.md)

