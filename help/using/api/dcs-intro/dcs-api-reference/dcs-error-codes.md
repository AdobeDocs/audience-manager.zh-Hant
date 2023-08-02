---
description: 資料收集伺服器(DCS)產生的錯誤代碼和訊息，會依代碼ID以數字順序列出。
title: DCS 錯誤碼、訊息和範例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# DCS 錯誤碼、訊息和範例 {#dcs-error-codes-messages-and-examples}

產生的錯誤碼和訊息 [!UICONTROL Data Collection Servers] ([!DNL DCS])依程式碼ID以數值順序列出。

在下表中， *斜體* 代表變數預留位置。

## 系統錯誤碼 {#system-error-codes}

| 錯誤碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 0 | 未指定的錯誤 | 這是一個全包錯誤，會處理其他錯誤處理常式未涵蓋的事件。 疑難排解此錯誤相當困難。 這可能是由於各種未知的動作或事件所造成。 如果您收到此錯誤，請嘗試您的 [!DNL DCS] 再次要求。 連絡您的 [!DNL Adobe] 代表（如果問題仍然存在）。 |
| 1 | 找不到主機名稱的設定： `hostname` | 我們的合作夥伴布建團隊尚未設定請求中傳送的主機名稱。 連絡您的 [!DNL Adobe] 代表您是否看到此錯誤訊息。 |
| 2 | 無效 `d_orgid` 值（找不到此組織id的設定）： `ID` | 組織ID不正確。 請檢查您的ID，然後再次嘗試請求。 如果您不知道或沒有組織ID，請參閱「管理頁面」一節 [組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) 以取得如何找到該檔案的相關資訊。 |
| 10 | 無法評估特徵 | 要求的特徵已經過部分評估或完全沒有評估。 連絡您的 [!DNL Adobe] 代表（如果問題仍然存在）。 |

## 整合錯誤代碼 {#integration-error-codes}

