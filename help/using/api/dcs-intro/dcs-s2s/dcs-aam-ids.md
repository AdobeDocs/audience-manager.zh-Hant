---
description: 本節介紹如何分析DCS響應以檢索對DCS進行即時調用所需的訪問者和區域ID。
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: 從 DCS 回應取得使用者 ID 和區域。
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 16%

---

# 從 DCS 回應取得使用者 ID 和區域。 {#get-user-ids-and-regions-from-a-dcs-response}

本節介紹如何分析 [!DNL DCS] 響應，以檢索即時調用所需的訪問者和區域ID [!DNL DCS]。

## 用戶和區域ID {#user-region-ids}

A [!DNL DCS] 響應包含有關站點訪問者的資料。 您需要訪問者和區域ID，然後才能對 [!DNL DCS]。

* 需要用戶ID來識別資料並與特定訪問者相關聯。
* 區域ID是必需的，因為它與區域伺服器名稱相關，您需要將資料發送到 [!DNL DCS]。 的 [!DNL DCS] 將資訊儲存在地理上最接近站點訪問者的資料中心中。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

這些參數如下所述。 中的代碼 *斜體* 表示變數佔位符。

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
   <td colname="col2"> <p>整型 </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

這個簡單的回答顯示 `UUID` 區域 `ID`。 注意，這只是示例資料。 您的日誌檔案可能會更長、更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 後續步驟 {#next-steps}

用戶ID和區域伺服器名稱一經確定，就可以開始發送和接收 [!DNL DCS] 資料。 請參閱 [進行DCS API調用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
