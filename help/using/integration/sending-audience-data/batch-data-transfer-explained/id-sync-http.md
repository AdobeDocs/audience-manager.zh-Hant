---
description: 描述初始HTTP調用中用於在供應商和Audience Manager之間同步用戶ID的語法和參數。 ID同步可在您將資料分類發送到Audience Manager後開始。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: 傳入資料傳輸的 ID 同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 7%

---

# 傳入資料傳輸的 ID 同步 {#id-synchronization-for-inbound-data-transfers}

描述初始中使用的語法和參數 `HTTP` 調用以在供應商和 [!DNL Audience Manager]。 ID同步可在將資料分類發送到 [!DNL Audience Manager]。

ID同步是入站非同步資料傳輸過程中的第一步。 在這一步， [!DNL Audience Manager] 供應商將各自站點訪問者的ID進行比較和匹配。 例如， [!DNL Audience Manager] 客戶可能通過ID 123瞭解用戶。 但是，您的資料合作夥伴可以識別ID為456的此用戶。 同步過程允許 [!DNL Audience Manager] 以及資料供應商，以協調這些不同的ID並識別各自系統中的用戶。 完成後， [!DNL Audience Manager] 您的第三方合作夥伴應為我們網路上看到的每個唯一用戶擁有相應的ID。

可以使用以下方法將資料 [!DNL Audience Manager]:

* [ID同步HTTP請求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [聲明的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件嵌入式映像進行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步 `HTTP` 請求 {#id-sync-http}

在ID交換中，格式正確 [!DNL URL] 字串應如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>內容提供程式的唯一ID(由 <span class="keyword"> Audience Manager</span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL（百分比）編碼的唯一用戶ID的表示法。 除對保留的ASCII字元進行編碼外，還應根據UTF-8字元編碼表對任何非ASCII字元進行百分比編碼。 </p> <p>有關詳細資訊，請參見 <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL線上編碼/解碼</a> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>帶宏的編碼URL重定向 <code> ${DD_UUID}</code> 嵌入其中。 </p> <p>注：僅在內容提供程式啟動調用時添加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果使用 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience ManagerIAB TCF插件。</a></p> <p><code> gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。 </p> <p> <b>注：</b> 此參數只能與 <code>gdpr_consent</code>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>選填。如果使用 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience ManagerIAB TCF插件。</a></p> <p><code>gdpr_consent</code> 是URL安全的base64編碼的GDPR同意字串(請參見 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規範</a>)。 </p> <p> <b>注：</b> 此參數只能與 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Event {#declared-id-event}

有關詳細資訊，請參見 [聲明的ID](../../../features/declared-ids.md)。

## 從電子郵件嵌入式映像進行ID同步 {#id-sync-email-image}

通過電子郵件影像匹配ID的格式與上面所示相同。 但請注意，必須啟用電子郵件中的影像才能使此功能正常工作。 這會影響通過電子郵件進行的ID同步，因為大多數郵件系統預設禁用映像。

>[!MORELIKETHIS]
>
>* [資料收集元件](../../../reference/system-components/components-data-collection.md)