| 錯誤碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 100 | 無法擷取要求的主機名稱 | 一個 [!DNL API] 呼叫未傳送主機 [!DNL HTTP] 標頭。 請將主機標頭新增至呼叫，然後再試一次。 大部分的瀏覽器和 [!DNL API] 使用者端會自動執行此動作。 |
| 101 | 無效 [!DNL Experience Cloud] 傳入的ID `ID` | 此 [!DNL DCS] 呼叫包含無效的呼叫 [!DNL Experience Cloud] ID。 檢查 `d_mid=` 標頭字串中的機碼值組。 確定您傳入的是正確的 [!DNL Experience Cloud] ID，請重試請求。 |
| 102 | 無效 [!DNL AAM ID] 傳入請求 `ID` | 此 [!DNL DCS] 呼叫包含無效的呼叫 [!DNL Audience Manager] ID。 檢查 `d_uuid=` 標頭字串中的機碼值組。 確定您傳入的是正確的 [!DNL Audience Manager] ID，請重試請求。 |
| 104 | 所有客戶ID無效 | 您呼叫中的所有客戶ID無效。 請檢查您的ID，然後再試一次。 |
| 109 | Referer `HTTP referer` 不允許用於合作夥伴 `Partner ID` | 此 `HTTP referer` 呼叫的合作夥伴ID不允許呼叫上的標頭。 檢查 `HTTP referer` 標題正確。 |
| 111 | 無效 `IMS` 已收到Token | 已傳回 [!DNL Audience Manager] - [!DNL Adobe Target] 整合。 呼叫時擲回錯誤 [!DNL DCS]，包含無效的 [!DNL IMS] Token。 權杖可能格式錯誤、已過期或使用者可能無權存取所需的資源。 |

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
   <td colname="col2"> <p>遇到ID的選擇退出標籤 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客戶已選擇退出接收以興趣為基礎的廣告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>封鎖的Cookie </p> </td> 
   <td colname="col3"> <p>當使用者的瀏覽器封鎖第三方Cookie時傳回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>透過以下方式遇到信任關係： <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>使用者已透過NAI啟動選擇退出程式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作夥伴封鎖來自此國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP位址， <span class="wintitle"> DCS</span> 封鎖來自合作夥伴刻意限制流量的國家/地區的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允許來自這個國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP位址， <span class="wintitle"> DCS</span> 封鎖來自下列國家/地區的請求： </p> <p> 
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
   <td colname="col2"> <p> 無法從設定檔快取中讀取ID的特徵： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法從我們的內部儲存裝置讀取使用者設定檔時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 無法從設定檔快取中讀取客戶ID的裝置ID： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>於以下情況傳回： <a href="../../../reference/ids-in-aam.md"> 裝置ID</a> 無法擷取設定檔連結合併規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>無法讀取裝置ID的相關客戶： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>於以下情況傳回： <a href="../../../reference/ids-in-aam.md"> 客戶ID (UUID)</a> 無法從我們的內部儲存區中擷取與裝置ID相關聯的上次驗證合併規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 無法讀取裝置叢集以取得識別碼： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>無法針對此裝置ID傳回來自相同裝置圖表叢集的連結裝置ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>無法執行移轉，因為主要裝置的設定檔讀取失敗 </p> </td> 
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料存放區可能會發生擴充性問題(<span class="wintitle"> PC</span>)。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>無法從執行移轉 <code><i>ID</i></code> 至 <code><i>ID</i></code>，因為設定檔讀取失敗 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料存放區可能會發生擴充性問題(<span class="wintitle"> PC</span>)。 如果問題仍然存在，請聯絡您的Adobe代表。 </p> </td> 
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
   <td colname="col3"> <p>客戶ID無效（缺少資料來源的值、缺少整合代碼、資料來源的格式無效、已封鎖客戶ID、空白客戶ID、未獲授權存取不屬於合作夥伴的資料來源）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>已超出最大客戶ID數。 允許的最大值為 <code><i>maximum allowed</i></code>. 找到了 <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>與跨裝置資料來源相關聯的客戶ID數量超過每個請求允許的跨裝置ID數量。 這些ID包含跨裝置、行動或Cookie ID。 限制目前設為10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未獲授權的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID資料來源並非目前組織ID所擁有時傳回。 如果您不知道或沒有組織ID，請參閱 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> 組織和帳戶連結</a> 以取得如何找到該檔案的相關資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>封鎖的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID被識別為惡意且已新增至封鎖清單時傳回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>封鎖的資料來源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當資料來源ID被識別為惡意且已新增至封鎖清單時傳回 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>封鎖的宣告裝置識別碼 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>裝置ID已識別為惡意，且已新增至封鎖清單。當我們收到超大數量的 <span class="wintitle"> DCS</span> 短時間內包含此裝置ID的請求。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>已封鎖的設定檔作業 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>已封鎖讀取/寫入動作，因為ID已被識別為惡意並已新增至封鎖清單請參閱錯誤碼306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客戶ID <code><i>ID</i></code> 已捨棄，因為超過每個請求宣告的客戶id限制 </p> </td> 
   <td colname="col3"> <p>與錯誤301相關。 此錯誤會指定因為超過限制而捨棄哪個客戶ID。 </p> <p>例如，如果在 <span class="wintitle"> DCS</span> 呼叫，將會捨棄其中兩個。 為了轉送哪些客戶已捨棄，此錯誤會在回應中出現兩次（每個捨棄的客戶ID顯示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>已捨棄客戶ID，因為它超過指定名稱空間的限制。 名稱空間ID為 <code><i>ID</i></code>，客戶id為 <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>如果為同一個名稱空間(<code> DPID</code>)在 <span class="wintitle"> DCS</span> 呼叫。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此範例中 <span class="wintitle"> DCS</span> 請求中，相同的名稱空間會宣告4個id （整合程式碼為1）。 其中一個ID會遭捨棄，並傳回錯誤310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>請求包含無效的引數 </p> </td> 
   <td colname="col3"> <p>此 <span class="wintitle"> DCS</span> 至少有一個URL引數未正確編碼時會傳回此錯誤碼。 在此案例中， <span class="wintitle"> DCS</span> 會忽略整個請求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上述範例要求中， <code> %</code> 序列編碼不正確。 因此， <span class="wintitle"> DCS</span> 會忽略它。 </p> <p>正確編碼的範例看起來應該像這樣： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>請求包含無效的全域裝置識別碼 </p> </td> 
   <td colname="col3"> <p>此 <span class="wintitle">DCS</span> 當請求包含無效的全域裝置ID時，會傳回此錯誤碼。 DCS會忽略無效ID並擲回312錯誤以及無效ID的特定錯誤。 請參閱 <a href="../../../features/global-data-sources.md" format="dita" scope="local">全域資料來源</a> 和 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager內的ID索引</a> 以取得正確裝置廣告ID格式與對應全球資料來源的詳細資訊。</p>
   <p>不正確呼叫的範例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>說明： An <span class="keyword">IDFA (DPID 20915)</span> 必須為大寫ID。 請求中提供的ID為小寫。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP ID不存在於GCL中</p> </td> 
   <td colname="col3"> <p>時間 <code>gdpr=1</code> 而且IAB TC字串是由評估時Audience Manager快取版本的「全域CMP清單」中不存在的CMP ID所產生，適用於IAB TCF的Audience Manager外掛程式會捨棄IAB TC字串，並照常處理請求。 IAB TCF v2.2 ${GDPR} 巨集設為0，且${GDPR_CONSENT_XXX} 巨集是空的。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID在GCL中標籤為已刪除</p> </td> 
   <td colname="col3"> <p>時間 <code>gdpr=1</code> 而且IAB TC字串是由在「全域CMP清單」的快取版本中標籤為已刪除的CMP所產生，如果評估時間超過從「全域CMP清單」刪除的時間，適用於IAB TCF的Audience Manager外掛程式會捨棄TC字串並照常處理請求。 IAB TCF v2.2 ${GDPR} 巨集設為0，且${GDPR_CONSENT_XXX} 巨集是空的。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>同意字串表示不同意</p> </td> 
   <td colname="col3"> <p>未提供同意時，適用於IAB TCF的Audience Manager外掛程式會選擇讓使用者退出後續的資料收集，或是在未偵測到合作夥伴內容時完全捨棄呼叫。</p>
   </td>
  </tr>

</tbody>
</table>

## 錯誤碼訊息範例 {#sample-error-codes}

此 [!DNL DCS] 在「 」中傳回錯誤碼和訊息 [!DNL JSON] 物件或HTTP回應字串中的X標題。

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

X標頭擷取的錯誤碼會顯示在URL字串中，如下所示： `X-Error: 101,102`.

[競爭條件與錯誤處理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
