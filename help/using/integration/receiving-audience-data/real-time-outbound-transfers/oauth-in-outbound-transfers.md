---
description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，Audience Manager可在提出請求時設定為使用OAuth2.0進行驗證。這表示能夠從Audience Manager核發已驗證的請求至您的端點。
seo-description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，Audience Manager可在提出請求時設定為使用OAuth2.0進行驗證。這表示能夠從Audience Manager核發已驗證的請求至您的端點。
seo-title: OAuth2.0的即時對外傳輸整合
solution: Audience Manager
title: OAuth2.0的即時對外傳輸整合
uuid: 39e370c-b3 bd-4b06-a1 af-60a024 ee7 ee
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] 整合即時傳輸傳輸{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. 這表示能夠從Audience Manager核發已驗證的請求至您的端點。

## Authentication Flow {#auth-flow}

[!DNL Adobe Audience Manager][OAuth2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 驗證實作是以用戶端認證為基礎，並遵循下列步驟：

1. 您必須提供下列項目：
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * 用來產生Token的憑證。
1. [!DNL Audience Manager] 顧問會使用您提供的資訊設定 [目標](../../../features/destinations/destinations.md) 。
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

[!DNL Audience Manager] 身為合作夥伴，需要下列端點才能接收已驗證的要求：

### IRIS用來取得承載Token的端點1

此端點會接受步驟中提供的憑證，並產生將用於後續請求的承載Token。

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Audience Manager對合作夥伴端點提出的範例要求，以取得持有人代號

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

### IRIS使用的端點，使用標題Token發佈區段

[!DNL Audience Manager] 可在使用者符合區段資格時即時將資料傳送至此端點。此外，此方法可每隔24小時傳送離線或已上線資料批次。

端點產生的標題Token會用來發出要求至此端點。[!DNL Audience Manager] 即時資料傳輸系統 [IRIS](../../../reference/system-components/components-data-action.md#iris)可建立一般HTTPS請求，並包含授權標題。The value for this header will be: Bearer `<bearer token from step 1>`.

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
>此請求包含標準裝載(請求內容)。

## Important Considerations {#considerations}

### Token是密碼

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] 是必要

[!DNL SSL] 必須用來維護安全驗證程序。All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.