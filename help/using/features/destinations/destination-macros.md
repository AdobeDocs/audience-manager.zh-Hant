---
description: 說明可新增至目的地URL的巨集。
seo-description: 說明可新增至目的地URL的巨集。
seo-title: 定義的巨集目的地
solution: Audience Manager
title: 定義的巨集目的地
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: 目的地基本知識
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 3%

---

# 定義的巨集目的地 {#destination-macros-defined}

描述可添加到目標[!DNL URL]的宏。

<!-- destination-macros.xml -->

建立[!DNL URL]目標時，可將以下宏插入[!DNL URL]字串中。 請向資料/目的地合作夥伴查詢目標[!DNL URL]內正確放置巨集的資訊。

>[!NOTE]
>
>除非另有指示，否則巨集為選用。 *斜體*&#x200B;表示變數預留位置。

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 解釋 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>必填. </p> <p>定義對應區段值在目標URL中的位置。 這通常是<i>區段ID</i>，但也可能是整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>將使用者的<span class="keyword">Audience Manager</span> ID插入目標URL中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>資料源id</i>對應於傳入宏的資料源的標識符。 </p> <p>讓我們以一個簡單的例子來看看它是如何運作的。 在此案例中，我們有<span class="keyword">Audience Manager</span>合作夥伴，具有下列ID和條件： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">資料來源ID:<code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">內部客戶ID:<code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">宣告ID:合作夥伴想將這些值作為聲明ID <code> 1:CustomerABC</code>傳入。 </li> 
    </ul> <p>若要對<code>%dpid_<i>data source id</i>%</code>執行此操作，<span class="keyword">Audience Manager</span>合作夥伴會將巨集格式如下： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏將用<code> CustomerABC</code>替換<code> 1</code>。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指出GDPR法規是否適用於訪客。 使用此巨集，將同意包含在傳送至與IAB整合之URL目的地的區段中。 如需詳細資訊，請參閱<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF適用的Audience Manager外掛程式</a> 。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>訪客在您的網站上提供或拒絕同意時收集的同意字串（包括IAB廠商ID）。 使用此巨集，將同意字串納入傳送至與IAB整合之URL目的地的區段。 將<code>XXXX</code>替換為目標合作夥伴ID。 如需詳細資訊，請參閱<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF適用的Audience Manager外掛程式</a> 。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>檢測父網頁中使用的協定並將其插入到目標URL中。 例如:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果網頁是<b>https</b>://aam_client.com ，則此巨集將替換為<b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果網頁是<b>http</b>://aam_client.com ，則此宏將替換為<b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="keyword">Experience Cloud</span> ID插入目標URL中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="wintitle">資料收集伺服器(DCS)</span>區域插入目標URL。 為了將延遲降至最低，當訪客對<span class="keyword">Audience Manager</span>進行HTTP呼叫時，會將他們重新導向至最接近的<span class="wintitle"> DCS</span>資料中心。 這是透過DNS來達成的，DNS可偵測訪客的位置，並將訪客導向適當的資料中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>在目標URL中插入隨機數字，以執行快取破壞功能。 這會防止瀏覽器提供快取內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>將UNIX時間戳記插入目標URL，以防止瀏覽器提供快取內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 目標宏{#destination-cache-busting}的快取破壞

`%rnd%`和`%timestamp%`巨集會將唯一值插入[!DNL URL]字串中，以防止瀏覽器快取。

## 使用`%rnd%`和`%timestamp%` {#dest-cache-busting}進行快取破壞

<!-- c_dest_cache_busting.xml -->

瀏覽器快取（儲存）記憶體中經常要求的內容。 當頁面載入時，儲存的內容會從快取而非遠端伺服器提供。 此程式有助於維持有效的下載時間，因為資料會在本機提供，而非從其他位置提供。 不過，由於快取不需要伺服器呼叫，因此會人為降低唯一請求數，以扭曲報表。

快取破壞會阻止瀏覽器儲存和重複使用內容。 此技巧使用的程式碼會將隨機數字或時間戳記插入URL字串中，因此瀏覽器看起來就很獨特。 因此，每個`HTTP`呼叫都會計為對伺服器的個別請求。 強制對每個請求執行新伺服器呼叫，有助於維持報表正確性並減少差異。 [!DNL Audience Manager] 為快取破壞提供兩個宏：

* `%rnd%`:在URL中插入隨機數字。
* `%timestamp%`:將Unix日期/時間插入URL中。

## 比較`%rnd%`和`%timestamp%` {#compare-rnd-timestamp}

這兩個巨集都會阻止快取，但`%rnd%`可能會更有效。 例如，若使用`%timestamp%`，若有數位使用者同時檢視頁面，則會獲得相同的日期/時間值。 因此，[!DNL URL]並非唯一，且只會計算一次多個呼叫。 不過，`%rnd%`會為每個呼叫產生唯一的數值（即使使用者同時看到相同的頁面）。 這表示[!DNL URL]字串包含不同的值，並計為唯一。

>[!MORELIKETHIS]
>
>* [定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)

