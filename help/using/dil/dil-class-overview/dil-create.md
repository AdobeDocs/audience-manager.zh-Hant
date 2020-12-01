---
description: 建立合作夥伴專屬的DIL例項。
seo-description: 建立合作夥伴專屬的DIL例項。
seo-title: DIL 建立
solution: Audience Manager
title: DIL 建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 11%

---


# DIL建立方法{#dil-create}

## DIL 建立 {#dil-create-new}

建立特定於合作夥伴的[!UICONTROL DIL]實例。

**函式簽名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>`visitorService`屬性為&#x200B;*always*。 此處列出的其他屬性是可選的，除非另有說明。

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
   <td colname="col3"> <p>該屬性會設定 <span class="keyword">Audience Manager</span> 所使用的容器 ID 以供 ID 同步之用。如果您已部署在多個網站上的<span class="wintitle"> DIL </span>，您可設定<code> containerNSID </code>。 這些網站都會有其專屬的容器ID和ID同步。 當您只有1個網站時，容器ID預設為0，您不需要正確設定。 請連絡您的顧問，以取得網站及其容器ID的清單。 </p> <p>在<a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>中，屬性<code> idSyncContainerID </code>對應於<span class="wintitle"> DIL </span>中的<code> containerNSID </code>。 如果您使用<span class="wintitle"> DIL </span> <i>和</i>跨多個網站的ID服務，請注意： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">針對每個網站，在<code> containerNSID </code>和<code> idSyncContainerID </code>上設定相同的容器ID。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span>和ID服務都會嘗試傳送ID同步至我們的資料收集iFrame。 不過，iFrame可確保<span class="wintitle"> DIL </span>不會觸發ID同步。 這可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有<span class="wintitle"> DIL </span>會將資料傳送至<a href="../../features/destinations/destinations.md"> URL目的地</a>。 </li> 
     </ul> </p> <p>另請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 用於傳遞以下任一項： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:Audience Manager指派給您的資料合作 <span class="keyword"> 夥伴ID </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:您的使用者唯一ID。 </li> 
    </ul> <p> <p>重要： 僅對您的ID使用未編碼值。 編碼會建立雙重編碼識別碼。 </p> </p> <p> <p>注意： 如果您使用<a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>，請使用<code> setCustomerIDs </code>方法來設定客戶ID，而非使用<span class="wintitle"> DIL </span>。 請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">客戶ID和驗證狀態</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 如果為true，則會將所有請求（IFRAME、事件呼叫、ID同步和目的地）從執行中刪除，直到<code> Page Load </code>事件觸發。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> False 依預設，這表示<span class="keyword"> Audience Manager </span>會在合作夥伴的網域中設定Cookie（設定第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）已淘汰此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函式</a>。 </p> </p> <p> 如果<code> true </code>，將不會將目標發佈IFRAME附加至DOM或引發目標。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）已淘汰此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函式</a>。 </p> </p> <p>停用 ID 同步。使用DIL v6.2+和訪客ID服務時，您必須停用ID同步。 <code> visitorService </code>函式（請參閱下面的范常式式碼）會處理此作業。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 設為<code> true </code>以啟用頁面上所有<span class="wintitle"> DIL </span>例項的錯誤報告。 僅適用於布林<code> true </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）已淘汰此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.idSyncSSLUseAkamai </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external">函式</a>。 </p> </p> <p> 指定目標發佈範本是否應該針對 HTTPS 連線使用 Akamai。每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將一個鍵值對的值關聯到另一個鍵值對。 請參閱<a href="../../dil/dil-use-cases.md#map-key-values">將鍵值映射至其他鍵</a>。 隨2.4版發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p><code> namespace </code>金鑰值配對包含您的<span class="keyword"> Experience Cloud </span>組織ID。 如果您沒有此ID，則可在<span class="keyword"> Experience Cloud </span>控制面板的<span class="wintitle">管理</span>區段中找到它。 您需要管理員權限才能檢視此控制面板。 請參閱<a href="../../faq/faq-features.md">產品功能常見問答集</a>和<a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external">管理——使用者管理和常見問答集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p> <span class="keyword"> Audience Manager </span>提供的合作夥伴名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 刪除指令碼和回呼。 預設為 <code> False </code>. 僅適用於當前<span class="wintitle"> DIL </span>實例。 隨v3.3發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>使用從<span class="keyword"> Audience Manager </span>傳回的唯一使用者ID來設定Cookie。 請參閱<a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie屬性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DIL </span> 6.2或更新版本為必要項目。 </p> <p> DIL依賴<span class="wintitle"> Adobe Experience Platform Identity Service </span>中的<code> setCustomerIDs </code>函式，將宣告的ID傳入<span class="keyword"> Audience Manager </span>。 如需詳細資訊，請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">客戶ID和驗證狀態</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**程式碼範例**

範例[!UICONTROL DIL]呼叫看起來可能類似下列：

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

成功的響應返回[!UICONTROL DIL]實例。 如果您的程式碼設定不當，或在遇到錯誤時，失敗的嘗試會傳回錯誤物件（未拋出）。

## uuidCookie屬性{#uuidcookie-props}

定義`uuidCookie`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

`uuidCookie` 具有以下屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | Cookie名稱（預設值為`aam_did`）。 |
| `days` | Cookie存留期（預設為100天）。 |
| `path` | Cookie路徑，例如`'/test'`（預設值為`/`）。 |
| `domain` | Cookie所設定的網域，例如`'adobe.com'`（預設值為`'.'+document.domain`）。 |
| `secure` | 設定標幟，僅透過HTTPS連線傳送資料。 |

## visitorService屬性{#visitor-service-props}

定義`visitorService`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

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
