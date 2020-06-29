---
description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目標時，Audience Manager可在提出要求時設定為使用OAuth 2.0進行驗證。 這可讓您從Audience Manager向端點發出已驗證的請求。
seo-description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目標時，Audience Manager可在提出要求時設定為使用OAuth 2.0進行驗證。 這可讓您從Audience Manager向端點發出已驗證的請求。
seo-title: OAuth 2.0 整合即時傳出傳輸
solution: Audience Manager
title: OAuth 2.0 整合即時傳出傳輸
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] 整合即時出站傳輸{#oauth-integration-for-real-time-outbound-transfers}

透過即時伺服器對伺服器整合將區段發佈至合作夥伴目標時，可設定Audience Manager，以便在提出要求時使 [!DNL OAuth 2.0] 用驗證。 這可讓您從Audience Manager向端點發出已驗證的請求。

## 驗證流程 {#auth-flow}

OAuth 2.0 [!DNL Adobe Audience Manager][](https://tools.ietf.org/html/rfc6749#section-4.4) 驗證實作是以用戶端認證授權流程為基礎，並遵循下列步驟：

1. 您必須提供以下資訊：
   * 產生 [!DNL OAuth 2.0] 驗證Token的端點。
   * 用來產生Token的憑證。
1. 顧 [!DNL Audience Manager] 問使用您提 [供的信](../../../features/destinations/destinations.md) 息設定目標。
1. 一旦區段映射至此目的地，我們的即時資料傳送系統 [IRIS](../../../reference/system-components/components-data-action.md#iris)`POST` ，會向Token端點提出要求，以交換承載Token的認證。
1. 對於向夥伴端點發佈的每個區段請求， [!UICONTROL IRIS] 請使用承載Token來驗證。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作為合 [!DNL Audience Manager] 作夥伴，需要下列端點才能接收已驗證的請求：

### IRIS用於獲取承載令牌的端點1

此端點將接受步驟1中提供的認證，並產生用於後續請求的承載Token。

* 端點必須接受 `HTTP POST` 請求。
* 端點必須接受並查看標 [!DNL Authorization] 題。 此標題的值為： `Basic <credentials_provided_by_partner>`.
* 端點必須查看標 [!DNL Content-type] 題並驗證其值為 `application/x-www-form-urlencoded ; charset=UTF-8`。
* 請求的正文為 `grant_type=client_credentials`。

### Audience Manager向合作夥伴端點提出的範例要求，以取得載體Token

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### 合作夥伴端點的範例回應

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS使用端點2來使用承載Token發佈區段

[!DNL Audience Manager] 當使用者符合區段的資格時，會即時傳送資料至此端點。 此外，此方法可每24小時傳送一批離線或已登入的資料。

端點1產生的承載Token可用來向此端點發出請求。 實 [!DNL Audience Manager] 時資料傳輸系統 [IRIS](../../../reference/system-components/components-data-action.md#iris)，構造正常的HTTPS請求並包括授權標頭。 此標題的值為： 持械 `<bearer token from step 1>`者。

### 合作夥伴端點的範例回應

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>此請求包含標準裝載（請求內容）。

## 重要考量事項 {#considerations}

### Token是密碼

合作夥伴所出示的憑證和使用流程進行驗 [!DNL Audience Manager] 證時所取得的代 [!DNL OAuth 2.0] 號是敏感資訊，不得與第三方共用。

### [!DNL SSL] 必要

[!DNL SSL] 必須使用才能維護安全驗證程式。 所有請求，包括用於取得和使用Token的請求，都必須使用 `HTTPS` 端點。