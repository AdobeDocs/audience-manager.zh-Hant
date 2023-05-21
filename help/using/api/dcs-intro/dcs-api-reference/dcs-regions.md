---
description: 要調用DCS，需要使用區域DCS伺服器主機名。 這是因為DCS將資訊儲存在地理上靠近站點訪問者的資料中心中。 如果將查詢發送到錯誤的DCS，則查詢將起作用，但這些調用效率低下，可能會延遲響應。 要發出DCS請求，請將區域ID與其相應的區域主機名匹配，並使用正確的主機名來形成查詢。
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: DCS 區域 ID、位置與主機名稱。
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 10%

---

# DCS 區域 ID、位置與主機名稱。 {#dcs-region-ids-locations-and-host-names}

區域 [!DNL DCS] 需要伺服器主機名來調用 [!DNL DCS]。 這是因為 [!DNL DCS] 將資訊儲存在地理上靠近站點訪問者的資料中心中。 如果您將查詢發送到錯誤的 [!DNL DCS]但這些呼叫效率低，可能會延遲響應。 做 [!DNL DCS] 請求，將區域ID與其相應的區域主機名匹配，並使用正確的主機名來形成查詢。

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS區域ID(dcs_region) </th> 
   <th colname="col2" class="entry"> 區域（和位置） </th> 
   <th colname="col3" class="entry"> 主機名 </th> 
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
   <td colname="col2"> <p>歐洲（都柏林，愛爾蘭） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美國東部（維吉尼亞，美國） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋/大洋洲（澳大利亞雪梨） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美國西部（美國俄勒岡州） </p> </td> 
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

您還可以使用 [!DNL API] 獲取可用清單的方法 [!DNL DCS] 區域。 請參閱 [DCS區域API方法](../../../api/rest-api-main/aam-api-dcs-regions.md)。
