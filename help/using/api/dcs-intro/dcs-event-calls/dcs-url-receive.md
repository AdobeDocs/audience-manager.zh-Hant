---
description: 請繼續這裡，以取得如何在/event呼叫中要求DCS回應的詳細資訊。 本節包含回應範例和回應中常見資料元素的定義。
seo-description: 請繼續這裡，以取得如何在/event呼叫中要求DCS回應的詳細資訊。 本節包含回應範例和回應中常見資料元素的定義。
seo-title: 接收來自 DCS 的資料
solution: Audience Manager
title: 接收來自 DCS 的資料
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# 接收來自 DCS 的資料 {#receive-data-from-the-dcs}

請繼續此處，以取得有關如何在呼叫中 [!DNL DCS] 請求回應的 `/event` 資訊。 本節包含回應範例和回應中常見資料元素的定義。

在檢視此內容之前，請參 [閱傳送資料至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS響應參數： 評論 {#dcs-response-parameters}

如果您 [!DNL DCS] 想要從 `d_rtbd=json` 收到回覆，請求必須包含在內 [!DNL DCS]。 如果 [!DNL DCS] 您省略此參數，則不會傳回資料。 要求資料的基 [!DNL DCS] 本呼叫使用下列語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 範例回應 {#sample-response}

回想一下，在 [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation中，虛構的公司 [!DNL Acme, Inc.] 打了這個電話：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由於此呼叫包含所需的回應參數，因此 [!DNL DCS] 會傳回下列 [!DNL JSON] 物件。 您的產品可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應參數 {#response-parameters}

下表列出並定義了您在回應中可能看到的較常見參數 [!DNL DCS]。 這套用至事件呼叫或傳回資 [!DNL DCS] 料的 [!DNL API] 其他查詢。

| 參數 | 說明 |
|--- |--- |
| `c` | 已設為 [URL目的地的URL](../../../features/destinations/create-url-destination.md)。 |
| `cn` | Cookie目標之Cookie名稱欄位中設定的名稱 [或ID](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 傳送至由&quot;cn&quot;:&quot;目標名稱&quot;參數定義之目標的值。 |
| `dcs_region` | 伺 [服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此物件包含在UI中設定之所有URL目的地的資訊。 此物件的清單會根據使用者的動作而動態顯示。 |
| `dmn` | 這是在Cookie目標的Cookie網域欄位中指定的網域。 See [Optional Settings for Cookie Destinations](../../../features/destinations/cookie-destination-options.md).  若是伺服器對伺服器的整合，我們建議使用類似的網域 `aam-api.com`。 |
| `e` | 已在URL目標中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。 此物件的清單會根據使用者的動作而動態顯示。 |
| `tid` | 交易ID，是用於除錯的唯一12個字元ID。 每次對DCS的/event呼叫都會收到一個ID，您可在支援查詢中參考它，以獲得更好、更快速的回應。 |
| `ttl` | 以天為單位的Cookie存留時間值。 |
| `u`和`uuid` | 由Audience Manager指派的唯一使用者ID。 如果您要進行伺服器對伺服 [器DCS呼叫，則此為必要項](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。 |
| `y` | 目標類型、iFrame(`iframe`)或影像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支援的關鍵值字首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

