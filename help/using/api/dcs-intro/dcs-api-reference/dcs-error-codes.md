---
description: 資料收集伺服器(DCS)依程式碼ID以數值順序列出產生的錯誤碼和訊息。
seo-description: 資料收集伺服器(DCS)依程式碼ID以數值順序列出產生的錯誤碼和訊息。
seo-title: DCS 錯誤碼、訊息和範例
solution: Audience Manager
title: DCS 錯誤碼、訊息和範例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1509'
ht-degree: 3%

---


# DCS 錯誤碼、訊息和範例 {#dcs-error-codes-messages-and-examples}

由()依程式碼ID以數 [!UICONTROL Data Collection Servers] 值順序列[!DNL DCS]出而產生的錯誤碼和訊息。

In the tables below, *italics* represents a variable placeholder.

## 系統錯誤代碼 {#system-error-codes}

|錯誤代碼|錯誤消息|說明|
|—|—|—|
|0|未指定錯誤|這是一個捕獲全部錯誤，處理其他錯誤處理程式未覆蓋的事件。 疑難排解此錯誤。 它可能是由各種未知的動作或事件所造成。 如果您收到此錯誤，請再試一次 [!DNL DCS] 您的請求。 如果問題 [!DNL Adobe] 仍然存在，請聯絡您的代表。|
|1|找不到主機名的配置： `hostname`|我們的合作夥伴布建團隊尚未設定在請求中傳送的主機名稱。 如果您看 [!DNL Adobe] 到此錯誤訊息，請連絡您的代表。|
|2|無 `d_orgid` 效值（找不到此組織ID的組態）: `ID`|組織ID不正確。 請檢查您的ID，然後再試一次請求。 如果您不知道或沒有組織ID，請參閱「管理頁面」一節的「組織與帳戶連結 [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html) 」，以取得如何尋找的詳細資訊。|

## 整合錯誤碼 {#integration-error-codes}

|錯誤代碼|錯誤消息|說明|
|—|—|—|
|100|無法擷取請求的主機名稱|呼 [!DNL API] 叫未傳送請求中的主 [!DNL HTTP] 機標題。 將主機標題新增至呼叫，然後再試一次。 大部分的瀏覽器 [!DNL API] 和用戶端都會自動執行此動作。 |
|101|傳入的 [!DNL Experience Cloud] ID無效 `ID`|呼叫 [!DNL DCS] 包含無效 [!DNL Experience Cloud] ID。 檢查標 `d_mid=` 題字串中的鍵值對。 請確定您傳入的是正確的 [!DNL Experience Cloud] ID，然後再試一次請求。 |
|102|傳入請 [!DNL AAM ID] 求無效 `ID`|呼叫 [!DNL DCS] 包含無效 [!DNL Audience Manager] ID。 檢查標 `d_uuid=` 題字串中的鍵值對。 請確定您傳入的是正確的 [!DNL Audience Manager] ID，然後再試一次請求。 |
|104|所有客戶ID無效 |您呼叫中的所有客戶ID都無效。 請檢查您的ID，然後再試一次。|
|109|合作伙 `HTTP referer` 伴不允許參考者 `Partner ID`|呼 `HTTP referer` 叫上的夥伴ID不允許標題。 檢查標題 `HTTP referer` 是否正確。|
|111|收到的 `IMS` Token無效|已傳回 [!DNL Audience Manager] - [!DNL Adobe Target] 整合。 當對進行呼叫時，會擲回錯誤，此呼 [!DNL DCS]叫包含無效的代 [!DNL IMS] 號。 Token可能格式錯誤、過期，或者使用者未獲得存取所需資源的授權。|

