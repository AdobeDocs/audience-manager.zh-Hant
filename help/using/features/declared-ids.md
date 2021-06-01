---
description: 宣告ID如何運作、設定程式、程式碼範例和變數。
keywords: id同步
seo-description: 宣告ID如何運作、設定程式、程式碼範例和變數。
seo-title: 宣告 ID
solution: Audience Manager
title: 宣告 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID同步
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 10%

---

# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]如何運作、設定程式、程式碼範例和變數。

## [!UICONTROL Declared ID] 定位 {#declared-id-targeting}

從不使用或接受永久性儲存機制的裝置或瀏覽器（例如第三方[!DNL cookies]），將使用者ID與[!DNL Audience Manager]交換並同步。

## [!UICONTROL Declared ID]目標定位{#declared-id-targeting-purpose}的用途

某些瀏覽器和大部分行動裝置不接受第三方[!DNL cookies]。 這使得您很難保留網站訪客的相關資訊或指派永久性ID。 若要解決此問題，[!DNL Audience Manager]使用[!UICONTROL DIL]，讓您在事件呼叫時傳入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]也可當作適用於[!DNL Experience Cloud]中所有解決方案的相同使用者的通用ID。 下表說明ID目標定位/比對程式：

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
   <td colname="col2"> <p>若要運作，您需要頁面上的<span class="wintitle">DIL</span>和<a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>程式碼。 <span class="wintitle"> DIL </span> 會從 <span class="wintitle"> Adobe Experience Platform  </span> Identity Service提 <code> setVisitorID </code> 供的函式取得宣告 <span class="keyword"> ID，並 </span> 將其傳遞 <span class="keyword"> 至Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>符合ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會嘗試將用戶端和訪客ID與系統中的對應ID進行比對。 如果相符的ID不存在，Audience Manager會建立新ID，並將其與用戶端和訪客ID建立關聯。 </p> <p> <p>注意： 如果您的ID對應至多個Audience ManagerID，則會使用最新的對應。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>傳回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會將其同步的ID寫入用戶端網域或應用程式中的第一方Cookie（或其他可定址的儲存空間）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件呼叫</b> </td>
   <td colname="col2"> <p>其他事件呼叫會從用戶端的網域讀取Audience ManagerID，並將其傳送至Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要開始，您必須在網站上要用於資料收集的頁面上，設定[!DNL Experience Cloud] ID服務和[!UICONTROL DIL]。 請參閱[DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)和[宣告ID變數](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫{#opt-out-calls}

[!UICONTROL declared ID]程式會依照網站訪客的偏好設定，選擇退出您的網站所定位的[!DNL Audience Manager]。 當[!DNL Audience Manager]收到選擇退出請求時，[!DNL DCS]返回的[!DNL JSON]包含錯誤代碼171，並帶有消息`Encountered opt out tag`，而不是[!DNL Audience Manager]用戶ID。

* [!DNL Audience Manager] 可連同 [!UICONTROL declared ID] 中的傳遞 [!DNL Audience Manager] [!UICONTROL UUID] 退出 [!DNL URL]。
* [!UICONTROL declared ID]選擇退出會依各別合作夥伴儲存在[!UICONTROL Profile Cache Server]([!UICONTROL PCS])中。 沒有使用[!UICONTROL declared IDs]的平台層級選擇退出。 此外， [!DNL Audience Manager]會選擇使用者離開邊緣上的該特定區域（選擇退出不會跨[!DNL DCS]區域）。

請參閱[資料隱私權](../overview/data-security-and-privacy/data-privacy.md) ，以取得有關選擇退出資料收集的詳細資訊。

## [!UICONTROL Declared ID] 退出範例  {#opt-out-examples}

您可以使用`d_cid`和`d_cid_ic`索引鍵值配對，提出[!UICONTROL declared ID]選擇退出請求。 舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>鍵值配對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 選擇退出（包含[!UICONTROL DPID]、[!UICONTROL DPUUID]和[!UICONTROL UUID]）（已廢止）

這些方法仍可運作，但被視為已淘汰。 本資訊僅供舊版使用及參考。 舊版選擇退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出（已過時） </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> 必須 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作夥伴層級選擇退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>系統會儲存合作夥伴層級的選擇退出，以將此<code> dpid </code> + <code> dpuuid </code>配對的最新對應對應至AAM UUID。 如果先前沒有現有對應，Audience Manager會檢查請求中是否包含AAM UUID，如果包含，則會使用該UUID來儲存選擇退出。 否則，Audience Manager會產生新的AAM UUID，並將選擇退出儲存在其下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 和明確  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 一律優先。如果<code> dpid </code> + <code> dpuuid </code>組合對應至另一個AAM UUID，則選擇退出會儲存在傳入要求的AAM UUID下(<code> d_uuid </code>)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs] {#variables-and-syntax}的變數和語法

下表列出傳入[!DNL Audience Manager]資料提供者ID、使用者ID或整合代碼（若有使用）的機碼值組。 注意， *斜體*&#x200B;表示變數預留位置。 已新增空格，讓這些字元更容易閱讀。

在每個機碼值組中：

* `=`符號將鍵與其相關值分開。
* 非打印的[!DNL ASCII]字元`%01`分隔值。

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
   <td colname="col2"> <p>在單一機碼值組中包含資料提供者ID和相關聯的不重複使用者ID。 <code> d_cid </code> 取 <code> d_dpid </code> 代和 <code> d_dpuuid </code>，雖然被視為已過時，但仍受支援。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在單一機碼值組中包含整合程式碼和相關聯的唯一使用者ID。 <code> d_cid_ic </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>（已淘汰，但仍支援）。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件呼叫範例{#sample-event-calls}

有了這些機碼值組及其必要語法，您可以進行事件呼叫，如下所示。

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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>鍵值配對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 變數 {#declared-id-variables}

說明用來傳遞[!UICONTROL declared IDs]至[!UICONTROL DIL]至[!DNL Audience Manager.]的設定變數

## [!UICONTROL DIL] 使用 [!DNL Adobe Experience Platform Identity Service] 來傳遞  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

與[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)搭配使用時，您不再需要使用已棄用的`dpid`和`dpuuid`變數傳入[!UICONTROL declared IDs]。 相反地，當前版本的[!UICONTROL DIL]依賴於`visitorService`函式從[!UICONTROL Adobe Experience Platform Identity Service]中的`setCustomerIDs`函式獲取[!UICONTROL declared IDs]。 如需詳細資訊，請參閱[客戶ID和驗證狀態](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 您可以呼叫`DIL.create`中的`visitorService`，如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`機碼值組中，`MCORG`是您的[!DNL Experience Cloud]組織ID。 如果您沒有此ID，可以在[!DNL Experience Cloud]控制面板的[!UICONTROL Administration]區段中找到。 您需要管理員權限才能檢視此控制面板。 請參閱[管理：核心服務](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html)。

## 已棄用的函式{#deprecated-functions}

若使用最新版本的[!UICONTROL DIL](6.2+)，您不需要使用這些機碼值組來傳遞[!UICONTROL declared IDs]。 這是因為[!UICONTROL DIL]現在仰賴上述程式碼範例中顯示的`visitorService`函式。 此函式從[!UICONTROL Adobe Experience Platform Identity Service]獲取[!UICONTROL declared IDs]。 不過，我們會在這裡參照這些變數，以用於歷史和舊版用途。 如需如何設定`DIL.create`以從[!UICONTROL Visitor ID Service]取得[!UICONTROL declared ID]的範例，請參閱下列程式碼。
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
   <td colname="col3"> <p>依Audience Manager指派的資料合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>資料提供者的使用者唯一 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID]和[!UICONTROL DPUUID]

[!DNL Audience Manager] 會將結合的和 `DPID` 比 `DPUUID` 對到系統中的對應使用者ID。如果ID不存在，[!DNL Audience Manager]會建立新的使用者ID並將其同步至`DPID/DPUUID`組合。 一旦[!DNL Audience Manager]匹配或建立用戶ID(`UUID`)，它就會在[!DNL JSON]響應中返回該ID，以響應客戶端域（第一方[!DNL cookie]）或其他本地儲存。[!DNL cookie]

當您使用[!UICONTROL DIL] v6.1或更舊版本時，請呼叫此函式。 不過，此函式已遭取代，改用從[!DNL Adobe Experience Platform Identity Service]取得[!UICONTROL declared IDs]的新版本。

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
>您需要以程式設計方式開發提供`d_dpuuid`和`d_dpid`鍵ID值的程式碼。

### 在[!UICONTROL DIL]實例化之後傳遞ID

>[!NOTE]
>
>如果您使用不同的`declaredID`組合進行[!DNL API]呼叫，則新組合將僅用於該呼叫。 進一步的一般事件呼叫將使用原始的`DIL.create` `declaredID`組合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求/回應範例{#request-response-examples}

請求會將資料提供者和使用者ID傳送至[!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回寫入至頁面網域中第一方Cookie的Audience ManagerID（例如`UUID`）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 請勿鎖定目標和選擇退出呼叫{#do-not-target}

[!UICONTROL declared ID]程式會依照網站訪客的偏好設定，選擇退出您的網站所定位的[!DNL Audience Manager]。 當[!DNL Audience Manager]收到選擇退出請求時， [!DNL DCS]會傳回空的[!DNL JSON]物件，而非[!DNL Audience Manager]使用者ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 及 DPUUID](../reference/cid.md)

