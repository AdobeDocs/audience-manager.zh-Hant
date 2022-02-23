---
description: 聲明的ID的工作方式、設定過程、代碼示例和變數。
keywords: ID同步
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: 宣告 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

如何 [!UICONTROL declared IDs] 工作、設定過程、代碼示例和變數。

## [!UICONTROL Declared ID] 定位 {#declared-id-targeting}

Exchange和同步用戶ID [!DNL Audience Manager] 來自不使用或接受永久儲存機制的設備或瀏覽器，如第三方 [!DNL cookies]。

## 目的 [!UICONTROL Declared ID] 目標 {#declared-id-targeting-purpose}

某些瀏覽器和大多數移動設備不接受第三方 [!DNL cookies]。 這使得很難保留有關站點訪問者或分配持久ID的資訊。 為瞭解決這個問題， [!DNL Audience Manager] 使用 [!UICONTROL DIL] 讓你過去 [!UICONTROL declared IDs] 在活動電話上。 另外， [!UICONTROL declared ID] 可以充當通用ID，該通用ID適用於位於 [!DNL Experience Cloud]。 下表介紹了ID目標/匹配過程：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程序 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>事件調用</b> </td> 
   <td colname="col2"> <p>要工作，你需要 <span class="wintitle"> DIL </span> 和 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform身份服務 </a> 頁碼。 <span class="wintitle"> DIL </span> 得 <span class="wintitle"> 聲明的ID </span> 從 <code> setVisitorID </code> 函式 <span class="keyword"> Adobe Experience Platform身份服務 </span> 然後傳到 <span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager嘗試將客戶端和訪問者ID與系統中的相應ID匹配。 如果不存在匹配的ID,Audience Manager會建立新ID，並將其與客戶端和訪問者ID關聯。 </p> <p> <p>注：如果ID映射到多個Audience ManagerID，則使用最新映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager將其同步的ID寫入客戶端域或應用程式中的第一方cookie（或其他可定址儲存空間）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件調用</b> </td>
   <td colname="col2"> <p>其他事件調用從客戶端的域讀取Audience ManagerID並將其發送到Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

要開始，您需要配置 [!DNL Experience Cloud] ID服務和 [!UICONTROL DIL] 的頁面。 請參閱 [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create) 和 [聲明的ID變數](../features/declared-ids.md#declared-id-variables)。

## 選擇退出呼叫 {#opt-out-calls}

的 [!UICONTROL declared ID] 流程授予站點訪問者首選項以選擇退出 [!DNL Audience Manager] 以你的網站為目標。 當 [!DNL Audience Manager] 收到退出請求， [!DNL JSON] 返回 [!DNL DCS] 包含錯誤代碼171，其中包含消息 `Encountered opt out tag`，而不是 [!DNL Audience Manager] 用戶ID。

* [!DNL Audience Manager] 能通過 [!UICONTROL declared ID] 選擇退出 [!DNL Audience Manager] [!UICONTROL UUID] 的 [!DNL URL]。
* 的 [!UICONTROL declared ID] opt-out儲存在 [!UICONTROL Profile Cache Server] ([!UICONTROL PCS])，按合作夥伴計算。 沒有平台級別的退出選項，使用 [!UICONTROL declared IDs]。 此外， [!DNL Audience Manager] 從邊緣上的特定區域選擇用戶（opt-out不交叉） [!DNL DCS] 區域)。

請參閱 [資料隱私](../overview/data-security-and-privacy/data-privacy.md) 的子菜單。

## [!UICONTROL Declared ID] 退出示例 {#opt-out-examples}

你可以 [!UICONTROL declared ID] 帶有 `d_cid` 和 `d_cid_ic` 鍵值對。 舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

### 選擇退出 [!UICONTROL CID] 和 [!UICONTROL CID_IC]

