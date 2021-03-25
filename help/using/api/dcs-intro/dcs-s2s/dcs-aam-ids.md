---
description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-title: 從 DCS 回應取得使用者 ID 和區域。
solution: Audience Manager
title: 從 DCS 回應取得使用者 ID 和區域。
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---


# 從 DCS 回應取得使用者 ID 和區域{#get-user-ids-and-regions-from-a-dcs-response}。

本節說明如何剖析[!DNL DCS]回應，以擷取對[!DNL DCS]進行即時呼叫所需的訪客和地區ID。

## 使用者和地區ID {#user-region-ids}

[!DNL DCS]回應包含您網站訪客的相關資料。 您需要訪客和地區ID，才能對[!DNL DCS]進行伺服器對伺服器呼叫。

* 使用者ID是識別資料及與特定訪客建立關聯的必要條件。
* 地區ID是必要的，因為它與地區伺服器名稱相關聯，您需要將資料傳送至[!DNL DCS]。 [!DNL DCS]會在地理上最接近網站訪客的資料中心儲存資訊。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

這些參數說明如下。 *斜體字*&#x200B;中的代碼代表變數預留位置。

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 資料類型 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

此簡單響應顯示`UUID`和`ID`區域。 請注意，這僅是範例資料。 您的記錄檔可能會更長，也更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 後續步驟 {#next-steps}

一旦您擁有使用者ID和地區伺服器名稱，就可以開始傳送和接收[!DNL DCS]資料。 請參閱[進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
