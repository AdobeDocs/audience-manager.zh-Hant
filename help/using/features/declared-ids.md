---
description: 宣告的ID如何運作、設定程序、程式碼範例和變數。
keywords: id同步
seo-description: 宣告的ID如何運作、設定程序、程式碼範例和變數。
seo-title: 宣告的ID
solution: Audience Manager
title: 宣告的ID
uuid: 49bb4f7e-b4 a7-4d87-a29 c-c3 dca036 d
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 宣告的ID {#declared-ids}

宣告的ID如何運作、設定程序、程式碼範例和變數。

## 宣告的 ID 定位 {#declared-id-targeting}

從未使用或接受永久儲存機制(例如第三方Cookie)的裝置或瀏覽器，交換使用者ID並同步使用者ID。

<!-- declared_id_about.xml -->

## 宣告ID定位的目的 {#declared-id-targeting-purpose}

有些瀏覽器和大部分的行動裝置不接受第三方Cookie。這會很難保留網站訪客的相關資訊，或指派永久性ID。若要解決此問題，Audience Manager會使用 [!UICONTROL DIL] 讓您傳入 [!UICONTROL declared IDs] 事件呼叫。此外，A也 [!UICONTROL declared ID] 可以作為通用ID，適用於所有解決方案中所有解決方案的相同使用者 [!DNL Experience Cloud]。下表說明ID定位/比對程序：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程序 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>活動呼叫</b> </td> 
   <td colname="col2"> <p>若要運作，您需要 <span class="wintitle"> 頁面上的DIL </span> 和 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID服務 </a> 程式碼。<span class="wintitle"> DIL </span> 會從 <span class="wintitle"> Experience </span> Cloud ID服務提供 <code> 的setVisitorID </code> 函數 <span class="keyword"> 中取得宣告的ID， </span> 並將它傳遞 <span class="keyword"> 至Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>符合ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會嘗試將用戶端和訪客ID與我們系統中的對應ID搭配使用。如果不存在相符的ID，Audience Manager會建立新ID並將其與用戶端和訪客ID關聯。 </p> <p> <p>注意：如果您的ID對應到多個Audience Manager ID，則會使用最新的對應。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會將其同步ID寫入用戶端網域或應用程式中的第一方Cookie(或其他可定址儲存空間)。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件呼叫</b> </td>
   <td colname="col2"> <p>其他事件呼叫會讀取用戶端網域中的Audience Manager ID，並將其傳送至Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要開始，您需要設定 [!DNL Experience Cloud] ID服務和 [!UICONTROL DIL] 您要用於資料收集的網站上的頁面。請參閱 [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create) 和 [宣告ID變數](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫 {#opt-out-calls}

[!UICONTROL declared ID] 此程序會讓網站訪客偏好設定在您的網站中選擇退出Audience Manager鎖定。Audience [!DNL JSON] Manager收到選擇退出要求時， [!UICONTROL DCS] 包含錯誤代碼171的傳回，訊息「已發生退出標籤」，而非Audience Manager使用者ID。

* Audience Manager可與Audience [!UICONTROL declared ID] Manager [!UICONTROL UUID] 一起傳遞選擇退出 [!DNL URL]。
* [!UICONTROL declared ID] 選擇退出會儲存在[！UICOHTROL Profile Cache Server([!UICONTROL PCS])()。沒有平台層級的選擇退出 [!UICONTROL declared IDs]。此外，Audience Manager會將使用者從邊緣的特定區域退出(選擇退出並不會跨 [!UICONTROL DCS] 地區)。

如需退出資料收集的詳細資訊，請參閱 [資料隱私權](../overview/data-security-and-privacy/data-privacy.md) 。

## 宣告的ID選擇退出範例 {#opt-out-examples}

您可以使用與索引鍵值配對進行 [!UICONTROL declared ID]`d_cid``d_cid_ic` 選擇退出請求。舊式參數如 `d_dpid` 但 `d_dpuuid` 仍在運作中，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 使用CID和CID_ IC選擇退出

如需說明和語法，請參閱 [「宣告ID的URL變數和語法](../features/declared-ids.md#variables-and-syntax)」。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出使用 </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者ID和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/demoptout.jpg？d_ cid=123%01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合代碼和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/除錯？d_ cid_ ic=45601321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_ cid </code> 和 <code> d_ cid_ ic </code> key-value配對。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/除錯？d_ cid=123%01987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用DPID、DPUUID和UUID選擇退出(已停用)

這些方法仍可運作，但仍視為停用。此項資訊提供給舊有用途及參考。舊版退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出(已過時) </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> 僅限d_ uuid </p> </td> 
   <td colname="col2"> <p> <code> SocialID <i></i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作夥伴層級選擇退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid=使用者ID&amp; d_ dpid=資料供應商ID </code> </p> <p>會儲存合作夥伴層級選擇退出，以便將此 <code> dpid </code> + <code> dpuuid </code> 配對的最新對應映射至AAM UUID。如果先前沒有對應，Audience Manager會檢查該請求是否包含Cookie中的AAM UUID，如果有的話，請使用該Cookie來儲存選擇退出。否則，Audience Manager會產生新的AAM UUID，並將選擇退出項目儲存在其中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> 和明確 <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>使用者ID&amp; d_ dpuuid=資料提供者的使用者ID&amp;<i>d_ dpid=資料供應商ID</i></code> </p> <p> <code> d_ uuid </code> 一律優先。如果 <code> dpid </code> + <code> dpuuid </code> 組合對應到另一個AAM UUID，選擇退出會儲存在請求中傳遞的AAM UUID下方( <code> d_ uuid </code>)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 宣告ID的變數和語法 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

下表列出在您的 [!DNL Audience Manager] 資料供應商ID和使用者ID或整合代碼中傳遞的索引鍵值配對。Note, *italics* indicates a variable placeholder. 已新增空格，讓這些空間更容易閱讀。

在每個索引鍵值配對中：

* `=` 符號會將索引鍵與其相關值分開。
* 非列印 [!DNL ASCII] 字元會 `%01` 分隔值。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid=<i>資料供應商ID</i> %01<i>使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>在單一索引鍵值配對中包含資料供應商ID和相關聯的唯一使用者ID。<code> d_ cid </code> 取代 <code> d_ dpid </code> 和 <code> d_ dpuuid </code>，這會被視為已不再提倡，但仍受支援。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic=<i>integration code</i> %01<i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>在單一索引鍵值配對中包含整合代碼和相關聯的唯一使用者ID。<code> d_ cid_ ic </code> 取代 <code> d_ dpid </code> 和 <code> d_ dpuuid </code>，這些取代已過時但仍受支援。請參閱 <a href="../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例事件呼叫 {#sample-event-calls}

鑒於這些索引鍵值配對及其必要語法，您會進行事件呼叫，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包括 </th> 
   <th colname="col2" class="entry"> 程式碼範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者ID和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/事件？d_ cid=123%01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>整合代碼和使用者ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/事件？d_ cid_ ic=45601321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_ cid </code> 和 <code> d_ cid_ ic </code> key-value配對。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/事件？d_ cid=123%01987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [CID取代DPID和DPUUID](../reference/cid.md)


## 宣告的ID變數 {#declared-id-variables}

說明將宣告的ID傳遞至 [!UICONTROL DIL][!DNL Audience Manager.]

## DIL使用Experience Cloud ID服務傳遞宣告的ID {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

與 [Experience Cloud ID服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)搭配使用時，您不再需要 [!UICONTROL declared IDs] 隨已過時 `dpid``dpuuid` 和變數傳入。相反地，目前的版本 [!UICONTROL DIL] 依賴 `visitorService` 函數從函數 [!UICONTROL declared IDs] 中取得 `setCustomerIDs` 函數 [!UICONTROL Experience Cloud ID Service]。For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 您會呼叫 `visitorService` 如下 `DIL.create` 所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 在索引鍵值配對中， `MCORG` 是 [!DNL Experience Cloud] 您的組織ID。如果您沒有此ID，可以在控制面板 [!UICONTROL Administration] 的區段 [!DNL Experience Cloud] 中找到。您需要管理員權限才能檢視此控制面板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 已過時的函數 {#deprecated-functions}

使用最新版本( [!UICONTROL DIL] 6.2+)，您不需要使用這些機碼值組來傳入 [!UICONTROL declared IDs]。這是因為 [!UICONTROL DIL] 現在需仰賴上述程式碼範例中所顯示的 `visitorService` 函數。此函數來自 [!UICONTROL declared IDs][!UICONTROL Experience Cloud ID Service]於。不過，我們會在此處參照這些變數，以滿足歷史和舊有用途。請參閱下面的程式碼，以瞭解如何設定 `DIL.create` 從中取得的 [!UICONTROL declared ID] 範例 [!UICONTROL Visitor ID Service]。
下表說明 `declaredId` 物件使用的舊變數：

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

Audience Manager會比較並比對系統中的相對應 `DPID``DPUUID` 使用者ID和對應的使用者ID。如果ID不存在，Audience Manager會建立新的使用者ID並將其同步至 `DPID/DPUUID` 組合。Audience `UUID`Manager符合或建立使用者ID時，會傳回該ID， [!DNL JSON] 回應客戶網域中的Cookie(第一方Cookie)或其他本機儲存。

當您使用 [!UICONTROL DIL] v6.1或更早版本時，請呼叫此函數。不過，此函數已停用，有利於從中取得 [!UICONTROL declared IDs] 的新版本 [!UICONTROL Experience Cloud ID Service]。

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
>注意，您需要程式設計程式碼來開發提供ID值 `d_dpuuid` 和 `d_dpid` 索引鍵的代碼。

### 在DIL試用後傳遞ID

>[!NOTE]
>
>如果您使用 [!DNL API] 不同 `declaredID` 組合進行呼叫，則只會針對該呼叫使用新組合。其他一般事件呼叫將使用原始 `DIL.create``declaredID` 組合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求/回應範例 {#request-response-examples}

請求會傳送資料提供者和使用者ID給Audience Manager：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回Audience Manager ID(例如 `UUID`，)，此ID會寫入至頁面網域中的第一方Cookie。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不要定位和退出呼叫 {#do-not-target}

[!UICONTROL declared ID] 此程序會讓網站訪客偏好設定在您的網站中選擇退出Audience Manager鎖定。當Audience Manager收到選擇退出要求時，會 [!UICONTROL DCS] 傳回空白 [!DNL JSON] 物件，而非Audience Manager使用者ID。
