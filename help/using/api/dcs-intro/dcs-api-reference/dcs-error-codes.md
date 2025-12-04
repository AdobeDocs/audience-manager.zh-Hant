---
description: 資料收集伺服器(DCS)產生的錯誤代碼和訊息，會依代碼ID以數字順序列出。
title: DCS錯誤碼、訊息和範例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: f8ba09b674b71045e08f6d171471cdcdd0efb265
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 3%

---

# DCS錯誤碼、訊息和範例 {#dcs-error-codes-messages-and-examples}

[!UICONTROL Data Collection Servers] ([!DNL DCS])產生的錯誤碼和訊息，依代碼識別碼以數值順序列出。

在下清單格中，*斜體*&#x200B;代表變數預留位置。

## 系統錯誤碼 {#system-error-codes}

| 錯誤碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 0 | 未指定的錯誤 | 這是一個全包錯誤，會處理其他錯誤處理常式未涵蓋的事件。 疑難排解此錯誤相當困難。 這可能是由於各種未知的動作或事件所造成。 如果您收到此錯誤，請重試您的[!DNL DCS]要求。 如果問題仍然存在，請聯絡您的[!DNL Adobe]代表。 |
| 1 | 找不到主機名稱的設定： `hostname` | 我們的合作夥伴布建團隊尚未設定請求中傳送的主機名稱。 如果您看到此錯誤訊息，請聯絡您的[!DNL Adobe]代表。 |
| 2 | 無效的`d_orgid`值（找不到此組織ID的設定）： `ID` | 組織ID不正確。 請檢查您的ID，然後再次嘗試請求。 如果您不知道或沒有您的組織ID，請參閱「管理頁面」一節[組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)，以瞭解如何找到它。 |
| 10 | 無法評估特徵 | 要求的特徵已經過部分評估或完全沒有評估。 如果問題仍然存在，請聯絡您的[!DNL Adobe]代表。 |

## 整合錯誤代碼 {#integration-error-codes}

| 錯誤碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 100 | 無法擷取要求的主機名稱 | [!DNL API]呼叫未在要求中傳送主機[!DNL HTTP]標頭。 請將主機標頭新增至呼叫，然後再試一次。 大部分的瀏覽器和[!DNL API]使用者端會自動執行此動作。 |
| 101 | 在[!DNL Experience Cloud]中傳遞的`ID` ID無效 | [!DNL DCS]呼叫包含無效的[!DNL Experience Cloud] ID。 檢查標頭字串中的`d_mid=`機碼值組。 請確定您傳入了正確的[!DNL Experience Cloud] ID，然後再次嘗試該請求。 |
| 102 | 傳入要求[!DNL AAM ID]的`ID`無效 | [!DNL DCS]呼叫包含無效的[!DNL Audience Manager] ID。 檢查標頭字串中的`d_uuid=`機碼值組。 請確定您傳入了正確的[!DNL Audience Manager] ID，然後再次嘗試該請求。 |
| 104 | 所有客戶ID無效 | 您呼叫中的所有客戶ID無效。 請檢查您的ID，然後再試一次。 |
| 109 | 不允許協力廠商`HTTP referer`使用反向連結`Partner ID` | 呼叫中的合作夥伴ID不允許呼叫中的`HTTP referer`標頭。 檢查`HTTP referer`標頭是否正確。 |
| 111 | 收到無效的`IMS`權杖 | 已傳回[!DNL Audience Manager] - [!DNL Adobe Target]整合。 呼叫[!DNL DCS]時擲回錯誤，其中包含無效的[!DNL IMS]權杖。 權杖可能格式錯誤、已過期或使用者可能無權存取所需的資源。 |

