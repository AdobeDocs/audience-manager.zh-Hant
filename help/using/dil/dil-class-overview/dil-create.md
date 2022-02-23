---
description: 建立特定於合作夥伴的DIL實例。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL 建立
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 9%

---

# DIL建立方法{#dil-create}

## DIL 建立 {#dil-create-new}

建立特定於合作夥伴的 [!UICONTROL DIL] 實例。

**函式簽名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>的 `visitorService` 屬性 *總是* 。 此處列出的其他屬性是可選的，除非另有說明。

`initConfig` 接受以下元素：

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
   <td colname="col3"> <p>該屬性會設定 <span class="keyword">Audience Manager</span> 所使用的容器 ID 以供 ID 同步之用。你可以 <code> containerNSID </code> 如果你 <span class="wintitle"> DIL </span> 跨多個站點部署。 這些站點中的每個站點都將具有自己的容器ID和ID同步。 當您只有1個站點時，預設情況下容器ID為0，您無需正確設定。 請與咨詢人聯繫，以獲取您的站點及其容器ID的清單。 </p> <p>在 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform身份服務 </a>，屬性 <code> idSyncContainerID </code> 對應 <code> containerNSID </code> 在 <span class="wintitle"> DIL </span>。 如果使用 <span class="wintitle"> DIL </span> <i>和</i> 跨多個站點的ID服務： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">對於每個站點，在 <code> containerNSID </code> 和 <code> idSyncContainerID </code>。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">兩者 <span class="wintitle"> DIL </span> ID服務將嘗試將ID同步發送到我們的資料收集iFrame。 但是，iFrame確保 <span class="wintitle"> DIL </span> 不會觸發ID同步。 這可防止重複。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">僅 <span class="wintitle"> DIL </span> 向 <a href="../../features/destinations/destinations.md"> URL目標 </a>。 </li> 
     </ul> </p> <p>另請參見 <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 用於傳遞以下任一項： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:資料合作夥伴ID由 <span class="keyword"> Audience Manager </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:用戶的唯一ID。 </li> 
    </ul> <p> <p>重要提示：僅對ID使用未編碼值。 編碼將建立雙編碼標識符。 </p> </p> <p> <p>注：如果使用 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform身份服務 </a>，使用 <code> setCustomerIDs </code> 方法代替 <span class="wintitle"> DIL </span>。 請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客戶ID和身份驗證狀態 </a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 如果為true，則將所有請求（IFRAME、事件調用、ID同步和目標）從執行到 <code> Page Load </code> 事件觸發。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> False 預設情況下，這意味著 <span class="keyword"> Audience Manager </span> 在夥伴的域中設定cookie（設定第一方cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要提示：此元素已棄用 <span class="wintitle"> DIL </span> 8.0版（2018年8月發佈）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函式 </a> 在Adobe Experience Platform身份服務。 </p> </p> <p> 如果 <code> true </code>，不會將目標發佈IFRAME附加到DOM或觸發目標。 預設為 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要提示：此元素已棄用 <span class="wintitle"> DIL </span> 8.0版（2018年8月發佈）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函式 </a> 在Adobe Experience Platform身份服務。 </p> </p> <p>停用 ID 同步。使用DILv6.2+和訪問者ID服務時，必須禁用ID同步。 的 <code> visitorService </code> 函式（請參閱下面的示例代碼）將處理此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 設定為 <code> true </code> 啟用錯誤報告 <span class="wintitle"> DIL </span> 實例。 使用布爾值 <code> true </code> 只是。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> <p>重要提示：此元素已棄用 <span class="wintitle"> DIL </span> 8.0版（2018年8月發佈）。 使用 <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> 函式 </a> 在Adobe Experience Platform身份服務。 </p> </p> <p> 指定目標發佈範本是否應該針對 HTTPS 連線使用 Akamai。每位合作夥伴皆啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>將值從一個鍵值對關聯到另一個鍵值對。 請參閱 <a href="../../dil/dil-use-cases.md#map-key-values"> 將鍵值映射到其他鍵 </a>。 隨v2.4發佈。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p>的 <code> namespace </code> 鍵值對包含 <span class="keyword"> Experience Cloud </span> 組織ID。 如果您沒有此ID，可以在 <span class="wintitle"> 管理 </span> 的下界 <span class="keyword"> Experience Cloud </span> 控制項欄。 您需要管理員權限才能查看此儀表板。 查看 <a href="../../faq/faq-features.md"> 產品功能和常見問題 </a> 和 <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> 管理 — 用戶管理和常見問題 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>必填. </p> <p> 合作夥伴名稱，由提供 <span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布林值 </p> </td> 
   <td colname="col3"> <p> 刪除指令碼和回調。 預設為 <code> False </code>. 應用於當前 <span class="wintitle"> DIL </span> 僅實例。 隨v3.3發佈。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>使用從返回的唯一用戶ID設定Cookie <span class="keyword"> Audience Manager </span>。 請參閱 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> UUIDCookie屬性 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>物件 </p> </td> 
   <td colname="col3"> <p>必填項 <span class="wintitle"> DIL </span> 6.2或更高版本。 </p> <p> DIL依靠 <code> setCustomerIDs </code> 函式 <span class="wintitle"> Adobe Experience Platform身份服務 </span> 將聲明的ID傳遞到 <span class="keyword"> Audience Manager </span>。 請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客戶ID和身份驗證狀態 </a> 的子菜單。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**程式碼範例**

示例 [!UICONTROL DIL] 呼叫可能與以下內容類似：

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

成功的響應返回 [!UICONTROL DIL] 實例。 如果代碼配置不正確或遇到錯誤，則失敗嘗試返回錯誤對象（未引發）。

## UUIDCookie屬性 {#uuidcookie-props}

定義由 `uuidCookie` 變數。 此變數是 `DIL.create` 的雙曲餘切值。

`uuidCookie` 具有以下屬性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名稱 | 說明 |
|---|---|
| `name` | Cookie名稱( `aam_did` 為預設值)。 |
| `days` | Cookie生存期（預設為100天）。 |
| `path` | Cookie路徑，例如， `'/test'` ( `/` 為預設值)。 |
| `domain` | Cookie所在的域，例如 `'adobe.com'` ( `'.'+document.domain` 為預設值)。 |
| `secure` | 設定僅通過HTTPS連接發送資料的標誌。 |

## 訪問者服務屬性 {#visitor-service-props}

定義由 `visitorService` 變數。 此變數是 `DIL.create` 的雙曲餘切值。

`visitorService` 具有以下屬性：

| 名稱 | 類型 | 說明 |
|---|---|---|
| `namespace` | 字串 | 必填。表示Experience Cloud組織ID。 這是Experience Cloud核心服務功能所需的。 用於實例化訪問者ID功能的參數相同。 |

**程式碼範例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
