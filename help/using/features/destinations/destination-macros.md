---
description: 說明可添加到目標URL的宏。
seo-description: 說明可添加到目標URL的宏。
seo-title: 定義的巨集目的地
solution: Audience Manager
title: 定義的巨集目的地
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# 定義的巨集目的地 {#destination-macros-defined}

介紹可添加到目標的宏 [!DNL URL]。

<!-- destination-macros.xml -->

建立目標 [!DNL URL] 時，可以將以下宏插入字串 [!DNL URL] 中。 請洽詢您的資料／目標合作夥伴，以瞭解在目標內的正確巨集位置 [!DNL URL]。

>[!NOTE]
>
>除非另有指示，否則宏是可選的。 *斜體*&#x200B;表示變數預留位置。

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
   <td colname="col2"> <p>必填. </p> <p>定義映射區段值在目標URL中的位置。 這通常是區 <i>段ID</i>，但也可以是整合程式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>將使用者的 <span class="keyword"> Audience Manager</span> ID插入目標URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>數 <i>據源ID</i> ，與傳遞給宏的資料源的標識符相對應。 </p> <p>讓我們以一個簡單的例子來看看它是如何運作的。 在此案例中，我們有 <span class="keyword"> Audience Manager</span> 合作夥伴，其ID和條件如下： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">資料來源ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">內部客戶ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">宣告的ID: 合作夥伴想將這些值傳入為宣告的ID <code> 1:CustomerABC</code>。 </li> 
    </ul> <p>若要使用， <code>%dpid_<i>data source id</i>%</code>Audience Manager <span class="keyword"></span> 合作夥伴會將巨集格式設為如下： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏將替換 <code> 1</code> 為 <code> CustomerABC</code>。 </p> <p> 
     <draft-comment>
       基於AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指出GDPR規則是否適用於訪客。 使用此巨集，將同意包含在傳送至與IAB整合之URL目的地的區段中。 如需詳 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">細資訊，請參閱IAB TCF的Audience Manager外掛程式</a> 。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>當訪客在您的網站上提供或拒絕同意時收集的同意字串（包括IAB廠商ID）。 使用此巨集將同意字串包含在傳送至與IAB整合之URL目的地的區段中。 以目 <code>XXXX</code> 標合作夥伴ID取代。 如需詳 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">細資訊，請參閱IAB TCF的Audience Manager外掛程式</a> 。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>偵測父網頁中使用的通訊協定，並將其插入目標URL。 例如:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果網頁是 <b>https</b>://aam_client.com，則此巨集將被 <b>https</b>://url-destination.com取代 </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果網頁是 <b>http</b>://aam_client.com，則此巨集將被 <b>http</b>://url-destination.com取代 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>將 <span class="keyword"> Experience Cloud</span> ID插入目標URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>將資料 <span class="wintitle"> 收集伺服器(DCS)區域插入目標URL</span> 。 為了將延遲降到最低，當訪客對 <span class="keyword"> Audience Manager進行HTTP呼叫時</span>，會將其重新導向至最接近的 <span class="wintitle"> DCS資料中心</span> 。 這是透過DNS來實現的，DNS可偵測訪客的位置，並將其導向適當的資料中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>在目標URL中插入隨機數字，以執行快取破壞功能。 這可防止瀏覽器提供快取的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>將UNIX時間戳記插入目標URL，以防止瀏覽器提供快取內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目標宏進行快取破壞 {#destination-cache-busting}

這些 `%rnd%` 和 `%timestamp%` 巨集會將唯一值插入字串， [!DNL URL] 以防止瀏覽器快取。

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

瀏覽器會快取（儲存）記憶體中經常要求的內容。 當頁面載入時，儲存的內容會從快取中提供，而非從遠端伺服器。 此程式有助於維持有效的下載時間，因為資料是本機提供，而非來自其他位置。 不過，由於快取不需要伺服器呼叫，因此會人為降低唯一請求數量，以傾斜報告。

快取破壞功能可防止瀏覽器儲存和重複使用內容。 此技巧使用將隨機數字或時間戳記插入URL字串的程式碼，讓它看起來對瀏覽器是獨一無二的。 因此，每個呼 `HTTP` 叫都會計為對伺服器的個別請求。 強制對每個請求進行新伺服器呼叫，有助於維持報告的正確性並減少不一致。 [!DNL Audience Manager] 提供兩個快取拆分宏：

* `%rnd%`: 在URL中插入隨機數。
* `%timestamp%`: 將Unix日期／時間插入URL。

## 比較 `%rnd%` 和 `%timestamp%` {#compare-rnd-timestamp}

這兩個巨集都會阻止快取， `%rnd%` 但效率可能更高。 例如，若有數 `%timestamp%`位使用者同時檢視頁面，則會獲得相同的日期／時間值。 因此，此呼叫並 [!DNL URL] 非唯一，且多個呼叫只會被計算一次。 不過， `%rnd%` 會為每個呼叫產生唯一的數值（即使使用者同時看到相同的頁面）。 這表示字 [!DNL URL] 串包含不同的值，並計為唯一。

>[!MORELIKETHIS]
>
>* [定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)