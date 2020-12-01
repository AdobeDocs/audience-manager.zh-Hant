---
description: 宣告的ID如何運作、設定程式、程式碼範例和變數。
keywords: id sync
seo-description: 宣告的ID如何運作、設定程式、程式碼範例和變數。
seo-title: 宣告 ID
solution: Audience Manager
title: 宣告 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 10%

---


# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]如何運作、設定程式、程式碼範例和變數。

## [!UICONTROL Declared ID] 定位 {#declared-id-targeting}

從不使用或接受永久儲存機制（例如協力廠商[!DNL cookies]）的裝置或瀏覽器，將使用者ID與[!DNL Audience Manager]交換並同步。

## [!UICONTROL Declared ID]定位{#declared-id-targeting-purpose}的用途

某些瀏覽器和大部分行動裝置不接受協力廠商[!DNL cookies]。 因此，很難保留網站訪客的相關資訊或指派永久性ID。 若要解決此問題，[!DNL Audience Manager]使用[!UICONTROL DIL]讓您在事件呼叫時傳入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]可當成通用ID，適用於[!DNL Experience Cloud]中所有解決方案的相同使用者。 下表說明ID定位／符合程式：

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
   <td colname="col2"> <p>若要運作，您需要頁面上的<span class="wintitle"> DIL </span>和<a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>程式碼。 <span class="wintitle"> DIL從 </span>  <span class="wintitle">  </span>  <code> setVisitorID </code> Adobe Experience Platform Identity Service提供的函 <span class="keyword"> 數取得宣告的ID，並將其傳 </span> 遞至Audience Manager <span class="keyword">  </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>符合ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會嘗試將用戶端和訪客ID與我們系統中的對應ID相符。 如果相符的ID不存在，Audience Manager會建立新的ID，並將其與用戶端和訪客ID關聯。 </p> <p> <p>注意： 如果您的ID對應至多個Audience Manager ID，則會使用最新的對應。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>傳回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會將其同步化ID寫入用戶端網域或應用程式中的第一方Cookie（或其他可定址儲存空間）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件呼叫</b> </td>
   <td colname="col2"> <p>其他事件呼叫會從用戶端網域讀取Audience Manager ID，並將它傳送至Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要開始，您必須在您網站上要用於資料收集的頁面上設定[!DNL Experience Cloud] ID服務和[!UICONTROL DIL]。 請參閱[DIL create](../dil/dil-class-overview/dil-create.md#dil-create)和[Declared ID變數](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫{#opt-out-calls}

[!UICONTROL declared ID]程式會接受網站訪客的偏好設定，以選擇退出您網站的[!DNL Audience Manager]定位。 當[!DNL Audience Manager]收到退出請求時，[!DNL DCS]傳回的[!DNL JSON]包含錯誤碼171，並包含訊息`Encountered opt out tag`，而非[!DNL Audience Manager]使用者ID。

* [!DNL Audience Manager] 可以傳入 [!UICONTROL declared ID] 退出選項旁 [!DNL Audience Manager] [!UICONTROL UUID] 邊的 [!DNL URL]。
* [!UICONTROL declared ID]選擇退出會依每個合作夥伴儲存在[!UICONTROL Profile Cache Server]([!UICONTROL PCS])中。 沒有使用[!UICONTROL declared IDs]的平台層級選擇退出。 此外，[!DNL Audience Manager]會選擇使用者離開邊緣上的特定區域（退出不會跨越[!DNL DCS]區域）。

如需退出資料收集的詳細資訊，請參閱[資料隱私](../overview/data-security-and-privacy/data-privacy.md)。

## [!UICONTROL Declared ID] 退出範例  {#opt-out-examples}

您可以使用`d_cid`和`d_cid_ic`鍵值對發出[!UICONTROL declared ID]選擇退出請求。 舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

### 選擇退出（含[!UICONTROL CID]和[!UICONTROL CID_IC]）

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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 選擇退出（已過時）[!UICONTROL DPID][!UICONTROL DPUUID][!UICONTROL UUID]

這些方法仍然有效，但被視為已過時。 此資訊是供舊版使用及參考之用。 舊版退出包括：

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>會儲存合作夥伴層級選擇退出，以便將此<code> dpid </code> + <code> dpuuid </code>對最新對應至AAM UUID。 如果先前沒有現有的對應，Audience Manager會檢查請求中是否包含AAM UUID，如果包含，則會使用該AAM UUID儲存選擇退出。 否則，Audience Manager會產生新的AAM UUID，並將選擇退出儲存在其下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 和明確  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 永遠優先。如果<code> dpid </code> + <code> dpuuid </code>組合對應至其他AAM UUID，則退出會儲存在傳入請求的AAM UUID(<code> d_uuid </code>)下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs] {#variables-and-syntax}的變數和語法

下表列出傳入[!DNL Audience Manager]資料提供者ID和使用者ID或整合代碼（如果使用）的金鑰值配對。 請注意，*斜體*&#x200B;表示變數預留位置。 已新增空格，讓這些字元更容易閱讀。

在每個鍵值對中：

* `=`符號將鍵與其相關值分隔開。
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
   <td colname="col2"> <p>在單一索引鍵值對中包含資料提供者ID和相關聯的唯一使用者ID。 <code> d_cid </code> 取 <code> d_dpid </code> 代 <code> d_dpuuid </code>和，但仍受支援。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在單一金鑰值配對中包含整合程式碼和相關聯的唯一使用者ID。 <code> d_cid_ic </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>，這些已過時但仍受支援。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件呼叫範例{#sample-event-calls}

若有這些鍵值配對及其必要語法，您會進行下列事件呼叫。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包含 </th> 
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
   <td colname="col1"> <p>多個<code> d_cid </code>和<code> d_cid_ic </code>鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 變數 {#declared-id-variables}

說明用於將[!UICONTROL declared IDs]傳遞至[!UICONTROL DIL]至[!DNL Audience Manager.]的組態變數

## [!UICONTROL DIL] 使用 [!DNL Adobe Experience Platform Identity Service] 來傳遞  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

當與[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)搭配使用時，您不再需要使用已過時的`dpid`和`dpuuid`變數傳入[!UICONTROL declared IDs]。 相反，[!UICONTROL DIL]的當前版本依賴`visitorService`函式從[!UICONTROL Adobe Experience Platform Identity Service]的`setCustomerIDs`函式獲得[!UICONTROL declared IDs]。 如需詳細資訊，請參閱[客戶ID和驗證狀態](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 如下所示，您會呼叫`DIL.create`中的`visitorService`。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`鍵值對中，`MCORG`是您的[!DNL Experience Cloud]組織ID。 如果您沒有此ID，則可在[!DNL Experience Cloud]控制面板的[!UICONTROL Administration]區段中找到它。 您需要管理員權限才能檢視此控制面板。 請參閱[管理：核心服務](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html)。

## 已過時的函式{#deprecated-functions}

在[!UICONTROL DIL](6.2+)的最新版本中，您不需要使用這些鍵值配對來傳入[!UICONTROL declared IDs]。 這是因為[!UICONTROL DIL]現在依賴於上述程式碼範例中顯示的`visitorService`函式。 此函式從[!UICONTROL Adobe Experience Platform Identity Service]獲取[!UICONTROL declared IDs]。 不過，我們會在這裡參照這些變數，以用於歷史和舊有用途。 請參閱以下程式碼，以取得如何從[!UICONTROL Visitor ID Service]設定`DIL.create`以取得[!UICONTROL declared ID]的範例。
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

[!DNL Audience Manager] 比較並比對組合 `DPID` 的 `DPUUID` 使用者ID，以及我們的系統。如果ID不存在，[!DNL Audience Manager]會建立新的使用者ID並將它同步至`DPID/DPUUID`組合。 當[!DNL Audience Manager]符合或建立使用者ID(`UUID`)後，它會在[!DNL JSON]回應中傳回該ID，以回應用戶端網域（第一方[!DNL cookie]）或其他本機儲存。[!DNL cookie]

當您使用[!UICONTROL DIL] v6.1或更舊版本時，請呼叫此函式。 但是，此函式已過時，而改用從[!DNL Adobe Experience Platform Identity Service]取得[!UICONTROL declared IDs]的新版本。

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

### 在[!UICONTROL DIL]實例化後傳入ID

>[!NOTE]
>
>如果您使用不同的`declaredID`組合進行[!DNL API]呼叫，則新組合將僅用於該呼叫。 進一步的常規事件調用將使用原始的`DIL.create` `declaredID`組合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求／回應範例{#request-response-examples}

請求會將資料提供者和使用者ID傳送至[!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回寫入至頁面網域第一方Cookie的Audience Manager ID（例如`UUID`）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不要定位和選擇退出呼叫{#do-not-target}

[!UICONTROL declared ID]程式會接受網站訪客的偏好設定，以選擇退出您網站的[!DNL Audience Manager]定位。 當[!DNL Audience Manager]收到退出請求時，[!DNL DCS]會傳回空的[!DNL JSON]物件，而非[!DNL Audience Manager]使用者ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 及 DPUUID](../reference/cid.md)

