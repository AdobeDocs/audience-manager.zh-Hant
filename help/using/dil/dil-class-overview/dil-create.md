---
description: 建立合作夥伴特定的DIL例項。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# DIL建立方法{#dil-create}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe在此點之後不會開發[!DNL DIL]。 建議客戶針對[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)。

## DIL建立 {#dil-create-new}

建立合作夥伴特定的[!UICONTROL DIL]執行個體。

**函式簽章：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>`visitorService`屬性是&#x200B;*一律需要*。 除非另有指示，否則此處列出的其他屬性是選用的。

`initConfig`接受下列元素：

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
   <td colname="col3"> <p>此屬性會設定<span class="keyword">Audience Manager</span>所使用的容器ID以供ID同步之用。 如果您將<span class="wintitle">DIL</span>部署在多個網站，請設定<code> containerNSID </code>。 每個網站都有各自的容器ID和ID同步。 當您只有1個網站時，容器ID預設為0，您不需要正確設定。 請聯絡您的顧問，以取得您的網站清單及其容器ID。 </p> <p>在<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant" format="https" scope="external"> Adobe Experience Platform Identity Service </a>中，屬性<code> idSyncContainerID </code>對應至<span class="wintitle">DIL</span>中的<code> containerNSID </code>。 如果您在多個網站上使用<span class="wintitle">DIL</span> <i>和</i> ID服務，請注意下列事項： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">針對每個網站，在<code> containerNSID </code>和<code> idSyncContainerID </code>上設定相同的容器ID。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle">DIL</span>和ID服務都會嘗試將ID同步傳送至我們的資料收集iFrame。 不過，iFrame會確保<span class="wintitle">DIL</span>不會引發ID同步處理。 如此可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有<span class="wintitle">DIL</span>會將資料傳送至<a href="../../features/destinations/destinations.md"> URL目的地</a>。 </li> 
     </ul> </p> <p>另請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=zh-Hant" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code>是用來傳入： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>： <span class="keyword">Audience Manager</span>指派給您的資料合作夥伴識別碼。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>：您的使用者唯一ID。 </li> 
    </ul> <p> <p>重要：請僅將未編碼的值用於ID。 編碼將會建立雙重編碼的識別碼。 </p> </p> <p> <p>注意：如果您使用<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant" format="https" scope="external"> Adobe Experience Platform Identity Service </a>，請使用<code> setCustomerIDs </code>方法設定客戶ID，而非<span class="wintitle">DIL</span>。 檢視<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hant" format="https" scope="external">客戶ID與驗證狀態</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 若為true，則會延遲執行所有要求（IFRAME、事件呼叫、ID同步和目的地），直到<code> Page Load </code>事件引發為止。 預設值為<code> false </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 預設為False，表示<span class="keyword">Audience Manager</span>在合作夥伴的網域中設定Cookie （設定第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已在<span class="wintitle">DIL</span> 8.0版（2018年8月發行）中棄用。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=zh-Hant" format="https" scope="external">函式</a>。 </p> </p> <p> 如果<code> true </code>，將不會將目的地發佈IFRAME附加至DOM或引發目的地。 預設值為<code> false </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已在<span class="wintitle">DIL</span> 8.0版（2018年8月發行）中棄用。 請改用Adobe Experience Platform Identity Service中的<code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=zh-Hant" format="https" scope="external">函式</a>。 </p> </p> <p>停用ID同步。 使用DILv6.2+和訪客ID服務時，您必須停用ID同步。 <code> visitorService </code>函式（請參閱下列範常式式碼）負責此作業。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 設定為<code> true </code>以啟用頁面上所有<span class="wintitle">DIL</span>執行個體的錯誤報告。 僅適用於布林值<code> true </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已在<span class="wintitle">DIL</span> 8.0版（2018年8月發行）中棄用。 請改用Adobe Experience Platform Identity Service中的<code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=zh-Hant" format="https" scope="external">函式</a>。 </p> </p> <p> 指定目的地發佈範本是否應該針對HTTPS連線使用Akamai。 每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將一個機碼值組的值與另一個機碼值組建立關聯。 請參閱<a href="../../dil/dil-use-cases.md#map-key-values">將索引鍵值對應到其他索引鍵</a>。 隨v2.4發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填。 </p> <p><code> namespace </code>機碼值組包含您的<span class="keyword">Experience Cloud</span>組織識別碼。 如果您沒有此ID，可以在<span class="keyword">Experience Cloud</span>儀表板的<span class="wintitle">管理</span>區段中找到。 您需要管理員許可權才能檢視此儀表板。 請參閱<a href="../../faq/faq-features.md">產品特色與功能常見問題集</a>與<a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=zh-Hant" format="https" scope="external">管理 — 使用者管理與常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填。 </p> <p> 由<span class="keyword">Audience Manager</span>提供的合作夥伴名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 移除指令碼和回呼。 預設值為<code> False </code>。 僅適用於目前的<span class="wintitle">DIL</span>執行個體。 隨v3.3發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>使用從<span class="keyword">Audience Manager</span>傳回的不重複使用者識別碼設定Cookie。 請參閱<a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie屬性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DIL</span> 6.2或更新版本為必要。 </p> <p> DIL仰賴<span class="wintitle"> Adobe Experience Platform Identity Service </span>中的<code> setCustomerIDs </code>函式將宣告的ID傳遞至<span class="keyword">Audience Manager</span>。 如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hant" format="https" scope="external">客戶ID與驗證狀態</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**程式碼範例**

範例[!UICONTROL DIL]呼叫可能類似於以下內容：

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

成功的回應傳回[!UICONTROL DIL]執行個體。 如果您的程式碼設定不正確或發生錯誤，失敗的嘗試會傳回錯誤物件（未擲回）。

## uuidCookie屬性 {#uuidcookie-props}

定義`uuidCookie`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

`uuidCookie`具有以下屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | Cookie名稱（`aam_did`為預設值）。 |
| `days` | Cookie期限（預設為100天）。 |
| `path` | Cookie路徑，例如`'/test'` （預設為`/`）。 |
| `domain` | Cookie設定所在的網域，例如`'adobe.com'` （`'.'+document.domain`為預設值）。 |
| `secure` | 設定旗標以僅透過HTTPS連線傳送資料。 |

## visitorService屬性 {#visitor-service-props}

定義`visitorService`變數使用的屬性。 此變數是`DIL.create`方法的一部分。

`visitorService`具有以下屬性：

| 名稱 | 類型 | 說明 |
|---|---|---|
| `namespace` | 字串 | 必填。代表Experience Cloud組織ID。 這是Experience Cloud核心服務功能所需的專案。 用來例項化訪客ID功能的相同引數。 |

**程式碼範例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
