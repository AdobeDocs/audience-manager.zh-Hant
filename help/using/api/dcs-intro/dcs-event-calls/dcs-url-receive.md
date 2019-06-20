---
description: 請繼續這裡以取得如何在/event呼叫中請求DCS回應的相關資訊。本節包含回應範例和回應中常見資料元素的定義。
seo-description: 請繼續這裡以取得如何在/event呼叫中請求DCS回應的相關資訊。本節包含回應範例和回應中常見資料元素的定義。
seo-title: 從DCS接收資料
solution: Audience Manager
title: 從DCS接收資料
uuid: fbb771977-8530-48a8-b708-d785 f7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. 本節包含回應範例和回應中常見資料元素的定義。

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

[!UICONTROL DCS] 如果您想接收回應，則必須包含 `d_rtbd=json` 您的請求 [!UICONTROL DCS]。The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>出版業者？<i></i><i>key1</i>= <i>val1</i>，&amp;<i>key2</i>= <i>val</i>&amp; d_ dst=1&amp; d_ rtbd= json&amp; d_ cb=<i>回呼</i></code>
</pre>

## 範例回應 {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. 您的內容可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應參數 {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| 參數 | 說明 |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | [Cookie目的地的Cookie名稱欄位中設定的名稱或ID](../../../features/destinations/manage-destinations.md#create-cookie-destination)。 |
| `cv` | 傳送至「cn」定義之目的地的值：「deinaton name」參數。 |
| `dcs_region` | [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此物件包含所有在UI中設定之URL目的地的資訊。此物件的清單會根據使用者的動作進行動態。 |
| `dmn` | 這是Cookie網域欄位中指定的網域，用於Cookie目的地。See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | 已在URL目的地中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。此物件的清單會根據使用者的動作進行動態。 |
| `tid` | 交易ID，這是用於除錯用途的唯一12個字元ID。每個/event呼叫DCS都會收到一個提示，您可以在支援中參考，以獲得更好且更快速的回應。 |
| `ttl` | Cookie的存留時間值。 |
| `u`和`uuid` | Audience Manager指派的唯一使用者ID。This is required if you&#39;re making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_贊_ this]
>
>* [DCS支援的索引鍵值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

