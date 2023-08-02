---
description: 建立合作夥伴特定的DIL例項。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL 建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 8%

---

# DIL建立方法{#dil-create}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超出此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

## DIL 建立 {#dil-create-new}

建立合作夥伴特定的 [!UICONTROL DIL] 執行個體。

**函式簽章：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>此 `visitorService` 屬性為 *一直* 必填。 除非另有指示，否則此處列出的其他屬性是選用的。

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
   <td colname="col3"> <p>該屬性會設定 <span class="keyword">Audience Manager</span> 所使用的容器 ID 以供 ID 同步之用。您可以設定 <code> containerNSID </code> 若您擁有 <span class="wintitle"> DIL </span> 跨多個網站部署。 每個網站都有各自的容器ID和ID同步。 當您只有1個網站時，容器ID預設為0，您不需要正確設定。 請聯絡您的顧問，以取得您的網站清單及其容器ID。 </p> <p>在 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity服務 </a>，屬性 <code> idSyncContainerID </code> 對應至 <code> containerNSID </code> 在 <span class="wintitle"> DIL </span>. 如果您使用 <span class="wintitle"> DIL </span> <i>和</i> 跨多個網站的ID服務： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">針對每個網站，在設定相同的容器ID <code> containerNSID </code> 和 <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">兩者 <span class="wintitle"> DIL </span> 而且ID服務會嘗試將ID同步傳送至我們的資料收集iFrame。 不過，iFrame可確保 <span class="wintitle"> DIL </span> 將不會引發ID同步。 如此可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">僅限 <span class="wintitle"> DIL </span> 將資料傳送至 <a href="../../features/destinations/destinations.md"> URL目的地 </a>. </li> 
     </ul> </p> <p>另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 用於傳入： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>：資料合作夥伴ID由指派給您 <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>：您的使用者唯一ID。 </li> 
    </ul> <p> <p>重要：請僅將未編碼的值用於ID。 編碼將會建立雙重編碼的識別碼。 </p> </p> <p> <p>附註：如果您使用 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity服務 </a>，使用設定客戶ID <code> setCustomerIDs </code> 方法而非 <span class="wintitle"> DIL </span>. 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客戶ID和驗證狀態 </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 如果為true，則會延遲執行所有要求（IFRAME、事件呼叫、ID同步和目的地），直到 <code> Page Load </code> 事件會引發。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> False 根據預設，這表示 <span class="keyword"> Audience Manager </span> 在合作夥伴的網域中設定Cookie （設定第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已過時 <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函式 </a> 改用Adobe Experience Platform Identity Service。 </p> </p> <p> 如果 <code> true </code>，不會將目的地發佈IFRAME附加至DOM或引發目的地。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已過時 <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函式 </a> 改用Adobe Experience Platform Identity Service。 </p> </p> <p>停用 ID 同步。使用DILv6.2+和訪客ID服務時，您必須停用ID同步。 此 <code> visitorService </code> 函式（請參閱下面的範常式式碼）會負責此作業。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 將設為 <code> true </code> 啟用所有錯誤報告 <span class="wintitle"> DIL </span> 頁面上的例項。 與布林值搭配使用 <code> true </code> 僅限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要：此元素已過時 <span class="wintitle"> DIL </span> 8.0版（2018年8月發行）。 使用 <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> 函式 </a> 改用Adobe Experience Platform Identity Service。 </p> </p> <p> 指定目標發佈範本是否應該針對 HTTPS 連線使用 Akamai。每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將一個機碼值組的值與另一個機碼值組建立關聯。 另請參閱 <a href="../../dil/dil-use-cases.md#map-key-values"> 將索引鍵值對應到其他索引鍵 </a>. 隨v2.4發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p>此 <code> namespace </code> 機碼值組包含您的 <span class="keyword"> Experience Cloud </span> 組織ID。 如果您沒有此ID，可以在 <span class="wintitle"> 管理 </span> 的區段 <span class="keyword"> Experience Cloud </span> 儀表板。 您需要管理員許可權才能檢視此儀表板。 請參閱 <a href="../../faq/faq-features.md"> 產品特色與功能常見問題集 </a> 和 <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> 管理 — 使用者管理與常見問題 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p> 提供的合作夥伴名稱 <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 移除指令碼和回呼。 預設為 <code> False </code>. 套用至目前 <span class="wintitle"> DIL </span> 僅限執行個體。 隨v3.3發行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>以傳回的不重複使用者ID設定Cookie <span class="keyword"> Audience Manager </span>. 另請參閱 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie屬性 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>必填： <span class="wintitle"> DIL </span> 6.2或更新版本。 </p> <p> DIL仰賴 <code> setCustomerIDs </code> 中的函式 <span class="wintitle"> Adobe Experience Platform Identity服務 </span> 將已宣告ID傳遞至 <span class="keyword"> Audience Manager </span>. 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客戶ID和驗證狀態 </a> 以取得詳細資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**程式碼範例**

範例 [!UICONTROL DIL] 呼叫可能類似於以下內容：

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

成功的回應會傳回 [!UICONTROL DIL] 執行個體。 如果您的程式碼設定不正確或發生錯誤，失敗的嘗試會傳回錯誤物件（未擲回）。

## uuidCookie屬性 {#uuidcookie-props}

定義使用的屬性 `uuidCookie` 變數中。 此變數屬於 `DIL.create` 方法。

`uuidCookie` 具有以下屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | Cookie名稱( `aam_did` 為預設值)。 |
| `days` | Cookie期限（預設為100天）。 |
| `path` | Cookie路徑，例如 `'/test'` ( `/` 為預設值)。 |
| `domain` | Cookie設定所在的網域，例如 `'adobe.com'` ( `'.'+document.domain` 為預設值)。 |
| `secure` | 設定旗標以僅透過HTTPS連線傳送資料。 |

## visitorService屬性 {#visitor-service-props}

定義使用的屬性 `visitorService` 變數中。 此變數屬於 `DIL.create` 方法。

`visitorService` 具有以下屬性：

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
