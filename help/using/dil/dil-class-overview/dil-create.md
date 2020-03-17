---
description: 建立合作夥伴專屬的DIL例項。
seo-description: 建立合作夥伴專屬的DIL例項。
seo-title: DIL建立
solution: Audience Manager
title: DIL建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# DIL建立方法{#dil-create}

## DIL建立 {#dil-create-new}

建立特定於合作夥伴的 [!UICONTROL DIL] 實例。

**函式簽名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>屬 `visitorService` 性永 *遠為* 必要。 此處列出的其他屬性是可選的，除非另有說明。

`initConfig` 接受下列元素：

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>該屬性會設定 <span class="keyword">Audience Manager</span> 所使用的容器 ID 以供 ID 同步之用。如果您已 <code> containerNSID </code> 在多個網站上 <span class="wintitle"> 部 </span> 署DIL，請加以設定。 這些網站都會有其專屬的容器ID和ID同步。 當您只有1個網站時，容器ID預設為0，您不需要正確設定。 請連絡您的顧問，以取得網站及其容器ID的清單。 </p> <p>在 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Adobe Experience Platform Identity Service中，屬 </a>性與DIL <code> idSyncContainerID </code> 中 <code> containerNSID </code> 的相 <span class="wintitle"> 對應 </span>。 如果您在多個網站上使用 <span class="wintitle"> DIL </span> 和 <i>ID服務</i> ，請注意下列事項： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">對於每個網站，請在和上設定相同的容 <code> containerNSID </code> 器ID <code> idSyncContainerID </code>。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">DIL <span class="wintitle"> 和ID服 </span> 務都會嘗試傳送ID同步檔至我們的資料收集iFrame。 不過，iFrame可確保 <span class="wintitle"> DIL </span> 不會觸發ID同步。 這可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有 <span class="wintitle"> DIL </span> 會傳送資料至 <a href="../../features/destinations/destinations.md"> URL目的地 </a>。 </li> 
     </ul> </p> <p>另請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>在每次事件 <a href="../../features/declared-ids.md"> 呼叫時傳送 </a> Declared ID變數至 <span class="keyword"> Audience Manager </span>。 </p> 
    </draft-comment> <p> <code> delcaredId </code> 用於傳遞以下任一項： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:Audience Manager指派給您的資料合作 <span class="keyword"> 夥伴ID </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:您的使用者唯一ID。 </li> 
    </ul> <p> <p>重要： 僅對您的ID使用未編碼值。 編碼會建立雙重編碼識別碼。 </p> </p> <p> <p>注意： 如果您使用 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Adobe Experience Platform Identity Service，請 </a>使用方法設定客戶ID，而 <code> setCustomerIDs </code> 非 <span class="wintitle"> DIL </span>。 See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 如果為true，則會將所有請求（IFRAME、事件呼叫、ID同步和目的地）從執行中刪除，直到觸 <code> Page Load </code> 發事件。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> False 依預設，這表示 <span class="keyword"> Audience Manager會 </span> 在合作夥伴的網域中設定Cookie（設定第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL 8.0版( <span class="wintitle"> 2018年8月 </span> 發行)已淘汰此元素。 請改 <code> visitor.disableIdSyncs </code> 用Adobe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> Experience Platform Identity Service中的功能。 </p> </p> <p> 如 <code> true </code>果，將不會將目標發佈IFRAME附加至DOM或引發目標。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL 8.0版( <span class="wintitle"> 2018年8月 </span> 發行)已淘汰此元素。 請改 <code> visitor.disableIdSyncs </code> 用Adobe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> Experience Platform Identity Service中的功能。 </p> </p> <p>停用 ID 同步。使用DIL v6.2+和訪客ID服務時，您必須停用ID同步。 函 <code> visitorService </code> 數（請參閱下面的范常式式碼）負責此作業。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 設為啟 <code> true </code> 用頁面上所有 <span class="wintitle"> DIL例 </span> 項的錯誤報告。 僅適用於布爾 <code> true </code> 型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL 8.0版( <span class="wintitle"> 2018年8月 </span> 發行)已淘汰此元素。 請改 <code> visitor.idSyncSSLUseAkamai </code> 用Adobe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"></a> Experience Platform Identity Service中的功能。 </p> </p> <p> 指定目標發佈範本是否應該針對 HTTPS 連線使用 Akamai。每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將一個鍵值對的值關聯到另一個鍵值對。 請參 <a href="../../dil/dil-use-cases.md#map-key-values"> 閱將索引鍵值映射至其他索引鍵 </a>。 隨2.4版發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p>金 <code> namespace </code> 鑰值配對包含您的 <span class="keyword"> Experience Cloud組織 </span> ID。 如果您沒有此ID，可在Experience Cloud控制面板的「管 <span class="wintitle"> 理」 </span> 區段中找 <span class="keyword"> 到該 </span> ID。 您需要管理員權限才能檢視此控制面板。 請參閱產 <a href="../../faq/faq-features.md"> 品功能常見問答集 </a> 與管 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> 理——使用者管理與常見問答集 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p> Audience Manager提供的合 <span class="keyword"> 作夥伴名 </span>稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 刪除指令碼和回呼。 預設為 <code> False </code>. 僅適用於目前 <span class="wintitle"> 的DIL </span> 例項。 隨v3.3發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>使用從 <span class="keyword"> Audience Manager傳回的唯一使用者ID來設定Cookie </span>。 請參閱 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie屬 </a>性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>DIL <span class="wintitle"> 6.2或更 </span> 新版本必需。 </p> <p> DIL依賴 <code> setCustomerIDs </code> Adobe Experience Platform Identity Service <span class="wintitle"> 中的功能， </span> 將宣告的ID傳遞至 <span class="keyword"> Audience Manager </span>。 See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**程式碼範例**

範例呼 [!UICONTROL DIL] 叫可能類似於下列：

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

成功的回應會傳回 [!UICONTROL DIL] 例項。 如果您的程式碼設定不當，或在遇到錯誤時，失敗的嘗試會傳回錯誤物件（未拋出）。

## uuidCookie屬性 {#uuidcookie-props}

定義變數使用的 `uuidCookie` 屬性。 此變數是方法的一 `DIL.create` 部分。

`uuidCookie` 具有以下屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Cookie存留期（預設為100天）。 |
| `path` | Cookie路徑，例如 `'/test'` ( `/` 預設)。 |
| `domain` | Cookie設定所在的網域，例如 `'adobe.com'` ( `'.'+document.domain` 預設)。 |
| `secure` | 設定標幟，僅透過HTTPS連線傳送資料。 |

## visitorService屬性 {#visitor-service-props}

定義變數使用的 `visitorService` 屬性。 此變數是方法的一 `DIL.create` 部分。

`visitorService` 具有以下屬性：

| 名稱 | 類型 | 說明 |
|---|---|---|
| `namespace` | 字串 | 必填。代表Experience Cloud組織ID。 Experience Cloud核心服務功能需要此項功能。 用於執行個體化訪客ID功能的參數相同。 |

**程式碼範例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
