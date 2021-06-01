---
description: 請繼續前往這裡，了解如何在/event呼叫中要求DCS回應的資訊。 本節包含回應範例和回應中常見資料元素的定義。
seo-description: 請繼續前往這裡，了解如何在/event呼叫中要求DCS回應的資訊。 本節包含回應範例和回應中常見資料元素的定義。
seo-title: 接收來自 DCS 的資料
solution: Audience Manager
title: 接收來自 DCS 的資料
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# 接收來自 DCS 的資料 {#receive-data-from-the-dcs}

請在此處繼續，以了解如何在`/event`呼叫中要求[!DNL DCS]回應的資訊。 本節包含回應範例和回應中常見資料元素的定義。

檢閱此內容之前，請參閱[將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## DCS回應參數：評論{#dcs-response-parameters}

若要從[!DNL DCS]接收回應，您的[!DNL DCS]要求必須包含`d_rtbd=json`。 如果忽略此參數， [!DNL DCS]將不會傳回資料。 對[!DNL DCS]發出要求資料的基本呼叫使用以下語法：

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## 範例回應 {#sample-response}

回想一下，在[將資料傳送至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)檔案中，虛構公司[!DNL Acme, Inc.]發出此呼叫：

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

由於此呼叫包含必要的回應參數，因此[!DNL DCS]會傳回下方所示的[!DNL JSON]物件。 您的可能類似或更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 回應參數 {#response-parameters}

下表列出並定義了在[!DNL DCS]的回應中可能看到的較常見參數。 這會套用至事件呼叫或傳回資料的其他[!DNL DCS] [!DNL API]查詢。

| 參數 | 說明 |
|--- |--- |
| `c` | 已設定為[URL目標](../../../features/destinations/create-url-destination.md)的URL。 |
| `cn` | 在[cookie目的地](../../../features/destinations/create-cookie-destination.md)的cookie名稱欄位中設定的名稱或ID。 |
| `cv` | 傳送至由&quot;cn&quot;:&quot;目的地名稱&quot;參數定義之目的地的值。 |
| `dcs_region` | [伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。 |
| `dests` | 此物件包含UI中已設定之所有URL目的地的資訊。 此物件的清單會根據使用者的動作而動態顯示。 |
| `dmn` | 這是Cookie目的地的Cookie網域欄位中指定的網域。 請參閱Cookie目的地的[選用設定](../../../features/destinations/cookie-destination-options.md)。  若要進行伺服器對伺服器的整合，建議您使用`aam-api.com`之類的網域。 |
| `e` | 已在URL目的地中設定的安全URL。 |
| `stuff` | 此物件包含所有Cookie目的地的資訊。 此物件的清單會根據使用者的動作而動態顯示。 |
| `tid` | 交易ID，此為唯一的12個字元ID，用於偵錯用途。 對DCS發出的每個/event呼叫都會收到一個tid，您可在支援查詢中參照，以獲得更好、更快速的回應。 |
| `ttl` | Cookie的存留時間值（以天為單位）。 |
| `u`和`uuid` | 依Audience Manager指派的不重複使用者ID。 如果您要進行[伺服器對伺服器DCS呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)，則此為必要項目。 |
| `y` | 目的地類型、iFrame(`iframe`)或影像(`img`)。 |

>[!MORELIKETHIS]
>
>* [DCS支援的機碼值前置詞和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

