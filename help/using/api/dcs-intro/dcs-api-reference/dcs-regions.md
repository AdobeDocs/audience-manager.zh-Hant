---
description: 必須有區域DCS伺服器主機名稱才能呼叫DCS。這是因為DCS儲存了地理位置接近網站訪客的資料中心資訊。如果您將查詢傳送至錯誤的DCS，查詢將會運作，但這些呼叫效率不彰，並可能延遲回應。若要提出DCS請求，請比對地區ID至其對應的地區主機名稱，並以適當的主機名稱形式填寫查詢。
seo-description: 必須有區域DCS伺服器主機名稱才能呼叫DCS。這是因為DCS儲存了地理位置接近網站訪客的資料中心資訊。如果您將查詢傳送至錯誤的DCS，查詢將會運作，但這些呼叫效率不彰，並可能延遲回應。若要提出DCS請求，請比對地區ID至其對應的地區主機名稱，並以適當的主機名稱形式填寫查詢。
seo-title: DCS地區ID、位置和主機名稱
solution: Audience Manager
title: DCS地區ID、位置和主機名稱
uuid: ad150ffe-4583-472b-ac8 b-fb900 a7966 e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS地區ID(cs_ region) </th> 
   <th colname="col2" class="entry"> 地區(和地點) </th> 
   <th colname="col3" class="entry"> 主機名稱 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>東南亞(新加坡) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>南美洲(巴西聖保羅) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>歐洲(都柏林，愛爾蘭) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美國東部(美國維吉尼亞州) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋/奧克蘭(澳洲雪梨) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美國西部(美國俄勒岡) </p> </td> 
   <td colname="col3"> <p> <code> usew2.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>亞洲(東京、日本) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).