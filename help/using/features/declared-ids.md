---
description: 宣告ID的運作方式、設定程式、程式碼範例和變數。
keywords: id同步
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: 宣告ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]如何運作、設定程式、程式碼範例和變數。

## [!UICONTROL Declared ID] 定位 {#declared-id-targeting}

從不使用或接受永久儲存機制的裝置或瀏覽器（例如協力廠商[!DNL Audience Manager]），將使用者ID與[!DNL cookies]交換及同步。

## [!UICONTROL Declared ID]目標定位的用途 {#declared-id-targeting-purpose}

某些瀏覽器和大多數行動裝置不接受協力廠商[!DNL cookies]。 這使得保留有關網站訪客的資訊或指派永久ID變得困難。 為解決此問題，[!DNL Audience Manager]使用[!UICONTROL DIL]讓您在事件呼叫中傳入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]可作為通用ID，套用至[!DNL Experience Cloud]中所有解決方案的相同使用者。 下表說明ID目標定位/比對程式：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程序 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>事件呼叫</b> </td> 
   <td colname="col2"> <p>若要使用，您需要在頁面上使用<span class="wintitle"> DIL </span>和<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant" format="https" scope="external"> Adobe Experience Platform Identity Service </a>程式碼。 <span class="wintitle"> DIL </span>從<span class="wintitle"> Adobe Experience Platform Identity Service </span>提供的<code> setVisitorID </code>函式中取得<span class="keyword">個宣告識別碼</span>，並將其傳遞至<span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>符合ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會嘗試將使用者端和訪客ID與系統中的對應ID比對。 如果相符的ID不存在，Audience Manager會建立新的ID，並將其與客戶端和訪客ID建立關聯。 </p> <p> <p>注意：如果您的ID對應至多個Audience Manager ID，則會使用最近一次對應。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>傳回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會將其同步的ID寫入使用者端網域或應用程式中的第一方Cookie （或其他可定址的儲存空間）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件呼叫</b> </td>
   <td colname="col2"> <p>其他事件呼叫會從使用者端的網域讀取Audience Manager ID，並將其傳送至Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要開始使用，您必須在您要用於資料收集的網站頁面上設定[!DNL Experience Cloud] ID服務和[!UICONTROL DIL]。 請參閱[DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)和[宣告ID變數](../features/declared-ids.md#declared-id-variables)。

## 選擇退出呼叫 {#opt-out-calls}

[!UICONTROL declared ID]程式遵循網站訪客偏好設定，以選擇退出您網站的[!DNL Audience Manager]目標定位。 當[!DNL Audience Manager]收到選擇退出要求時，[!DNL JSON]傳回的[!DNL DCS]包含錯誤碼171，且訊息為`Encountered opt out tag`，而非[!DNL Audience Manager]使用者識別碼。

* [!DNL Audience Manager]可以與[!UICONTROL declared ID]中的[!DNL Audience Manager] [!UICONTROL UUID]一起傳入[!DNL URL]選擇退出。
* [!UICONTROL declared ID]選擇退出會依每個合作夥伴儲存在[!UICONTROL Profile Cache Server] ([!UICONTROL PCS])中。 沒有使用[!UICONTROL declared IDs]的平台層級選擇退出。 此外，[!DNL Audience Manager]會選擇讓使用者退出邊緣上的該特定區域（選擇退出不會跨[!DNL DCS]區域）。

如需選擇退出資料收集的詳細資訊，請參閱[資料隱私權](../overview/data-security-and-privacy/data-privacy.md)。

## [!UICONTROL Declared ID]個選擇退出範例 {#opt-out-examples}

您可以使用[!UICONTROL declared ID]和`d_cid`機碼值組發出`d_cid_ic`個選擇退出請求。 舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

### 使用[!UICONTROL CID]和[!UICONTROL CID_IC]選擇退出

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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>機碼值組。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID]、[!UICONTROL DPUUID]和[!UICONTROL UUID]的選擇退出（已棄用）