## 選擇退出錯誤代碼 {#opt-out-error-codes}

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
   <td colname="col2"> <p>遇到ID的退出標籤 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客戶選擇不接收喜好式廣告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>封鎖的Cookie </p> </td> 
   <td colname="col3"> <p>在使用者的瀏覽器封鎖第三方Cookie時傳回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>透過 <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI遇到信任關係</a> </p> </td> 
   <td colname="col3"> <p>用戶已通過NAI啟動退出進程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作夥伴封鎖來自此國家的要求 </p> </td> 
   <td colname="col3"> <p>根據IP位址， <span class="wintitle"> DCS</span> 會封鎖合作夥伴有意限制流量之國家的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允許來自此國家的請求 </p> </td> 
   <td colname="col3"> <p>DCS會根據IP位址封 <span class="wintitle"> 鎖下列國家</span> （地區）的要求： </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴（古巴） </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">朝鮮(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">蘇丹(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">敘利亞(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 描述檔擷取錯誤碼 {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> 無法從ID的描述檔快取讀取特徵： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法從內部儲存區讀取使用者描述檔時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 無法從客戶ID的設定檔快取中讀取裝置ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法針 <a href="../../../reference/ids-in-aam.md"> 對描述檔連結</a> 合併規則擷取裝置ID時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>無法讀取裝置ID的相關客戶： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法從 <a href="../../../reference/ids-in-aam.md"> 內部儲存區擷取「上次驗證」合併規則的裝置ID(UUID)</a> ，則傳回與裝置ID關聯的客戶ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 無法讀取ID的設備群集： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>無法針對此裝置ID傳回來自相同裝置圖形叢集的連結裝置ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>無法執行遷移，因為主設備的配置檔案讀取失敗 </p> </td> 
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料儲存區(PCS<span class="wintitle"></span>)可能會發生延展性問題。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>無法執行從到的遷 <code><i>ID</i></code> 移，因 <code><i>ID</i></code>為配置檔案讀取失敗 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料儲存區(PCS<span class="wintitle"></span>)可能會發生延展性問題。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 整合警告代碼 {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代碼ID </th> 
   <th colname="col2" class="entry"> 訊息 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>無效的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客戶ID無效（缺少資料來源的值、缺少整合代碼、資料來源的格式無效、封鎖的客戶ID、空白客戶ID、未授權存取不屬於合作夥伴的資料來源）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>超出客戶ID的最大數量。 允許的上限 <code><i>maximum allowed</i></code>為。 找到 <code><i>maximum found</i></code>。</p> </td> 
   <td colname="col3"> <p>與跨裝置資料來源相關聯的客戶ID數量超過每個請求允許的跨裝置ID數量。 這些ID包括跨裝置、行動裝置或Cookie ID。 此限制目前設為10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未經授權的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID資料來源不歸目前組織ID所有時傳回。 如果您不知道或沒有組織ID，請參閱「組織與帳戶連結」中的「尋找組織ID」一節 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"></a> ，以取得如何尋找組織ID的詳細資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>封鎖的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID被識別為惡意且已新增至密文清單時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>封鎖的資料來源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當資料來源ID已識別為惡意並已新增至密鑰清單時傳回 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>已阻止已聲明的設備ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>裝置ID已識別為惡意，並已新增至密文清單。當我們在短時間內收到包含此裝置ID的極大量 <span class="wintitle"> DCS</span> 請求時，就會發生此情況。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>封鎖的描述檔操作 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>已封鎖讀／寫動作，因為ID已識別為惡意，並已新增至密碼清單。請參閱錯誤代碼306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客戶ID <code><i>ID</i></code> 已被捨棄，因為它超出每個請求所宣告的客戶ID的限制 </p> </td> 
   <td colname="col3"> <p>與錯誤301相關。 此錯誤會指定因超出限制而捨棄的客戶ID。 </p> <p>例如，如果DCS呼叫上宣告有12個客戶ID <span class="wintitle"></span> ，其中兩個會被捨棄。 為了傳遞被捨棄的客戶ID，回應中會出現兩次此錯誤（每個已棄置的客戶ID會顯示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>客戶ID已捨棄，因為它已超出指定名稱空間的限制。 命名空間ID <code><i>ID</i></code>是，客戶ID是 <code><i>ID</i></code>。 </p> </td> 
   <td colname="col3"> <p>如果在DCS呼叫上針對相同的命名空間(<code> DPID</code>)宣告3個以上的客戶ID，則會傳回 <span class="wintitle"> 此錯誤</span> 碼。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此範例 <span class="wintitle"> DCS請求中</span> ，有4個ID已宣告用於相同的命名空間（整合程式碼為1）。 其中一個ID被捨棄，並傳回錯誤310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>請求包含無效參數 </p> </td> 
   <td colname="col3"> <p>當至少 <span class="wintitle"> 一個URL參數未正確編碼時</span> ,DCS會傳回此錯誤碼。 在這種情況下， <span class="wintitle"> DCS會忽略</span> 整個請求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上述範例請求中，序 <code> %</code> 列編碼不正確。 因此， <span class="wintitle"> DCS</span> 將忽略它。 </p> <p>正確編碼的範例應如下所示： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>請求包含無效的全域裝置ID </p> </td> 
   <td colname="col3"> <p>當請 <span class="wintitle">求包含無效的全域裝置ID時</span> ,DCS會傳回此錯誤碼。 DCS會忽略無效ID，並引發312錯誤以及無效ID的特定錯誤。 如需正確 <a href="../../../features/global-data-sources.md" format="dita" scope="local">裝置廣告ID格式及</a> 對應全域資料來源的詳細資訊，請參閱Audience Manager <a href="../../../reference/ids-in-aam.md" format="dita" scope="local"></a> 中的全域資料來源和ID索引。</p>
   <p>錯誤呼叫的範例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>說明： <span class="keyword">IDFA(DPID 20915)</span> 必須是大寫ID。 請求中提供的ID為小寫。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>GCL中不存在CMP ID</p> </td> 
   <td colname="col3"> <p>當 <code>gdpr=1</code> 且IAB TC字串是由評估時Audience Manager的快取版本全域CMP清單中未顯示的CMP ID產生時，IAB TCF的Audience Manager外掛程式會放棄IAB TC字串並照常處理請求。 IAB TCF v2.0 ${GDPR}巨集設為0，而${GDPR_CONNENCE_XXX}巨集為空。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID在GCL中標籤為已刪除</p> </td> 
   <td colname="col3"> <p>當 <code>gdpr=1</code> 且IAB TC字串是由在我們的全域CMP清單快取版本中標示為已刪除的CMP產生時，Audience Manager Plug-in for IAB TCF會捨棄TC字串並照常處理要求，如果評估時間超過從全域CMP清單刪除的時間。 IAB TCF v2.0 ${GDPR}巨集設為0，而${GDPR_CONNENCE_XXX}巨集為空。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>同意字串表示未同意</p> </td> 
   <td colname="col3"> <p>未提供同意時，IAB TCF的Audience Manager外掛程式會將使用者拒絕進一步的資料收集，或在未偵測到合作夥伴內容時完全放棄呼叫。</p>
   </td>
  </tr>

</tbody>
</table>

## 錯誤代碼消息示例 {#sample-error-codes}

返 [!DNL DCS] 回對象或HTTP響應 [!DNL JSON] 字串中X-標題中的錯誤代碼和消息。

### 範例DCS錯誤碼和訊息

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

由X-標題擷取的錯誤碼會像這樣出現在URL字串中 `X-Error: 101,102`。

[競爭條件與錯誤處理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)