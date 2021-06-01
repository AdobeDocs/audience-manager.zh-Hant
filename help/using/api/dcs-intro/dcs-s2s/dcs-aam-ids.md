---
description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-title: 從 DCS 回應取得使用者 ID 和區域。
solution: Audience Manager
title: 從 DCS 回應取得使用者 ID 和區域。
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# 從 DCS 回應取得使用者 ID 和區域{#get-user-ids-and-regions-from-a-dcs-response}。

本節說明如何剖析[!DNL DCS]回應，以擷取對[!DNL DCS]進行即時呼叫所需的訪客和地區ID。

## 用戶和地區ID {#user-region-ids}

[!DNL DCS]回應包含有關您網站訪客的資料。 您必須先取得訪客和地區ID，才能對[!DNL DCS]進行伺服器對伺服器呼叫。

* 識別資料並將資料與特定訪客建立關聯是必要的使用者ID。
* 地區ID是必要的，因為它與地區伺服器名稱相連結，您需要將資料傳送至[!DNL DCS]。 [!DNL DCS]會將資訊儲存在地理位置上最接近網站訪客的資料中心。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

以下說明這些參數。 *斜體*&#x200B;中的代碼表示變數預留位置。

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
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

此簡單響應顯示`UUID`和`ID`區域。 請注意，這僅是範例資料。 您的日誌檔案可能會更長、更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 後續步驟 {#next-steps}

擁有用戶ID和區域伺服器名稱后，就可以開始發送和接收[!DNL DCS]資料。 請參閱「進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)」。[
