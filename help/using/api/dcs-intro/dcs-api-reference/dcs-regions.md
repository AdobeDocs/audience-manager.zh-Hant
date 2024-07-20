---
description: 呼叫DCS需要地區DCS伺服器主機名稱。 這是因為DCS會將資訊儲存在地理位置上接近網站訪客的資料中心。 如果您將查詢傳送至錯誤的DCS，查詢將正常運作，但這些呼叫效率不彰，可能會延遲回應。 若要提出DCS請求，請將地區ID與其對應的地區主機名稱配對，並使用正確的主機名稱來構成查詢。
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: DCS區域ID、位置與主機名稱
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# DCS區域ID、位置與主機名稱 {#dcs-region-ids-locations-and-host-names}

必須有地區[!DNL DCS]伺服器主機名稱才能呼叫[!DNL DCS]。 這是因為[!DNL DCS]會將資訊儲存在地理位置上接近網站訪客的資料中心。 如果您將查詢傳送至錯誤的[!DNL DCS]，則查詢將正常運作，但這些呼叫效率低下，可能會延遲回應。 若要提出[!DNL DCS]要求，請將地區ID與其對應的地區主機名稱比對，並以正確的主機名稱組成您的查詢。

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS地區ID (dcs_region) </th> 
   <th colname="col2" class="entry"> 地區（和位置） </th> 
   <th colname="col3" class="entry"> 主機名稱 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>東南亞（新加坡） </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>南美洲（巴西聖保羅） </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>歐洲（愛爾蘭都柏林） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>美國東部（美國維吉尼亞） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>南太平洋/大洋洲（澳洲雪梨） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>美國西部（美國奧勒岡州） </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>亞洲（日本東京） </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

您也可以使用[!DNL API]方法來取得可用[!DNL DCS]區域的清單。 請參閱[DCS地區API方法](../../../api/rest-api-main/aam-api-dcs-regions.md)。