這些方法仍有效，但被視為已過時。 提供此資訊以供舊版使用和參考。 舊版選擇退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選擇退出（已棄用） </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 僅<code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作夥伴層級選擇退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>針對此<code> dpid </code> + <code> dpuuid </code>配對與AAM UUID的最新對應，儲存合作夥伴層級的選擇退出。 如果之前沒有對應，Audience Manager會檢查請求在Cookie中是否包含AAM UUID，如果包含，會使用該UUID來儲存選擇退出。 否則，Audience Manager會產生新的AAM UUID，並將選擇退出儲存在其下方。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code>和明確的<code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code>一律優先。 如果<code> dpid </code> + <code> dpuuid </code>組合對應至其他AAM UUID，則選擇退出會儲存在請求中傳遞的AAM UUID下( <code> d_uuid </code>)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs]的變數和語法 {#variables-and-syntax}

下表列出傳入您的[!DNL Audience Manager]資料提供者ID和使用者ID或整合程式碼（若已使用）的索引鍵/值組。 請注意，*斜體*&#x200B;表示變數預留位置。 已新增空格，讓這些內容更易於閱讀。

在每個機碼值組中：

* `=`符號將金鑰與其相關值分開。
* 非列印[!DNL ASCII]字元`%01`會分隔值。

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
   <td colname="col2"> <p>在單一索引鍵/值配對中包含資料提供者ID和相關聯的不重複使用者ID。 <code> d_cid </code>取代<code> d_dpid </code>和<code> d_dpuuid </code>，這兩個專案已視為過時，但仍受支援。 請參閱<a href="../reference/cid.md"> CID取代DPID及DPUUID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在單一索引鍵值配對中包含整合代碼和關聯的唯一使用者ID。 <code> d_cid_ic </code>取代<code> d_dpid </code>和<code> d_dpuuid </code>，這兩個專案已棄用，但仍受支援。 請參閱<a href="../reference/cid.md"> CID取代DPID及DPUUID </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例事件呼叫 {#sample-event-calls}

根據這些機碼值組及其必要的語法，您可以進行事件呼叫，如下所示。

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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>機碼值組。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 變數 {#declared-id-variables}

說明用來透過[!UICONTROL declared IDs]傳遞[!UICONTROL DIL]至[!DNL Audience Manager.]的設定變數

## [!UICONTROL DIL]使用[!DNL Adobe Experience Platform Identity Service]傳遞[!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

與[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)搭配使用時，您不再需要以已棄用的[!UICONTROL declared IDs]和`dpid`變數傳入`dpuuid`。 相反地，[!UICONTROL DIL]的目前版本依賴`visitorService`函式從[!UICONTROL declared IDs]中的`setCustomerIDs`函式取得[!UICONTROL Adobe Experience Platform Identity Service]。 如需詳細資訊，請參閱[客戶ID與驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hant)。 您會在`visitorService`中呼叫`DIL.create`，如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`機碼值組中，`MCORG`是您的[!DNL Experience Cloud]組織識別碼。 如果您沒有此ID，可以在[!UICONTROL Administration]儀表板的[!DNL Experience Cloud]區段中找到。 您需要管理員許可權才能檢視此儀表板。 請參閱[開始使用Experience Cloud服務](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/services/getting-started)。

## 已棄用的函式 {#deprecated-functions}

使用最新版[!UICONTROL DIL] (6.2+)時，您不需要使用這些機碼值組來傳入[!UICONTROL declared IDs]。 這是因為[!UICONTROL DIL]現在依賴以上程式碼範例中顯示的`visitorService`函式。 此函式從[!UICONTROL declared IDs]取得[!UICONTROL Adobe Experience Platform Identity Service]。 不過，我們在此處參考這些變數，是為了歷史和舊版用途。 如需如何設定`DIL.create`以從[!UICONTROL declared ID]取得[!UICONTROL Visitor ID Service]的範例，請參閱下列程式碼。
下表說明`declaredId`物件使用的舊版變數：

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
   <td colname="col3"> <p>Audience Manager指派的資料合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>資料提供者的使用者唯一 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID]和[!UICONTROL DPUUID]

[!DNL Audience Manager]比較並比對合併的`DPID`和`DPUUID`與系統中的對應使用者ID。 如果ID不存在，[!DNL Audience Manager]會建立新的使用者ID並將其同步至`DPID/DPUUID`組合。 一旦[!DNL Audience Manager]符合或建立使用者ID (`UUID`)，它就會在使用者端的網域（第一方[!DNL JSON]）或其他本機儲存體中的[!DNL cookie]的[!DNL cookie]回應中傳回該ID。

當您使用[!UICONTROL DIL] v6.1或更舊版本時，請呼叫此函式。 但是，這個函式已過時，改用從[!UICONTROL declared IDs]取得[!DNL Adobe Experience Platform Identity Service]的新版本。

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
>您必須以程式設計方式開發提供`d_dpuuid`和`d_dpid`索引鍵識別碼值的程式碼。

### 在[!UICONTROL DIL]例項化之後傳遞ID

>[!NOTE]
>
>如果您使用不同的[!DNL API]組合進行`declaredID`呼叫，則新組合將僅用於該呼叫。 進一步的定期事件呼叫將使用原始`DIL.create` `declaredID`組合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求/回應範例 {#request-response-examples}

要求會將資料提供者和使用者ID傳送至[!DNL Audience Manager]：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回寫入頁面網域中第一方Cookie的Audience Manager ID （例如`UUID`）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不要鎖定和選擇退出呼叫 {#do-not-target}

[!UICONTROL declared ID]程式遵循網站訪客偏好設定，以選擇退出您網站的[!DNL Audience Manager]目標定位。 當[!DNL Audience Manager]收到選擇退出要求時，[!DNL DCS]會傳回空的[!DNL JSON]物件，而非[!DNL Audience Manager]使用者識別碼。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 及 DPUUID](../reference/cid.md)
