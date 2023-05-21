---
description: 在此處繼續獲取有關如何在/event調用中請求DCS響應的資訊。 本節包括響應示例和響應中公共資料元素的定義。
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: 接收來自 DCS 的資料
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 4%

---

# 接收來自 DCS 的資料 {#receive-data-from-the-dcs}

繼續此處獲取有關如何請求的資訊 [!DNL DCS] 響應 `/event` 呼叫。 本節包括響應示例和響應中公共資料元素的定義。

在查看此內容之前，請參閱 [將資料發送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS響應參數：回顧 {#dcs-response-parameters}

您 [!DNL DCS] 請求必須包括 `d_rtbd=json` 如果要從 [!DNL DCS]。 的 [!DNL DCS] 將不返回資料。 對 [!DNL DCS] 要請求資料，請使用此語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 範例回應 {#sample-response}

回想一下 [將資料發送到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 文檔，虛構公司 [!DNL Acme, Inc.] 撥打此電話：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由於此調用包括所需的響應參數，因此 [!DNL DCS] 寄回 [!DNL JSON] 下面顯示的對象。 你的可能相似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應參數 {#response-parameters}

下表列出並定義了在響應中可看到的更常見參數 [!DNL DCS]。 這適用於事件調用或其他 [!DNL DCS] [!DNL API] 返回資料的查詢。

| 參數 | 說明 |
|--- |--- |
| `c` | 已設定為 [URL目標](../../../features/destinations/create-url-destination.md)。 |
| `cn` | 在Cookie名稱欄位中設定的名稱或ID [cookie目標](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 發送到由&quot;cn&quot;:&quot;目標名稱&quot;參數定義的目標的值。 |
| `dcs_region` | 的 [伺服器到伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此對象包含在UI中配置的所有URL目標的資訊。 此對象的清單基於用戶的操作是動態的。 |
| `dmn` | 這是在Cookie域欄位中為Cookie目標指定的域。 請參閱 [Cookie目標的可選設定](../../../features/destinations/cookie-destination-options.md)。  對於伺服器到伺服器的整合，我們建議使用域，如 `aam-api.com`。 |
| `e` | 已在URL目標中設定的安全URL。 |
| `stuff` | 此對象包含所有Cookie目標的資訊。 此對象的清單基於用戶的操作是動態的。 |
| `tid` | 事務ID，是唯一的12個字元ID，用於調試。 每次對DCS的/event調用都會收到一個ID，您可以在支援查詢中引用該ID，以獲得更好、更快的響應。 |
| `ttl` | 以天為單位的Cookie生存時間值。 |
| `u`和`uuid` | 由Audience Manager分配的唯一用戶ID。 如果您正在進行 [伺服器到伺服器DCS呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。 |
| `y` | 目標類型， iFrame(`iframe`)或影像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支援的鍵值前置詞和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

