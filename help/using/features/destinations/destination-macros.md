---
description: 說明可添加到目標URL的宏。
seo-description: 說明可添加到目標URL的宏。
seo-title: 定義的巨集目的地
solution: Audience Manager
title: 定義的巨集目的地
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 3%

---


# 定義的巨集目的地 {#destination-macros-defined}

介紹可添加到目標[!DNL URL]的宏。

<!-- destination-macros.xml -->

建立[!DNL URL]目標時，可將以下宏插入[!DNL URL]字串中。 請洽詢您的資料／目標合作夥伴，瞭解目標[!DNL URL]中的正確巨集位置。

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
   <td colname="col2"> <p>必填. </p> <p>定義映射區段值在目標URL中的位置。 通常這是<i>區段ID</i>，但也可能是整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>將使用者的<span class="keyword"> Audience Manager</span> ID插入目標URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>資料源ID</i>對應於傳遞到宏的資料源的標識符。 </p> <p>讓我們以一個簡單的例子來看看它是如何運作的。 在此案例中，我們有<span class="keyword"> Audience Manager</span>合作夥伴，其ID和條件如下： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">資料來源ID:<code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">內部客戶ID:<code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">宣告的ID:合作夥伴希望將這些值作為聲明的ID <code> 1:CustomerABC</code>傳遞。 </li> 
    </ul> <p>若要對<code>%dpid_<i>data source id</i>%</code>執行此動作，<span class="keyword"> Audience Manager</span>合作夥伴會將巨集格式設為如下： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏將用<code> CustomerABC</code>替換<code> 1</code>。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指出GDPR規則是否適用於訪客。 使用此巨集，將同意包含在傳送至與IAB整合之URL目的地的區段中。 如需詳細資訊，請參閱IAB TCF</a>的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md"> Audience Manager外掛程式。</a></p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>當訪客在您的網站上提供或拒絕同意時收集的同意字串（包括IAB廠商ID）。 使用此巨集將同意字串包含在傳送至與IAB整合之URL目的地的區段中。 將<code>XXXX</code>替換為目標合作夥伴ID。 如需詳細資訊，請參閱IAB TCF</a>的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md"> Audience Manager外掛程式。 </a></p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>偵測父網頁中使用的通訊協定，並將其插入目標URL。 例如:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果網頁是<b>https</b>://aam_client.com，則此巨集將被<b>https</b>://url-destination.com取代 </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果網頁是<b>http</b>://aam_client.com，則此巨集將被<b>http</b>://url-destination.com取代 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="keyword"> Experience Cloud</span> ID插入目標URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="wintitle">資料收集伺服器(DCS)</span>區域插入目標URL。 為了將延遲降到最低，當訪客對<span class="keyword"> Audience Manager</span>進行HTTP呼叫時，會將其重新導向至最近的<span class="wintitle"> DCS</span>資料中心。 這是透過DNS來實現的，DNS可偵測訪客的位置，並將訪客導向適當的資料中心。 </p> </td> 
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

## 使用目標宏{#destination-cache-busting}進行快取破壞

`%rnd%`和`%timestamp%`巨集會將唯一值插入[!DNL URL]字串中，以防止瀏覽器快取。

## 使用`%rnd%`和`%timestamp%` {#dest-cache-busting}進行快取破壞

<!-- c_dest_cache_busting.xml -->

瀏覽器會快取（儲存）記憶體中經常要求的內容。 當頁面載入時，儲存的內容會從快取中提供，而非從遠端伺服器。 此程式有助於維持有效的下載時間，因為資料是本機提供，而非來自其他位置。 不過，由於快取不需要伺服器呼叫，因此會人為降低唯一請求數量，以傾斜報告。

快取破壞功能可防止瀏覽器儲存和重複使用內容。 此技巧使用將隨機數字或時間戳記插入URL字串的程式碼，讓它看起來對瀏覽器是獨一無二的。 因此，每個`HTTP`呼叫都會計為對伺服器的個別請求。 強制對每個請求進行新伺服器呼叫，有助於維持報告的正確性並減少不一致。 [!DNL Audience Manager] 提供兩個快取拆分宏：

* `%rnd%`:在URL中插入隨機數。
* `%timestamp%`:將Unix日期／時間插入URL。

## 比較`%rnd%`和`%timestamp%` {#compare-rnd-timestamp}

這兩個巨集都會阻止快取，但`%rnd%`可能會更有效率。 例如，使用`%timestamp%`時，若有數位使用者同時檢視頁面，則會取得相同的日期／時間值。 因此，[!DNL URL]並非唯一，而且多個呼叫只計一次。 但是，`%rnd%`會為每個呼叫產生唯一的數值（即使使用者同時看到相同的頁面）。 這表示[!DNL URL]字串包含不同的值，並計為唯一。

>[!MORELIKETHIS]
>
>* [定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)