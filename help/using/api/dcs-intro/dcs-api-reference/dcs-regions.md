---
description: 對DCS進行呼叫時，需要地區DCS伺服器主機名稱。 這是因為DCS會在地理位置接近網站訪客的資料中心儲存資訊。 如果您將查詢傳送至錯誤的DCS，則查詢會有效，但這些呼叫會很低效，而且會延遲回應。 若要提出DCS請求，請將地區ID與其對應的地區主機名稱相符，並使用正確的主機名稱來建立查詢。
seo-description: 對DCS進行呼叫時，需要地區DCS伺服器主機名稱。 這是因為DCS會在地理位置接近網站訪客的資料中心儲存資訊。 如果您將查詢傳送至錯誤的DCS，則查詢會有效，但這些呼叫會很低效，而且會延遲回應。 若要提出DCS請求，請將地區ID與其對應的地區主機名稱相符，並使用正確的主機名稱來建立查詢。
seo-title: DCS 區域 ID、位置與主機名稱。
solution: Audience Manager
title: DCS 區域 ID、位置與主機名稱。
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 9%

---


# DCS 區域 ID、位置與主機名稱{#dcs-region-ids-locations-and-host-names}。

要對 [!DNL DCS] 進行調用，需要區域伺服器主機名 [!DNL DCS]。 這是因為資 [!DNL DCS] 訊會儲存在地理位置接近網站訪客的資料中心。 如果您將查詢傳送到錯誤的位置，您的查詢會 [!DNL DCS]正常運作，但這些呼叫會效率低下，而且會延遲回應。 若要提出 [!DNL DCS] 請求，請將地區ID與其對應的地區主機名稱相符，並使用正確的主機名稱來建立查詢。

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS地區ID(dcs_region) </th> 
   <th colname="col2" class="entry"> 地區（和位置） </th> 
   <th colname="col3" class="entry"> 主機名稱 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>東南亞（新加坡） </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>南美洲（巴西聖保羅） </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>歐洲（愛爾蘭都柏林） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美國東部（美國維吉尼亞州） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋／大洋洲（澳洲雪梨） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美國西部（美國俄勒岡） </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>亞洲（日本東京） </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

您也可以使 [!DNL API] 用方法來取得可用區域的清 [!DNL DCS] 單。 See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).