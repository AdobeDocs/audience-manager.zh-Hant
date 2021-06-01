---
description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，可在提出請求時使用OAuth 2.0設定Audience Manager以進行驗證。 如此一來，您就能從Audience Manager向端點發出已驗證的請求。
seo-description: 透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，可在提出請求時使用OAuth 2.0設定Audience Manager以進行驗證。 如此一來，您就能從Audience Manager向端點發出已驗證的請求。
seo-title: OAuth 2.0 整合即時傳出傳輸
solution: Audience Manager
title: OAuth 2.0 整合即時傳出傳輸
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: 傳出資料傳輸
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# [!DNL OAuth 2.0] 整合即時傳出傳輸{#oauth-integration-for-real-time-outbound-transfers}

透過即時伺服器對伺服器整合將區段發佈至合作夥伴目的地時，可在提出要求時使用[!DNL OAuth 2.0]設定Audience Manager以進行驗證。 如此一來，您就能從Audience Manager向端點發出已驗證的請求。

## 驗證流{#auth-flow}

[!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4)驗證實作是以用戶端認證授權流程為基礎，並遵循下列步驟：

1. 您必須向我們提供：
   * 產生驗證Token的[!DNL OAuth 2.0]端點。
   * 用於產生Token的憑證。
1. [!DNL Audience Manager]顧問使用您提供的資訊設定[destination](../../../features/destinations/destinations.md)。
1. 將區段對應至此目的地後，我們的即時資料傳輸系統[IRIS](../../../reference/system-components/components-data-action.md#iris)會向代號端點發出`POST`請求，以交換承載代號的認證。
1. 對於向合作夥伴端點發佈的每個區段請求，[!UICONTROL IRIS]會使用承載權杖進行驗證。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作為[!DNL Audience Manager]合作夥伴，需要下列端點才能接收已驗證的請求：

### IRIS用於獲取承載令牌的端點1

此端點會接受步驟1提供的憑證，並產生用於後續請求的承載權杖。

* 端點必須接受`HTTP POST`請求。
* 端點必須接受並查看[!DNL Authorization]標題。 此標題的值將是：`Basic <credentials_provided_by_partner>`。
* 端點必須查看[!DNL Content-type]標題，並驗證其值為`application/x-www-form-urlencoded ; charset=UTF-8`。
* 要求內文將為`grant_type=client_credentials`。

### 由Audience Manager向合作夥伴端點提出以取得承載權杖的範例要求

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

### 來自合作夥伴端點的範例回應

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS用來使用承載權杖發佈區段的端點2

[!DNL Audience Manager] 當使用者符合區段資格時，會以近乎即時的方式傳送資料至此端點。此外，此方法最多可每24小時傳送批次離線或已上線資料。

端點1產生的承載權杖可用來向此端點發出請求。 [!DNL Audience Manager]即時資料傳輸系統[IRIS](../../../reference/system-components/components-data-action.md#iris)構造正常的HTTPS請求，並包括授權頭。 此標題的值將是：承載`<bearer token from step 1>`。

### 來自合作夥伴端點的範例回應

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
>此要求包含標準裝載（要求內容）。

## 重要考量 {#considerations}

### 代號是密碼

合作夥伴提供的認證以及使用[!DNL OAuth 2.0]流程進行驗證時由[!DNL Audience Manager]取得的代號是敏感資訊，不得與第三方共用。

### [!DNL SSL] 必填

[!DNL SSL] 必須使用才能維護安全驗證程式。所有要求，包括用來取得和使用代號的要求，都必須使用`HTTPS`端點。
