---
description: 說明初始HTTP呼叫中使用的語法和引數，以便同步廠商和Audience Manager之間的使用者ID。 ID同步可在您將資料分類法傳送至Audience Manager後開始。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: 傳入資料傳輸的ID同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# 傳入資料傳輸的ID同步 {#id-synchronization-for-inbound-data-transfers}

說明初始`HTTP`呼叫中所使用的語法和引數，以便在廠商和[!DNL Audience Manager]之間同步使用者ID。 ID同步會在您將資料分類傳送至[!DNL Audience Manager]後開始。

ID同步是內送、非同步資料傳輸程式中的第一個步驟。 在此步驟中，[!DNL Audience Manager]和廠商會比較並比對各自網站訪客的ID。 例如，[!DNL Audience Manager]客戶可能透過識別碼123認識使用者。 不過，您的資料合作夥伴可以使用ID 456識別此使用者。 同步處理可讓[!DNL Audience Manager]和資料廠商調解這些不同的ID，並識別其各自系統中的使用者。 完成之後，[!DNL Audience Manager]和您的協力廠商合作夥伴應該針對在我們的網路上看到的每個不重複使用者，設定對應的ID。

您可以使用下列方法將您的資料匯入[!DNL Audience Manager]：

* [ID同步HTTP要求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣告ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件內嵌影像進行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步`HTTP`要求 {#id-sync-http}

在ID交換中，正確格式化的[!DNL URL]字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>內容提供者的唯一識別碼(由<span class="keyword">Audience Manager</span>指派)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>不重複使用者ID的URL （百分比）編碼表示法。 除了編碼保留的ASCII字元外，任何非ASCII字元都應根據UTF-8字元編碼表進行百分比編碼。 </p> <p>如需詳細資訊，請參閱<a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a>網站。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>內嵌巨集<code> ${DD_UUID}</code>的編碼URL重新導向。 </p> <p>注意：只有在內容提供者起始呼叫時才會新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>可選。如果您使用適用於IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此引數。</a></p> <p><code> gdpr</code> 可為0 （GDPR不適用）或1 （GDPR適用）。 </p> <p> <b>注意：</b>此引數只能與<code>gdpr_consent</code>一起使用。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>可選。如果您使用適用於IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式，請新增此引數。</a></p> <p><code>gdpr_consent</code> 是URL安全base64編碼GDPR同意字串（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>）。 </p> <p> <b>注意：</b>此引數只能與<code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID]個事件 {#declared-id-event}

如需詳細資訊，請參閱[宣告識別碼](../../../features/declared-ids.md)。

## 從電子郵件內嵌影像進行ID同步 {#id-sync-email-image}

透過電子郵件影像比對ID的格式與上方所示相同。 但是請注意，必須啟用電子郵件中的影像才能讓此功能正常運作。 這可能會影響透過電子郵件的ID同步，因為大多數郵件系統預設會停用影像。

>[!MORELIKETHIS]
>
>* [資料收集元件](../../../reference/system-components/components-data-collection.md)
