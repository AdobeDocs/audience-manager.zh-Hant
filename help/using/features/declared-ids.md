---
description: 宣告的ID如何運作、設定程序、程式碼範例和變數。
keywords: id同步
seo-description: 宣告的ID如何運作、設定程序、程式碼範例和變數。
seo-title: 宣告的ID
solution: Audience Manager
title: 宣告的ID
uuid: 49bb4f7e-b4 a7-4d87-a29 c-c3 dca036 d
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

宣告的ID如何運作、設定程序、程式碼範例和變數。

## 宣告的 ID 定位 {#declared-id-targeting}

從未使用或接受永久儲存機制(例如第三方Cookie)的裝置或瀏覽器，交換使用者ID並同步使用者ID。

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

有些瀏覽器和大部分的行動裝置不接受第三方Cookie。這會很難保留網站訪客的相關資訊，或指派永久性ID。To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. 下表說明ID定位/比對程序：

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
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> 會從 <span class="wintitle"> Experience </span> Cloud ID服務提供 <code> 的setVisitorID </code> 函數 <span class="keyword"> 中取得宣告的ID， </span> 並將它傳遞 <span class="keyword"> 至Audience Manager </span>。 </p> </td> 
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

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

[!UICONTROL declared ID] 此程序會讓網站訪客偏好設定在您的網站中選擇退出Audience Manager鎖定。When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* [!UICONTROL declared ID] 選擇退出會儲存在[！UICOHTROL Profile Cache Serveîr([!UICONTROL PCS])，依合作夥伴的規定排列。There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. 請參閱 [CID 取代 DPID 及 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 使用CID和CID_ IC選擇退出

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid=使用者ID&amp; d_ dpid=資料供應商ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. 如果先前沒有對應，Audience Manager會檢查該請求是否包含Cookie中的AAM UUID，如果有的話，請使用該Cookie來儲存選擇退出。否則，Audience Manager會產生新的AAM UUID，並將選擇退出項目儲存在其中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> 和明確 <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>使用者ID&amp; d_ dpuuid=資料提供者的使用者ID&amp;<i>d_ dpid=資料供應商ID</i></code> </p> <p> <code> d_ uuid </code> 一律優先。If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. 已新增空格，讓這些空間更容易閱讀。

在每個索引鍵值配對中：

* `=` 符號會將索引鍵與其相關值分開。
* The non-printing [!DNL ASCII] character `%01` separates the values.

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

## Sample Event Calls {#sample-event-calls}

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名稱</i>/事件？d_ cid=123%01987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [CID取代DPID和DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 在索引鍵值配對中， `MCORG` 是 [!DNL Experience Cloud] 您的組織ID。If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 您需要管理員權限才能檢視此控制面板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don't need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That's because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. 不過，我們會在此處參照這些變數，以滿足歷史和舊有用途。See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

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

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client's domain (first-party cookie) or other local storage.

Call this function when you're using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create({
合作夥伴：「合作夥伴名稱」，
宣告ID：{
dpuuid： <i>dpuuid</i>，
DPID： <i>dpid</i> 
}
})；</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### 在DIL試用後傳遞ID

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getDil('partner name'). api. domigns({…}).陳述式({…})
dpuuid：<i>dpuuid</i> 
dpid：<i>dpid</i> }). 
mit()；</code>
</pre>

## Request/Response Examples {#request-response-examples}

請求會傳送資料提供者和使用者ID給Audience Manager：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

[!UICONTROL declared ID] 此程序會讓網站訪客偏好設定在您的網站中選擇退出Audience Manager鎖定。When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.