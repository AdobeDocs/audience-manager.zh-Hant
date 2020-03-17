---
description: 宣告的ID如何運作、設定程式、程式碼範例和變數。
keywords: id sync
seo-description: 宣告的ID如何運作、設定程式、程式碼範例和變數。
seo-title: 宣告的ID
solution: Audience Manager
title: 宣告的ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 宣告的ID {#declared-ids}

宣告的ID如何運作、設定程式、程式碼範例和變數。

## 宣告的 ID 定位 {#declared-id-targeting}

從不使用或接受永久儲存機制（例如協力廠商Cookie）的裝置或瀏覽器，將使用者ID與Audience Manager交換及同步化。

<!-- declared_id_about.xml -->

## 宣告ID定位的目的 {#declared-id-targeting-purpose}

某些瀏覽器和大部分行動裝置不接受協力廠商Cookie。 因此，很難保留網站訪客的相關資訊或指派永久性ID。 若要解決此問題，Audience Manager會 [!UICONTROL DIL] 讓您在事件呼叫 [!UICONTROL declared IDs] 時傳入。 此外， [!UICONTROL declared ID] 您也可以使用通用ID，在中的所有解決方案中套用至相同的使用者 [!DNL Experience Cloud]。 下表說明ID定位／符合程式：

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
   <td colname="col2"> <p>若要運作，您需 <span class="wintitle"> 要DIL </span> 和 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> 頁面上的Adobe Experience Platform Identity Service </a> 程式碼。 <span class="wintitle"> DIL從 </span><span class="wintitle"> Adobe Experience Platform Identity Service提供的函式取得宣告的ID </span> ，並將 <code> setVisitorID </code> 其傳遞至 <span class="keyword"></span><span class="keyword"></span>Audience Manager。 </p> </td> 
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

若要開始，您必須設定 [!DNL Experience Cloud] ID服務 [!UICONTROL DIL] ，以及您網站上要用於資料收集的頁面。 請參 [閱DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID變數](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫 {#opt-out-calls}

此程 [!UICONTROL declared ID] 序會接受網站訪客的偏好設定，以選擇退出Audience Manager並依您的網站進行定位。 當Audience Manager收到退出請求時， [!DNL JSON] 由傳回的 [!UICONTROL DCS] 錯誤碼會包含171，並顯示訊息「Encounted opt out tag」，而非Audience Manager使用者ID。

* Audience Manager可以在 [!UICONTROL declared ID] 的Audience Manager中同時傳入選擇退 [!UICONTROL UUID] 出選項 [!DNL URL]。
* 退 [!UICONTROL declared ID] 出選項按合作夥伴儲存在[!UICONTROL配置式快取服務[!UICONTROL PCS]器()中。 沒有使用平台層級的退出選項 [!UICONTROL declared IDs]。 此外，Audience Manager會從邊緣的特定區域選擇使用者退出(退出不會跨越區 [!UICONTROL DCS] 域)。

如需 [退出資料收集的詳細資訊](../overview/data-security-and-privacy/data-privacy.md) ，請參閱資料隱私權。

## 宣告的ID選擇退出範例 {#opt-out-examples}

您可以使 [!UICONTROL declared ID] 用和金鑰值配對 `d_cid` 提出 `d_cid_ic` 選擇退出請求。 舊有參數(例如 `d_dpid` 和) `d_dpuuid` 仍然有效，但被視為已過時。 請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 使用CID和CID_IC退出

如需說明和語法，請參 [閱URL變數和Declared ID的語法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選擇退出使用 </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者ID和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合程式碼和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_cid </code> 對 <code> d_cid_ic </code> 和鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用DPID、DPUUID和UUID的退出選項（已過時）

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>會儲存合作夥伴層級選擇退出，以便將此 <code> dpid </code> +對對最 <code> dpuuid </code> 新對應至AAM UUID。 如果先前沒有現有的對應，Audience Manager會檢查請求中是否包含AAM UUID，如果包含，則會使用該AAM UUID儲存選擇退出。 否則，Audience Manager會產生新的AAM UUID，並將選擇退出儲存在其下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> +明確 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 永遠優先。 如果 <code> dpid </code> + <code> dpuuid </code> 組合對應至另一個AAM UUID，則退出會儲存在傳入請求( <code> d_uuid </code>)的AAM UUID下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID的變數和語法 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

下表列出傳入資料提供者ID和使用者ID或整合 [!DNL Audience Manager] 代碼（如果使用）的金鑰值配對。 Note, *italics* indicates a variable placeholder. 已新增空格，讓這些字元更容易閱讀。

在每個鍵值對中：

* 符號 `=` 會將索引鍵與其相關值分開。
* 非列印字 [!DNL ASCII] 元 `%01` 會分隔值。

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
   <td colname="col2"> <p>在單一索引鍵值對中包含資料提供者ID和相關聯的唯一使用者ID。 <code> d_cid </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>，這些被視為已過時但仍受支援。 請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在單一金鑰值配對中包含整合程式碼和相關聯的唯一使用者ID。 <code> d_cid_ic </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>（已過時但仍受支援）。 請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例事件呼叫 {#sample-event-calls}

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
   <td colname="col1"> <p>資料提供者ID和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合程式碼和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_cid </code> 對 <code> d_cid_ic </code> 和鍵值對。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 宣告的ID變數 {#declared-id-variables}

說明將宣告的ID傳遞至的組態變 [!UICONTROL DIL] 數 [!DNL Audience Manager.]

## DIL使用Adobe Experience Platform Identity Service傳遞宣告的ID {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

當與 [Adobe Experience Platform Identity Service搭配使用時](https://marketing.adobe.com/resources/help/en_US/mcvid/)，您不再需要與已過時的 [!UICONTROL declared IDs] 和變數一起 `dpid` 傳入 `dpuuid` 。 相反，當前版本的 [!UICONTROL DIL] 依賴函 `visitorService` 數從中 [!UICONTROL declared IDs] 的函 `setCustomerIDs` 數中獲取 [!UICONTROL Adobe Experience Platform Identity Service]。 For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 如下所示， `visitorService` 您可 `DIL.create` 以呼叫。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在鍵 `namespace` 值配對中，是 `MCORG` 您的 [!DNL Experience Cloud] 組織ID。 如果您沒有此ID，您可以在控制面板的區 [!UICONTROL Administration] 段中找 [!DNL Experience Cloud] 到。 您需要管理員權限才能檢視此控制面板。 See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 已過時的函式 {#deprecated-functions}

有了最新版 [!UICONTROL DIL] 本(6.2+)，您就不需要使用這些金鑰值配對來傳入 [!UICONTROL declared IDs]。 這是因為現 [!UICONTROL DIL] 在需要仰賴上述 `visitorService` 程式碼範例中顯示的函式。 此函式 [!UICONTROL declared IDs] 來自 [!UICONTROL Adobe Experience Platform Identity Service]。 不過，我們會在這裡參照這些變數，以用於歷史和舊有用途。 請參閱下面的程式碼，以取得如何設 `DIL.create` 定從取得 [!UICONTROL declared ID] 的範例 [!UICONTROL Visitor ID Service]。
下表說明物件使用的舊版變 `declaredId` 數：

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

### `DPID`和`DPUUID`

Audience Manager會比較並比對合併後的 `DPID` 和 `DPUUID` 我們系統中的對應使用者ID。 如果ID不存在，Audience Manager會建立新的使用者ID並將其同步至組 `DPID/DPUUID` 合。 一旦Audience Manager符合或建立使用者ID( `UUID`)，就會在回應用戶端網域（第一方Cookie）或其他本機儲存 [!DNL JSON] 中的Cookie時傳回該ID。

當您使用v6.1或更舊版本時， [!UICONTROL DIL] 請呼叫此函式。 不過，此函式已過時，而改用從中取得的新 [!UICONTROL declared IDs] 版本 [!UICONTROL Adobe Experience Platform Identity Service]。

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
>請注意，您需要以程式設計方式開發提供和索引鍵ID值 `d_dpuuid` 的程 `d_dpid` 式碼。

### 在DIL實例化後傳入ID

>[!NOTE]
>
>如果您使用不 [!DNL API] 同的組合進行呼 `declaredID` 叫，新組合將僅用於該呼叫。 進一步的一般事件呼叫會使用原始 `DIL.create` 組 `declaredID` 合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求／回應範例 {#request-response-examples}

請求會傳送資料提供者和使用者ID至Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回寫入至頁面網域中第一方Cookie的 `UUID`Audience Manager ID（例如）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不定位和選擇退出呼叫 {#do-not-target}

此程 [!UICONTROL declared ID] 序會接受網站訪客的偏好設定，以選擇退出Audience Manager並依您的網站進行定位。 當Audience Manager收到退出請求時，會傳回 [!UICONTROL DCS] 空白物 [!DNL JSON] 件，而非Audience Manager使用者ID。

>[!MORELIKETHIS]
>
>* [CID取代DPID和DPUUID](../reference/cid.md)

