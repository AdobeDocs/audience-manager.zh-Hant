---
description: 描述可添加到目標URL的宏。
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: 定義的巨集目的地
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 2%

---

# 定義的巨集目的地 {#destination-macros-defined}

描述可添加到目標的宏 [!DNL URL]。

<!-- destination-macros.xml -->

建立 [!DNL URL] 目標，可將以下宏插入 [!DNL URL] 的下界。 與您的資料/目標合作夥伴覈實，以瞭解目標中的宏位置 [!DNL URL]。

>[!NOTE]
>
>除非另有指明，宏是可選的。 *斜體*&#x200B;表示變數預留位置。

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 解釋 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>必填. </p> <p>定義映射段值在目標URL中的位置。 通常這是 <i>段ID</i>，但也可能是整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>插入用戶 <span class="keyword"> Audience Manager</span> 目標URL中的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>的 <i>資料源id</i> 與傳入宏的資料源的標識符相對應。 </p> <p>讓我們用一個簡單的例子來看它是如何工作的。 在這個例子中，我們 <span class="keyword"> Audience Manager</span> 具有以下ID和條件的合作夥伴： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">資料源ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">內部客戶ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">聲明的ID:合作夥伴希望將這些值作為聲明的ID傳遞 <code> 1:CustomerABC</code>。 </li> 
    </ul> <p>使用 <code>%dpid_<i>data source id</i>%</code>，也請參見Wiki頁。 <span class="keyword"> Audience Manager</span> partner將按如下方式格式化宏： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏將替換 <code> 1</code> 與 <code> CustomerABC</code>。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指示GDPR法規是否適用於訪問者。 使用此宏可在發送到與IAB整合的URL目標的段中包括同意。 請參閱 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience ManagerIAB TCF插件</a> 的雙曲餘切值。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>訪問者在您的站點上提供或拒絕同意時收集的同意字串（包括IAB供應商ID）。 使用此宏可在發送到與IAB整合的URL目標的段中包括同意字串。 替換 <code>XXXX</code> 目標合作夥伴ID。 請參閱 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience ManagerIAB TCF插件</a> 的雙曲餘切值。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>檢測父網頁中使用的協定，並將其插入目標URL。 例如:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果網頁是 <b>htps</b>://aam_client.com，此宏將替換為 <b>htps</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果網頁是 <b>http</b>://aam_client.com，此宏將替換為 <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>插入 <span class="keyword"> Experience Cloud</span> 目標URL中的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>插入 <span class="wintitle"> 資料收集伺服器(DCS)</span> 的子菜單。 為了最小化延遲，訪問者調用HTTP時 <span class="keyword"> Audience Manager</span>，它們被重定向到 <span class="wintitle"> DCS</span> 資料中心。 這是通過DNS實現的，DNS能夠檢測訪問者的位置並將他們引導到適當的資料中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>通過將隨機數插入目標URL執行快取拆分功能。 這防止瀏覽器為快取內容提供服務。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>將UNIX時間戳插入目標URL，以防止瀏覽器提供快取內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目標宏快取區 {#destination-cache-busting}

的 `%rnd%` 和 `%timestamp%` 宏將唯一值插入 [!DNL URL] 字串，以阻止瀏覽器快取。

## 快取突破 `%rnd%` 和 `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

瀏覽器快取（保存）記憶體中頻繁請求的內容。 當頁面載入時，保存的內容從快取而不是從遠程伺服器提供。 此過程有助於保持有效的下載時間，因為資料是從本地而不是從其他位置提供的。 但是，由於快取不需要伺服器調用，它會通過人工降低唯一請求數來扭曲報告。

衝突快取會阻止瀏覽器保存和重新使用內容。 此技術使用將隨機數或時間戳插入URL字串的代碼，這使它對瀏覽器來說顯得獨一無二。 因此，每個 `HTTP` 呼叫被計為對伺服器的單獨請求。 強制對每個請求調用新伺服器有助於保持報告準確性並減少差異。 [!DNL Audience Manager] 提供了兩個快取區域：

* `%rnd%`:在URL中插入隨機數。
* `%timestamp%`:將Unix日期/時間插入URL。

## 比較 `%rnd%` 和 `%timestamp%` {#compare-rnd-timestamp}

這兩個宏都阻止快取，但 `%rnd%` 可能會更有效。 例如， `%timestamp%`，如果多個用戶同時查看一個頁面，則他們將獲得相同的日期/時間值。 因此， [!DNL URL] 不唯一，並且只計數一次多個調用。 但是， `%rnd%` 為每個調用生成一個唯一的數值（即使用戶同時看到同一頁）。 這意味著 [!DNL URL] 字串包含不同的值，並被計為唯一。

>[!MORELIKETHIS]
>
>* [定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)