## 選擇退出錯誤碼 {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代碼ID </th> 
   <th colname="col2" class="entry"> 訊息 </th> 
   <th colname="col3" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>發生ID <code><i>ID</i></code>的選擇退出標籤 </p> </td> 
   <td colname="col3"> <p>客戶已選擇退出接收以興趣為基礎的廣告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>封鎖的Cookie </p> </td> 
   <td colname="col3"> <p>當使用者的瀏覽器封鎖第三方Cookie時傳回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>透過<a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a>發現信任關係 </p> </td> 
   <td colname="col3"> <p>使用者已透過NAI啟動選擇退出程式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作夥伴封鎖來自此國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP位址，<span class="wintitle"> DCS</span>會封鎖來自合作夥伴刻意限制流量的國家/地區的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允許來自這個國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP位址，<span class="wintitle">個DCS</span>會封鎖來自下列國家/地區的要求： </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴(CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗 </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">北韓(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">蘇丹(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">敘利亞(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定檔擷取錯誤代碼 {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代碼ID </th> 
   <th colname="col2" class="entry"> 訊息 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> 無法從設定檔快取讀取ID為<code><i>ID</i></code>的特徵 </p> </td> 
   <td colname="col3"> <p>當無法從我們的內部儲存裝置讀取使用者設定檔時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 無法從設定檔快取中讀取客戶ID的裝置ID： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法擷取設定檔連結合併規則的<a href="../../../reference/ids-in-aam.md">裝置識別碼</a>時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>無法讀取裝置ID的相關客戶： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法從我們的內部儲存區為上次驗證的合併規則擷取與裝置ID相關聯的<a href="../../../reference/ids-in-aam.md">客戶識別碼(UUID)</a>時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 無法讀取識別碼： <code><i>ID</i></code>的裝置叢集 </p> </td> 
   <td colname="col3"> <p>無法針對此裝置ID傳回來自相同裝置圖表叢集的連結裝置ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>無法執行移轉，因為主要裝置的設定檔讀取失敗 </p> </td> 
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料存放區（<span class="wintitle">部PC</span>）可能會發生擴充性問題。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>無法從<code><i>ID</i></code>執行移轉至<code><i>ID</i></code>，因為<code><i>ID</i></code>的設定檔讀取失敗 </p> </td>
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料存放區（<span class="wintitle">部PC</span>）可能會發生擴充性問題。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 整合警告代碼 {#integration-warning-codes}

| 代碼ID | 訊息 | 說明 |
| --- | --- | --- |
| 300 | 無效的客戶ID `_ID_` | 客戶ID無效（缺少資料來源的值、缺少整合代碼、資料來源的格式無效、已封鎖客戶ID、空白客戶ID、未獲授權存取不屬於合作夥伴的資料來源）。 |
| 301 | 已超出最大客戶ID數。 允許的最大值為`_maximum allowed_`。 找到的是`_maximum found_`。 | 與跨裝置資料來源相關聯的客戶ID數量超過每個請求允許的跨裝置ID數量。 這些ID包含跨裝置、行動或Cookie ID。 限制目前設為10。 |
| 302 | 未獲授權的客戶ID `_ID_` | 當客戶ID資料來源並非目前組織ID所擁有時傳回。 如果您不知道或沒有組織ID，請參閱[組織和帳戶連結](https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html)中的「尋找組織ID」一節，瞭解如何尋找它。 |
| 303 | 封鎖的客戶ID `_ID_` | 當客戶ID被識別為惡意且已新增至封鎖清單時傳回。 |
| 304 | 封鎖的資料來源識別碼`_ID_` | 當資料來源ID被識別為惡意且已新增至封鎖清單時傳回 |
| 306 | 封鎖的宣告裝置識別碼`_ID_` | 裝置ID已識別為惡意，且已新增至封鎖清單。當我們收到極大量包含此裝置ID的DCS請求時，可能會在短時間內發生這種情況。 |
| 307 | 已封鎖`_ID_`的設定檔作業 | 已封鎖讀取/寫入動作，因為ID已被識別為惡意並已新增至封鎖清單請參閱錯誤碼306。 |
| 309 | 已捨棄客戶ID `_ID_`，因為它超過每個請求宣告的客戶ID限制 | 與錯誤301相關。 此錯誤會指定因為超過限制而捨棄哪個客戶ID。<br><br>例如，如果在DCS呼叫上宣告12個客戶ID，將會捨棄其中兩個。 為了轉送哪些客戶已捨棄，此錯誤會在回應中出現兩次（每個捨棄的客戶ID顯示一次）。 |
| 310 | 已捨棄客戶ID，因為它超過指定名稱空間的限制。 名稱空間ID為`_ID_`，客戶ID為`_ID_`。 | 如果DCS呼叫上的相同名稱空間( `DPID`)宣告3個以上的客戶ID，則會傳回此錯誤碼。<br><br>`https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one`<br><br>在此範例DCS請求中，有4個識別碼為同一個名稱空間宣告（整合程式碼為1）。 其中一個ID會遭捨棄，並傳回錯誤310。 |
| 311 | 請求包含無效的引數 | 若至少有一個URL引數未正確編碼，DCS會傳回此錯誤碼。 在此情況下，DCS會忽略整個請求。<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%esid!&d_creative=%ecid!&d_adgroup=%eaid!&d_placement=%epid!&d_campaign=%ebuy!&d_adsrc=48123`<br><br>在上述範例要求中，`%`順序編碼不正確。 因此，DCS將會忽略它。<br><br>正確編碼的範例應該如下所示：<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%25esid!&d_creative=%25ecid!&d_adgroup=%25eaid!&d_placement=%25epid!&d_campaign=%25ebuy!&d_adsrc=48123` |
| 312 | 請求包含無效的全域裝置識別碼 | 當請求包含無效的全域裝置ID時，DCS會傳回此錯誤碼。 DCS會忽略無效ID並擲回312錯誤以及無效ID的特定錯誤。 如需正確裝置廣告ID格式與對應之全域資料來源的詳細資訊，請參閱Audience Manager[中的](../../../features/global-data-sources.md)全域資料來源[與](../../../reference/ids-in-aam.md)ID索引。<br><br>不正確呼叫的範例： `"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"`<br><br>說明： IDFA (DPID 20915)必須是大寫的ID。 請求中提供的ID為小寫。 |
| 313 | CMP ID不存在於GCL中 | 當`gdpr=1`和IAB TC字串是由評估時Audience Manager快取版本的全域CMP清單中不存在的CMP ID產生時，適用於IAB TCF的Audience Manager外掛程式會捨棄IAB TC字串，並照常處理請求。 IAB TCF v2.2 ${GDPR}巨集設為0，而${GDPR\_CONSENT\_XXX}巨集為空白。 |
| 314 | CMP ID在GCL中標籤為已刪除 | 當`gdpr=1`和IAB TC字串是由在我們快取版本的「全域CMP清單」中標籤為已刪除的CMP產生時，如果評估時間超過從「全域CMP清單」刪除的時間，適用於IAB TCF的Audience Manager外掛程式會捨棄TC字串並照常處理請求。 IAB TCF v2.2 ${GDPR}巨集設為0，而${GDPR\_CONSENT\_XXX}巨集為空白。 |
| 315 | 同意字串表示不同意 | 若未提供同意，適用於IAB TCF的Audience Manager外掛程式會選擇讓使用者退出進一步的資料收集，或是在未偵測到合作夥伴內容時完全捨棄呼叫。 |

## 錯誤碼訊息範例 {#sample-error-codes}

[!DNL DCS]會在[!DNL JSON]物件或HTTP回應字串的X標頭中傳回錯誤碼和訊息。

### DCS錯誤碼和訊息範例

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X錯誤

X標頭擷取的錯誤碼會顯示在URL字串中，如下所示： `X-Error: 101,102`。

[競爭條件與錯誤處理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
