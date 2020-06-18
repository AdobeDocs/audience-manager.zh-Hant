---
description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-title: 從 DCS 回應取得使用者 ID 和區域。
solution: Audience Manager
title: 從 DCS 回應取得使用者 ID 和區域。
uuid: 08036045-3b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# 從 DCS 回應取得使用者 ID 和區域{#get-user-ids-and-regions-from-a-dcs-response}。

本節說明如何剖析回 [!DNL DCS] 應以擷取對進行即時呼叫所需的訪客和地區ID [!DNL DCS]。

## 使用者和地區ID {#user-region-ids}

回應 [!DNL DCS] 包含您網站訪客的相關資料。 您必須先取得訪客和地區ID，才能對進行伺服器對伺服器的呼叫 [!DNL DCS]。

* 使用者ID是識別資料及與特定訪客建立關聯的必要條件。
* 地區ID是必要的，因為它與地區伺服器名稱相關聯，您需要將資料傳送至 [!DNL DCS]。 這些 [!DNL DCS] 資料中心儲存地理上最接近網站訪客的資料。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

這些參數說明如下。 斜體中的 *程式碼* ，代表變數預留位置。

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

此簡單回應會顯示 `UUID` 和地區 `ID`。 請注意，這僅是範例資料。 您的記錄檔可能會更長，也更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 後續步驟 {#next-steps}

一旦您擁有使用者ID和地區伺服器名稱，就可以開始傳送和接收 [!DNL DCS] 資料。 請參 [閱進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
