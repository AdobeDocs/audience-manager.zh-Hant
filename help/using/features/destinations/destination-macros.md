---
description: 說明可新增至目的地URL的巨集。
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: 定義的巨集目的地
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# 定義的巨集目的地 {#destination-macros-defined}

說明您可以新增到目的地[!DNL URL]的巨集。

<!-- destination-macros.xml -->

建立[!DNL URL]目的地時，您可以將下列巨集插入到[!DNL URL]字串中。 請洽詢您的資料/目的地合作夥伴，瞭解目的地[!DNL URL]內適當的巨集位置。

>[!NOTE]
>
>巨集是選用的，除非另有指示。 *斜體*&#x200B;表示變數預留位置。

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
   <td colname="col2"> <p>必填。 </p> <p>定義目的地URL中對應區段值的位置。 這通常是<i>區段ID</i>，但也可能是整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>將使用者的<span class="keyword">Audience Manager</span> ID插入目的地URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>資料來源ID</i>對應到傳入巨集的資料來源識別碼。 </p> <p>讓我們來看看這如何在一個簡單的範例中運作。 在此案例中，我們有<span class="keyword">個Audience Manager</span>合作夥伴，具有下列ID和條件： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">資料來源識別碼： <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">內部客戶識別碼： <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">宣告ID：合作夥伴想要將這些值作為宣告ID <code> 1:CustomerABC</code>傳入。 </li> 
    </ul> <p>若要對<code>%dpid_<i>data source id</i>%</code>執行此動作，<span class="keyword">Audience Manager</span>合作夥伴將設定如下的巨集格式： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>巨集會以<code> CustomerABC</code>取代<code> 1</code>。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指出GDPR法規是否適用於訪客。 使用此巨集會包含傳送至與IAB整合之URL目的地的區段中的同意。 如需詳細資訊，請參閱適用於IAB TCF</a>的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>訪客在您的網站上提供或拒絕同意時收集的同意字串（包括IAB廠商ID）。 使用此巨集會包含同意字串，該字串會包含在傳送至與IAB整合之URL目的地的區段中。 將<code>XXXX</code>取代為目的地合作夥伴識別碼。 如需詳細資訊，請參閱適用於IAB TCF</a>的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager外掛程式。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>偵測上層網頁中使用的通訊協定，並將其插入目的地URL。 例如：
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果網頁為<b>https</b>：//aam_client.com，此巨集將會取代為<b>https</b>：//url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果網頁為<b>http</b>：//aam_client.com，此巨集將會取代為<b>http</b>：//url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="keyword">Experience Cloud</span> ID插入目的地URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>將<span class="wintitle">資料收集伺服器(DCS)</span>區域插入目的地URL。 為了將延遲降至最低，當訪客對<span class="keyword">Audience Manager</span>進行HTTP呼叫時，他們會被重新導向到最近的<span class="wintitle"> DCS</span>資料中心。 這是透過DNS達成，DNS可偵測訪客的位置，並將其導向適當的資料中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>將隨機數字插入目的地URL中，執行快取爆破功能。 這可防止瀏覽器提供快取的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>在目的地URL中插入UNIX時間戳記，以防止瀏覽器提供快取的內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目標巨集防止快取 {#destination-cache-busting}

`%rnd%`和`%timestamp%`巨集會將唯一值插入到[!DNL URL]字串中，以防止瀏覽器快取。

## 使用`%rnd%`和`%timestamp%`的快取破壞 {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

瀏覽器在記憶體中快取（儲存）經常要求的內容。 頁面載入時，儲存的內容會從快取提供，而非從遠端伺服器提供。 此程式有助於維持有效率的下載時間，因為資料是在本機（而非從其他位置）提供。 不過，由於快取不需要伺服器呼叫，因此可藉由人為降低不重複請求數來扭曲報表。

防快取可防止瀏覽器儲存及重複使用內容。 此技巧使用的程式碼會在URL字串中插入隨機數字或時間戳記，以便在瀏覽器中看起來是唯一的。 因此，每個`HTTP`呼叫都會計算為對伺服器的個別要求。 為每個請求強制執行新的伺服器呼叫有助於維持報告準確性並減少差異。 [!DNL Audience Manager]提供兩個巨集來防止快取：

* `%rnd%`：在URL中插入隨機數字。
* `%timestamp%`：將Unix日期/時間插入URL。

## 比較`%rnd%`與`%timestamp%` {#compare-rnd-timestamp}

這兩個巨集都防止快取，但`%rnd%`可能更有效率。 例如，透過`%timestamp%`，如果多位使用者同時檢視頁面，他們將取得相同的日期/時間值。 因此，[!DNL URL]不是唯一的，而且多個呼叫只會計算一次。 不過，`%rnd%`會為每個呼叫產生唯一的數值（即使使用者同時看到相同頁面）。 這表示[!DNL URL]字串包含不同的值，且計為唯一。

>[!MORELIKETHIS]
>
>* [定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)
