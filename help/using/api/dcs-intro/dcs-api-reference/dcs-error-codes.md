---
description: 資料收集伺服器(DCS)按代碼ID以數字順序列出生成的錯誤代碼和消息。
title: DCS 錯誤碼、訊息和範例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# DCS 錯誤碼、訊息和範例 {#dcs-error-codes-messages-and-examples}

由 [!UICONTROL Data Collection Servers] ([!DNL DCS]按代碼ID按數字順序列出。

在下表中， *斜體* 表示變數佔位符。

## 系統錯誤代碼 {#system-error-codes}

| 錯誤代碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 0 | 未指定的錯誤 | 這是一個捕獲全部錯誤，它處理其他錯誤處理程式未覆蓋的事件。 排除此錯誤很困難。 它可能是由各種未知操作或事件引起的。 如果收到此錯誤，請嘗試 [!DNL DCS] 請求。 聯繫您 [!DNL Adobe] 代表。 |
| 1 | 找不到主機名的配置： `hostname` | 我們的合作夥伴設定團隊尚未設定在請求中發送的主機名。 聯繫您 [!DNL Adobe] 代表。 |
| 2 | 無效 `d_orgid` 值（找不到此組織ID的配置）: `ID` | 組織ID不正確。 請檢查您的ID，然後重試請求。 如果您不知道或沒有組織ID，請參閱「管理頁」部分 [組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) 以獲取有關如何查找它的資訊。 |
| 10 | 無法評估特徵 | 請求中的特徵要麼被部分評估，要麼根本沒有被評估。 聯繫您 [!DNL Adobe] 代表。 |

## 整合錯誤代碼 {#integration-error-codes}

| 錯誤代碼 | 錯誤訊息 | 說明 |
|---|---|---|
| 100 | 無法檢索請求的主機名 | 安 [!DNL API] 呼叫未發送主機 [!DNL HTTP] 的子目錄。 將主機頭添加到呼叫，然後重試。 大多數瀏覽器和 [!DNL API] 客戶端自動執行此操作。 |
| 101 | 無效 [!DNL Experience Cloud] 傳遞的ID `ID` | 的 [!DNL DCS] 調用包含無效 [!DNL Experience Cloud] ID。 檢查 `d_mid=` 標題字串中的key-value對。 確保你的路過正確 [!DNL Experience Cloud] ID，然後重試請求。 |
| 102 | 無效 [!DNL AAM ID] 已傳遞請求 `ID` | 的 [!DNL DCS] 調用包含無效 [!DNL Audience Manager] ID。 檢查 `d_uuid=` 標題字串中的key-value對。 確保你的路過正確 [!DNL Audience Manager] ID，然後重試請求。 |
| 104 | 所有客戶ID無效 | 您呼叫中的所有客戶ID都無效。 請檢查您的ID，然後重試。 |
| 109 | 參考 `HTTP referer` 不允許合作夥伴 `Partner ID` | 的 `HTTP referer` 呼叫上的夥伴ID不允許有呼頭。 檢查 `HTTP referer` 標題正確。 |
| 111 | 無效 `IMS` 令牌已接收 | 返回 [!DNL Audience Manager] - [!DNL Adobe Target] 整合。 調用時引發錯誤 [!DNL DCS]，包含無效 [!DNL IMS] 標籤。 令牌可能格式不正確、已過期，或者用戶無權訪問所需資源。 |

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
   <td colname="col2"> <p>遇到ID的選擇退出標籤 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>一位客戶選擇不接受基於興趣的廣告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>阻止的Cookie </p> </td> 
   <td colname="col3"> <p>當用戶的瀏覽器阻止第三方Cookie時返回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>通過 <a href="https://www.networkadvertising.org/" format="http" scope="external"> 奈</a> </p> </td> 
   <td colname="col3"> <p>用戶已通過NAI啟動選擇退出進程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作夥伴阻止來自此國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP地址， <span class="wintitle"> DCS</span> 阻止來自合作夥伴故意限制流量的國家的請求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允許來自此國家/地區的請求 </p> </td> 
   <td colname="col3"> <p>根據IP地址， <span class="wintitle"> DCS</span> 阻止來自以下國家的請求： </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴(CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">朝鮮(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">蘇丹(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">敘利亞(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 配置檔案檢索錯誤代碼 {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> 無法從配置檔案快取中讀取ID的特徵： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當無法從內部儲存讀取用戶配置檔案時返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 無法從配置檔案快取中讀取客戶ID的設備ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>在 <a href="../../../reference/ids-in-aam.md"> 設備ID</a> 無法為「配置檔案連結」合併規則檢索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>無法讀取設備ID的相關客戶： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>在 <a href="../../../reference/ids-in-aam.md"> 客戶ID(UUID)</a> 無法從內部儲存中檢索與設備ID關聯的上次驗證合併規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 無法讀取ID的設備群集： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>無法為此設備ID返回來自同一設備圖形群集的連結設備ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>無法執行遷移，因為主設備的配置檔案讀取失敗 </p> </td> 
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料儲存可能會遇到可擴充性問題(<span class="wintitle"> PCS</span>)。 如果問題仍然存在，請與Adobe代表聯繫。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>無法從 <code><i>ID</i></code> 至 <code><i>ID</i></code>，因為讀取配置檔案失敗 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>如果您收到此錯誤，我們的資料儲存可能會遇到可擴充性問題(<span class="wintitle"> PCS</span>)。 如果問題仍然存在，請與Adobe代表聯繫。 </p> </td> 
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
   <td colname="col3"> <p>客戶ID無效（缺少資料源值、缺少整合代碼、資料源格式無效、阻止的客戶ID、空白的客戶ID、未授權訪問不屬於合作夥伴的資料源的嘗試）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>超出客戶ID的最大數量。 允許的最大值為 <code><i>maximum allowed</i></code>。 找到 <code><i>maximum found</i></code>。</p> </td> 
   <td colname="col3"> <p>與跨設備資料源關聯的客戶ID數超過每個請求允許的跨設備ID數。 這些ID包括跨設備、移動或Cookie ID。 此限制當前設定為10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未授權的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID資料源不歸當前組織ID所有時返回。 如果您不知道或沒有組織ID，請參閱中的「查找組織ID」部分 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> 組織和帳戶連結</a> 以獲取有關如何查找它的資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>阻止的客戶ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當客戶ID被標識為惡意並添加到密鑰清單時返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>阻止的資料源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>當資料源ID被標識為惡意並添加到denylist時返回 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>已阻止聲明的設備ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>設備ID已被標識為惡意，並已添加到密鑰清單。如果收到的密鑰數量達到極大值，則可能會發生此情況 <span class="wintitle"> DCS</span> 在短時間內包含此設備ID的請求。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>阻止的配置檔案操作 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>已阻止讀/寫操作，因為ID已被標識為惡意，並已添加到denylist請參閱錯誤代碼306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客戶ID <code><i>ID</i></code> 已丟棄，因為它超過了每個請求聲明的客戶ID的限制 </p> </td> 
   <td colname="col3"> <p>與錯誤301相關。 此錯誤指定因超出限制而放棄的客戶ID。 </p> <p>例如，如果在上聲明了12個客戶ID <span class="wintitle"> DCS</span> 電話，其中兩個將被丟棄。 為了中繼丟棄了哪些錯誤，此錯誤將在響應中出現兩次（對於每個丟棄的客戶ID顯示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>客戶ID已丟棄，因為它超出了給定命名空間的限制。 命名空間ID為 <code><i>ID</i></code>，客戶id <code><i>ID</i></code>。 </p> </td> 
   <td colname="col3"> <p>如果為同一命名空間聲明的客戶ID超過3個，則返回此錯誤代碼(<code> DPID</code>) <span class="wintitle"> DCS</span> 呼叫。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此示例中 <span class="wintitle"> DCS</span> 請求，為同一命名空間聲明了4個id（整合代碼為1）。 其中一個ID被丟棄，並返回錯誤310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>請求包含無效參數 </p> </td> 
   <td colname="col3"> <p>的 <span class="wintitle"> DCS</span> 當至少一個URL參數未正確編碼時返回此錯誤代碼。 在這個例子中， <span class="wintitle"> DCS</span> 無視整個請求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上述示例請求中， <code> %</code> 序列被錯誤編碼。 因此， <span class="wintitle"> DCS</span> 會忽略它。 </p> <p>正確編碼的示例應如下所示： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>請求包含無效的全局設備ID </p> </td> 
   <td colname="col3"> <p>的 <span class="wintitle">DCS</span> 當請求包含無效的全局設備ID時，返回此錯誤代碼。 DCS忽略無效ID並引發312錯誤以及無效ID的特定錯誤。 請參閱 <a href="../../../features/global-data-sources.md" format="dita" scope="local">全局資料源</a> 和 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager中ID的索引</a> 獲取有關正確設備廣告ID格式和相應全局資料源的詳細資訊。</p>
   <p>錯誤調用示例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>說明：安 <span class="keyword">IDFA(DPID 20915)</span> 必須是大寫ID。 請求中提供的ID為小寫。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>GCL中不存在CMP ID</p> </td> 
   <td colname="col3"> <p>當 <code>gdpr=1</code> 而IAB TC字串由評估時不在Audience Manager快取的全局CMP清單版本中的CMP ID生成，IAB TC的Audience Manager插件丟棄IAB TC字串並照常處理請求。 IAB TCF v2.0 ${GDPR}宏設定為0，而${GDPR_CONNENCE_XXX}宏為空。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID在GCL中標籤為已刪除</p> </td> 
   <td colname="col3"> <p>當 <code>gdpr=1</code> 而IAB TC字串由在我們的全局CMP清單快取版本中標籤為已刪除的CMP生成，如果評估時間超過從全局CMP清單刪除時間，則IAB TCF的Audience Manager插件會丟棄TC字串並照常處理請求。 IAB TCF v2.0 ${GDPR}宏設定為0，而${GDPR_CONNENCE_XXX}宏為空。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>同意字串表示不同意</p> </td> 
   <td colname="col3"> <p>當未提供同意時，IAB TCF的Audience Manager插件會選擇用戶不再進行進一步的資料收集，或者如果未檢測到夥伴上下文，則完全放棄呼叫。</p>
   </td>
  </tr>

</tbody>
</table>

## 示例錯誤代碼消息 {#sample-error-codes}

的 [!DNL DCS] 返回錯誤代碼和消息 [!DNL JSON] 對象或HTTP響應字串中的X — 標頭。

### 示例DCS錯誤代碼和消息

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

由X頭捕獲的錯誤代碼會出現在URL字串中， `X-Error: 101,102`。

[競爭條件與錯誤處理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
