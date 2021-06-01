---
description: 呼叫DCS時需要地區DCS伺服器主機名稱。 這是因為DCS會將資訊儲存在地理位置鄰近網站訪客的資料中心。 如果您將查詢傳送至錯誤的DCS，則您的查詢會有效，但這些呼叫效率低下，且可能會延遲回應。 若要提出DCS要求，請將地區ID與其對應的地區主機名稱相符，並以適當的主機名稱來建立查詢。
seo-description: 呼叫DCS時需要地區DCS伺服器主機名稱。 這是因為DCS會將資訊儲存在地理位置鄰近網站訪客的資料中心。 如果您將查詢傳送至錯誤的DCS，則您的查詢會有效，但這些呼叫效率低下，且可能會延遲回應。 若要提出DCS要求，請將地區ID與其對應的地區主機名稱相符，並以適當的主機名稱來建立查詢。
seo-title: DCS 區域 ID、位置與主機名稱。
solution: Audience Manager
title: DCS 區域 ID、位置與主機名稱。
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 9%

---

# DCS 區域 ID、位置與主機名稱{#dcs-region-ids-locations-and-host-names}。

對[!DNL DCS]進行調用時需要區域[!DNL DCS]伺服器主機名。 這是因為[!DNL DCS]會將資訊儲存在地理位置鄰近網站訪客的資料中心中。 如果將查詢發送到錯誤的[!DNL DCS]，則查詢將有效，但這些調用效率低下，並且會延遲響應。 若要提出[!DNL DCS]要求，請將地區ID與其對應的地區主機名稱配對，並以正確的主機名稱形成您的查詢。

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
   <td colname="col2"> <p>南太平洋/大洋洲（澳大利亞雪梨） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美國西部（俄勒岡，美國） </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>亞洲（東京，日本） </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

您也可以使用[!DNL API]方法來取得可用[!DNL DCS]區域的清單。 請參閱[DCS地區API方法](../../../api/rest-api-main/aam-api-dcs-regions.md)。
