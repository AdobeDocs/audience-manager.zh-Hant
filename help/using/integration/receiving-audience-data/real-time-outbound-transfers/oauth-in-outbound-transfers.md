---
description: 當通過即時伺服器到伺服器整合將段發佈到合作夥伴目標時，可以設定Audience Manager，以便在發出請求時使用OAuth 2.0進行身份驗證。 這提供了將經過身份驗證的請求從Audience Manager發送到終結點的能力。
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: OAuth 2.0 整合即時傳出傳輸
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# [!DNL OAuth 2.0] 即時出站傳輸整合{#oauth-integration-for-real-time-outbound-transfers}

當通過即時伺服器到伺服器整合將段發佈到合作夥伴目標時，可以設定Audience Manager以使用 [!DNL OAuth 2.0] 請求時。 這提供了將經過身份驗證的請求從Audience Manager發送到終結點的能力。

## 驗證流 {#auth-flow}

的 [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) 身份驗證實現基於客戶端憑據授予流，並遵循以下步驟：

1. 您必須向我們提供：
   * 的 [!DNL OAuth 2.0] 生成驗證令牌的終結點。
   * 用於生成令牌的憑據。
1. 安 [!DNL Audience Manager] 顧問設定 [目標](../../../features/destinations/destinations.md) 使用您提供的資訊。
1. 一旦一個資料段被映射到這個目標，我們的即時資料傳輸系統， [虹膜](../../../reference/system-components/components-data-action.md#iris)的 `POST` 請求令牌端點以交換承載令牌的憑據。
1. 對於每個段向夥伴終結點發佈請求， [!UICONTROL IRIS] 使用承載令牌進行身份驗證。

![](assets/oauth2-iris.png)

## 要求 {#auth-requirements}

作為 [!DNL Audience Manager] 需要以下端點來接收經過身份驗證的請求：

### IRIS用於獲取承載令牌的端點1

此端點將接受步驟1中提供的憑據，並生成將用於後續請求的承載令牌。

* 終結點必須接受 `HTTP POST` 請求。
* 端點必須接受並查看 [!DNL Authorization] 標題。 此標題的值將為： `Basic <credentials_provided_by_partner>`。
* 端點必須查看 [!DNL Content-type] 頭並驗證其值 `application/x-www-form-urlencoded ; charset=UTF-8`。
* 請求的正文將 `grant_type=client_credentials`。

### 通過Audience Manager對夥伴端點的示例請求以獲得承載令牌

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

### 來自夥伴終結點的示例響應

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### IRIS使用端點2使用承載令牌發佈段

[!DNL Audience Manager] 當用戶符合段的條件時，將資料以接近即時的方式發送到此端點。 此外，此方法可以每24小時發送一批離線或掛接資料。

端點1生成的承載令牌用於向此端點發出請求。 的 [!DNL Audience Manager] 即時資料傳輸系統， [虹膜](../../../reference/system-components/components-data-action.md#iris)，構建普通HTTPS請求並包括授權標頭。 此標題的值將為：持 `<bearer token from step 1>`。

### 來自夥伴終結點的示例響應

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
>此請求包含標準負載（請求內容）。

## 重要注意事項 {#considerations}

### 令牌是密碼

合作夥伴提供的憑據和合作夥伴獲取的令牌 [!DNL Audience Manager] 使用 [!DNL OAuth 2.0] 敏感資訊，不得與第三方共用。

### [!DNL SSL] 必填

[!DNL SSL] 必須使用才能維護安全身份驗證過程。 所有請求，包括用於獲取和使用令牌的請求，都必須使用 `HTTPS` 端點。