如需說明和語法，請參閱 [URL 變數和宣告 ID 的語法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用以下項目執行選擇退出 </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者 ID 和使用者 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合程式碼和使用者 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多重 <code> d_cid </code> 和 <code> d_cid_ic </code> 鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 選擇退出 [!UICONTROL DPID]。 [!UICONTROL DPUUID], [!UICONTROL UUID] （不建議使用）

這些方法仍然有效，但被視為已棄用。 此資訊供傳統用途和參考。 舊有選擇退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選擇退出（不建議使用） </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> 必須 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作夥伴級別選擇退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>儲存合作夥伴級別的退出選項，以獲取此項的最新映射 <code> dpid </code> + <code> dpuuid </code> 與UUIDAAM對。 如果以前沒有映射，則Audience Manager會檢查請求是否在Cookie中包含AAMUUID，如果包含，則使用該UUID儲存opt-out。 否則，Audience Manager將生AAM成新的UUID並將opt-out儲存在其下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 明確 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 總是優先。 如果 <code> dpid </code> + <code> dpuuid </code> 組合映射到AAM另一個UUID,opt-out儲存在AAM請求中傳遞的UUID下( <code> d_uuid </code>)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 的變數和語法 [!UICONTROL Declared IDs] {#variables-and-syntax}

下表列出了傳入的鍵值對 [!DNL Audience Manager] 資料提供程式ID和用戶ID或整合代碼（如果使用）。 注意， *斜體* 指示變數佔位符。 已添加空格，以便更容易閱讀。

在每個鍵值對中：

* 的 `=` 符號將鍵與其相關值分開。
* 非打印 [!DNL ASCII] 字元 `%01` 將值分開。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>包含單個鍵值對中的資料提供程式ID和關聯的唯一用戶ID。 <code> d_cid </code> 替換 <code> d_dpid </code> 和 <code> d_dpuuid </code>，它被視為已棄用，但仍受支援。 請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>包含單個鍵值對中的整合代碼和關聯的唯一用戶ID。 <code> d_cid_ic </code> 替換 <code> d_dpid </code> 和 <code> d_dpuuid </code>，已棄用，但仍受支援。 請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件調用 {#sample-event-calls}

給定這些key-value對及其所需的語法，您將進行事件調用，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包括 </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者 ID 和使用者 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合程式碼和使用者 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多重 <code> d_cid </code> 和 <code> d_cid_ic </code> 鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 變數 {#declared-id-variables}

描述用於傳遞的配置變數 [!UICONTROL declared IDs] 通 [!UICONTROL DIL] 至 [!DNL Audience Manager.]

## [!UICONTROL DIL] 使用 [!DNL Adobe Experience Platform Identity Service] 傳遞 [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

與 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)不用再過門了 [!UICONTROL declared IDs] 已棄用 `dpid` 和 `dpuuid` 變數。 相反， [!UICONTROL DIL] 依靠 `visitorService` 函式 [!UICONTROL declared IDs] 從 `setCustomerIDs` 函式 [!UICONTROL Adobe Experience Platform Identity Service]。 有關詳細資訊，請參見 [客戶ID和身份驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。 你會打電話 `visitorService` 在 `DIL.create` 如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在 `namespace` 鍵值對， `MCORG` 你 [!DNL Experience Cloud] 組織ID。 如果您沒有此ID，可以在 [!UICONTROL Administration] 的下界 [!DNL Experience Cloud] 控制項欄。 您需要管理員權限才能查看此儀表板。 請參閱 [管理：核心服務](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html)。

## 已棄用的函式 {#deprecated-functions}

使用 [!UICONTROL DIL] (6.2+)，您不需要使用這些鍵值對來傳遞 [!UICONTROL declared IDs]。 那是因為 [!UICONTROL DIL] 現在依靠 `visitorService` 函式。 此函式將獲取 [!UICONTROL declared IDs] 從 [!UICONTROL Adobe Experience Platform Identity Service]。 但是，我們在此處引用這些變數以用於歷史和傳統目的。 有關如何配置的示例，請參閱下面的代碼 `DIL.create` 去 [!UICONTROL declared ID] 從 [!UICONTROL Visitor ID Service]。
下表介紹了 `declaredId` 對象：

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>由Audience Manager分配的資料夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>資料提供者的使用者唯一 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID]和[!UICONTROL DPUUID]

[!DNL Audience Manager] 比較和匹配組合 `DPID` 和 `DPUUID` 到系統中相應的用戶ID。 如果ID不存在， [!DNL Audience Manager] 建立新用戶ID並將其與 `DPID/DPUUID` 的下界。 一次 [!DNL Audience Manager] 匹配或建立用戶ID( `UUID`)返回 [!DNL JSON] 對 [!DNL cookie] 在客戶端域（第一方） [!DNL cookie])或其他本地儲存。

使用 [!UICONTROL DIL] v6.1或更低版本。 但是，此函式已被棄用，取而代之的是 [!UICONTROL declared IDs] 從 [!DNL Adobe Experience Platform Identity Service]。

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>您需要以寫程式方式開發提供ID值的代碼 `d_dpuuid` 和 `d_dpid` 按鈕。

### 在以後傳入ID [!UICONTROL DIL] 實例化

>[!NOTE]
>
>如果你 [!DNL API] 用不同的 `declaredID` 組合，新組合將僅用於該呼叫。 更多常規事件調用將使用 `DIL.create`  `declaredID` 的下界。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求/響應示例 {#request-response-examples}

該請求將資料提供程式和用戶ID發送到 [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

響應返回Audience ManagerID(例如， `UUID`)，寫入到頁面域的第一方cookie中。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不瞄準和選擇退出呼叫 {#do-not-target}

的 [!UICONTROL declared ID] 流程授予站點訪問者首選項以選擇退出 [!DNL Audience Manager] 以你的網站為目標。 當 [!DNL Audience Manager] 收到退出請求， [!DNL DCS] 返回空 [!DNL JSON] 對象而不是 [!DNL Audience Manager] 用戶ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 及 DPUUID](../reference/cid.md)

