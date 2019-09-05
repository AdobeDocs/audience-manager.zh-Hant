---
description: 請繼續這裡以取得如何在/event呼叫中請求DCS回應的相關資訊。本節包含回應範例和回應中常見資料元素的定義。
seo-description: 請繼續這裡以取得如何在/event呼叫中請求DCS回應的相關資訊。本節包含回應範例和回應中常見資料元素的定義。
seo-title: 從DCS接收資料
solution: Audience Manager
title: 從DCS接收資料
uuid: fbb771977-8530-48a8-b708-d785 f7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 從DCS接收資料 {#receive-data-from-the-dcs}

請繼續這裡以取得如何在呼叫中請求 [!UICONTROL DCS] 回應的相關資訊 `/event` 。本節包含回應範例和回應中常見資料元素的定義。

在檢閱此內容之前，請參閱 [將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS回應參數：A Review {#dcs-response-parameters}

[!UICONTROL DCS] 如果您想接收回應，則必須包含 `d_rtbd=json` 您的請求 [!UICONTROL DCS]。如果省略此參數，則 [!UICONTROL DCS] 不會傳回資料。要求資料的 [!UICONTROL DCS] 基本呼叫使用此語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 範例回應 {#sample-response}

請記得，從 [傳送資料到DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) 文件，假設公司 [!DNL Acme, Inc.] 進行了此呼叫：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

當此呼叫包含必要的回應參數時， [!UICONTROL DCS] 會傳回下列所示 [!DNL JSON] 的物件。您的內容可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應參數 {#response-parameters}

下表列出並定義您可能在回應中看到的更常用參數 [!UICONTROL DCS]。這適用於事件呼叫或其他 [!UICONTROL DCS][!DNL API] 傳回資料的查詢。

| 參數 | 說明 |
|--- |--- |
| `c` | 已設為 [URL目的地](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | [Cookie目的地的Cookie名稱欄位中設定的名稱或ID](../../../features/destinations/create-cookie-destination.md)。 |
| `cv` | 傳送至「cn」定義之目的地的值：「deinaton name」參數。 |
| `dcs_region` | [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此物件包含所有在UI中設定之URL目的地的資訊。此物件的清單會根據使用者的動作進行動態。 |
| `dmn` | 這是Cookie網域欄位中指定的網域，用於Cookie目的地。請參閱 [「Cookie目的地的選擇性設定](../../../features/destinations/cookie-destination-options.md)」。對於伺服器與伺服器整合，建議您使用網域之類 `aam-api.com`的網域。 |
| `e` | 已在URL目的地中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。此物件的清單會根據使用者的動作進行動態。 |
| `tid` | 交易ID，這是用於除錯用途的唯一12個字元ID。每個/event呼叫DCS都會收到一個提示，您可以在支援中參考，以獲得更好且更快速的回應。 |
| `ttl` | Cookie的存留時間值。 |
| `u`和`uuid` | Audience Manager指派的唯一使用者ID。如果您要建立 [伺服器至伺服器DCS呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，這是必要的。 |
| `y` | 目的地類型、iFrame(`iframe`)或影像(`img`)。 |

>[!MORE_贊_ this]
>
>* [DCS支援的索引鍵值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

