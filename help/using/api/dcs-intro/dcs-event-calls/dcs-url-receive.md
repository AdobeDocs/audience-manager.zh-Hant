---
description: 請繼續前往這裡，瞭解如何在/event呼叫中要求DCS回應。 本節包含回應的範例，以及回應中常用資料元素的定義。
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: 接收來自DCS的資料
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# 接收來自DCS的資料 {#receive-data-from-the-dcs}

請在此繼續，以取得如何在[!DNL DCS]呼叫中要求`/event`回應的相關資訊。 本節包含回應的範例，以及回應中常用資料元素的定義。

檢閱此內容之前，請參閱[將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS回應引數：評論 {#dcs-response-parameters}

如果您想要從[!DNL DCS]接收回應，您的`d_rtbd=json`要求必須包含[!DNL DCS]。 如果您省略此引數，[!DNL DCS]將不會傳回資料。 對[!DNL DCS]進行基本呼叫以要求資料，會使用以下語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 範例回應 {#sample-response}

回想一下，在[傳送資料至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)檔案中，虛構的公司[!DNL Acme, Inc.]進行了此呼叫：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由於此呼叫包含必要的回應引數，因此[!DNL DCS]傳回的[!DNL JSON]物件如下所示。 您的可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應引數 {#response-parameters}

下表列出並定義您在[!DNL DCS]的回應中可能看到的較常見引數。 這適用於事件呼叫或其他[!DNL DCS] [!DNL API]個傳回資料的查詢。

| 參數 | 說明 |
|--- |--- |
| `c` | 已設定為[URL目的地](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | 在[Cookie目的地](../../../features/destinations/create-cookie-destination.md)的Cookie名稱欄位中設定的名稱或ID。 |
| `cv` | 傳送至由「cn」：「destination name」引數定義之目的地的值。 |
| `dcs_region` | [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此物件包含在UI中設定的所有URL目的地的資訊。 此物件的清單是根據使用者的動作而動態的。 |
| `dmn` | 這是Cookie目的地的「Cookie網域」欄位中指定的網域。 請參閱[Cookie目的地的選用設定](../../../features/destinations/cookie-destination-options.md)。  針對伺服器對伺服器整合，我們建議使用類似`aam-api.com`的網域。 |
| `e` | 已在URL目的地中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。 此物件的清單是根據使用者的動作而動態的。 |
| `tid` | 交易ID，是用於偵錯用途的唯一12個字元ID。 向DCS發出的每個/event呼叫都會收到一個tid，您可以在支援查詢中參考該值，以取得更佳且更快速的回應。 |
| `ttl` | Cookie存留時間值（以天為單位）。 |
| `u`和`uuid` | Audience Manager指派的不重複使用者ID。 如果您進行[伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，則需要此專案。 |
| `y` | 目的地型別、iFrame (`iframe`)或影像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支援的索引鍵值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
