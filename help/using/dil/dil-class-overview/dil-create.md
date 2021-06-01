---
description: 建立合作夥伴特定的DIL例項。
seo-description: 建立合作夥伴特定的DIL例項。
seo-title: DIL 建立
solution: Audience Manager
title: DIL 建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL實作
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '827'
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
>`visitorService`屬性為&#x200B;*always*&#x200B;必要。 此處列出的其他屬性為選用屬性，除非另有說明。

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
   <td colname="col3"> <p>該屬性會設定 <span class="keyword">Audience Manager</span> 所使用的容器 ID 以供 ID 同步之用。如果已在多個站點上部署<span class="wintitle">DIL</span>，則可以設定<code> containerNSID </code>。 這些網站都會有各自的容器ID和ID同步。 當您只有1個網站時，容器ID依預設為0，您不需要正確設定。 請連絡您的顧問，以取得網站及其容器ID的清單。 </p> <p>在<a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>中，屬性<code> idSyncContainerID </code>對應於<span class="wintitle">DIL</span>中的<code> containerNSID </code>。 如果您使用<span class="wintitle">DIL</span> <i>和</i>跨多個網站的ID服務，請注意下列事項： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">對於每個網站，在<code> containerNSID </code>和<code> idSyncContainerID </code>上設定相同的容器ID。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle">DIL</span>和ID服務都會嘗試將ID同步傳送至資料收集iFrame。 不過，iFrame可確保<span class="wintitle">DIL</span>不會引發ID同步。 這可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有<span class="wintitle">DIL</span>會將資料傳送至<a href="../../features/destinations/destinations.md"> URL目的地</a>。 </li> 
     </ul> </p> <p>另請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 會用來傳遞以下任一項： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:依Audience Manager指派給您的資料合作夥伴 <span class="keyword"> ID  </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:您的使用者唯一ID。 </li> 
    </ul> <p> <p>重要： 請僅對ID使用未編碼的值。 編碼將建立雙重編碼的識別碼。 </p> </p> <p> <p>注意： 若您使用<a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>，請使用<code> setCustomerIDs </code>方法設定客戶ID，而非使用<span class="wintitle">DIL</span>。 請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">客戶ID和驗證狀態</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 若為true，則會在<code> Page Load </code>事件引發之前，將所有請求（IFRAME、事件呼叫、ID同步和目的地）從執行中刪除。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> False 依預設，這表示<span class="keyword">Audience Manager</span>會在合作夥伴的網域中設定Cookie（設定第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle">DIL</span> 8.0版（2018年8月發行）已棄用此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函式</a>。 </p> </p> <p> 如果<code> true </code>，不會將目標發佈IFRAME附加至DOM或引發目的地。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle">DIL</span> 8.0版（2018年8月發行）已棄用此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函式</a>。 </p> </p> <p>停用 ID 同步。使用DILv6.2+和訪客ID服務時，您必須停用ID同步。 <code> visitorService </code>函式（請參閱下方的范常式式碼）負責此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 設為<code> true </code> ，以啟用頁面上所有<span class="wintitle">DIL</span>例項的錯誤報告。 僅適用於布林值<code> true </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要： <span class="wintitle">DIL</span> 8.0版（2018年8月發行）已棄用此元素。 請改用Adobe Experience Platform Identity Service中的<code> visitor.idSyncSSLUseAkamai </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external">函式</a>。 </p> </p> <p> 指定目標發佈範本是否應該針對 HTTPS 連線使用 Akamai。每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將值從一個索引鍵值組關聯至另一個。 請參閱<a href="../../dil/dil-use-cases.md#map-key-values">將索引鍵值映射至其他索引鍵</a>。 隨v2.4發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p><code> namespace </code>機碼值組包含您的<span class="keyword">Experience Cloud</span>組織ID。 如果您沒有此ID，可以在<span class="keyword">Experience Cloud</span>控制面板的<span class="wintitle">管理</span>區段中找到。 您需要管理員權限才能檢視此控制面板。 請參閱<a href="../../faq/faq-features.md">產品特色與功能常見問題集</a>和<a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external">管理 — 使用者管理和常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p> <span class="keyword">Audience Manager</span>提供的合作夥伴名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 移除指令碼和回呼。 預設為 <code> False </code>. 僅適用於當前<span class="wintitle">DIL</span>實例。 隨v3.3發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>使用從<span class="keyword">Audience Manager</span>傳回的不重複使用者ID設定Cookie。 請參閱<a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie屬性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DIL</span> 6.2或更高版本時為必填。 </p> <p> DIL仰賴<span class="wintitle"> Adobe Experience Platform Identity Service </span>中的<code> setCustomerIDs </code>函式，將宣告ID傳遞至<span class="keyword">Audience Manager</span>。 如需詳細資訊，請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">客戶ID和驗證狀態</a> 。 </p> </td> 
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

成功的回應會傳回[!UICONTROL DIL]例項。 如果您的程式碼設定不正確或每當發生錯誤，失敗的嘗試會傳回錯誤物件（未擲回）。

## uuidCookie屬性{#uuidcookie-props}

定義`uuidCookie`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

`uuidCookie` 具有下列屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | Cookie名稱（預設為`aam_did`）。 |
| `days` | Cookie期限（預設為100天）。 |
| `path` | Cookie路徑，例如`'/test'`（預設為`/`）。 |
| `domain` | Cookie設定的網域，例如`'adobe.com'`（預設為`'.'+document.domain`）。 |
| `secure` | 設定標幟以僅透過HTTPS連線傳送資料。 |

## visitorService屬性{#visitor-service-props}

定義`visitorService`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

`visitorService` 具有下列屬性：

| 名稱 | 類型 | 說明 |
|---|---|---|
| `namespace` | 字串 | 必填。代表Experience Cloud組織ID。 這是Experience Cloud核心服務功能所需的。 用來具現化訪客ID功能的相同參數。 |

**程式碼範例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
