---
description: 說明您可以新增至目標URL的巨集。
seo-description: 說明您可以新增至目標URL的巨集。
seo-title: 目標巨集定義
solution: Audience Manager
title: 目標巨集定義
uuid: 982cab05-8a3f-4f96-b4 d0-291709712ad1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

When creating a [!DNL URL] destination, you can insert the following macros into the [!DNL URL] string. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>除非另有指示，否則巨集為選用項目。*斜體*&#x200B;表示變數預留位置。

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 解釋 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %別名%</code> </p> </td> 
   <td colname="col2"> <p>必填. </p> <p>定義目標URL中對應之區段值的位置。Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data來源id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>資料來源ID</i> 對應至傳入巨集的資料來源識別碼。 </p> <p>讓我們來看看簡單範例。In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>To do this with the <code>%dpid_<i>data source id</i>%</code>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       根據AAM-22193https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %http_ proto%</code> </p> </td> 
   <td colname="col2"> <p>偵測上層網頁中使用的通訊協定，並將其插入目標URL中。例如: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %地區%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. 這是透過DNS實現的，它可偵測訪客的位置，並將其導向至適當的資料卡。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd</code> </p> </td> 
   <td colname="col2"> <p>在目標URL中插入隨機數字，執行快取修復函數。這可防止瀏覽器提供快取內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>插入UNIX時間戳記至目標URL，以防止瀏覽器提供快取的內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

The `%rnd%` and `%timestamp%` macros insert unique values into a [!DNL URL] string to prevent browser caching.

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

瀏覽器快取(儲存)常要求的記憶體中的內容。當頁面載入時，儲存的內容會從快取中提供，而非從遠端伺服器。此程序可協助維護有效率的下載時間，因為資料可在本機提供，而非其他位置。不過，由於快取不需要伺服器呼叫，因此可以手動降低唯一請求數目，以進行傾斜報告。

快取抑制功能可防止瀏覽器儲存和重復使用內容。此技巧使用將隨機數字或時間戳記插入URL字串中的程式碼，使其看起來不像瀏覽器。As a result, each `HTTP` call is counted as a separate request to the server. 強制對每個要求進行新的伺服器呼叫，有助於維持報告精確性並減少不一致。[!DNL Audience Manager] 提供兩個巨集來修復快取：

* `%rnd%`：將隨機數字插入URL中。
* `%timestamp%`：將Unix日期/時間插入URL中。

## Comparing `%rnd%` and `%timestamp%` {#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. However, `%rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_贊_ this]
>
>* [目標巨集定義](../../features/destinations/destination-macros.md#destination-macros-defined)