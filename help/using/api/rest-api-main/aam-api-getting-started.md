---
description: 一般需求、驗證、選擇性查詢參數、請求URL及其他參考的資訊。
seo-description: 一般需求、驗證、選擇性查詢參數、請求URL及其他參考的資訊。
seo-title: REST API快速入門
solution: Audience Manager
title: REST API快速入門
uuid: af0e527e-6eEC-449c-9709-f90 e57 cd188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

一般需求、驗證、選擇性查詢參數、請求URL及其他參考的資訊。

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **請求參數：** 除非另行指定，否則需要所有請求參數。
* **[!DNL JSON]內容類型：** 指定 `content-type: application/json`*和*`accept: application/json` 在您的程式碼中。

* **要求與回應：** 將請求傳送為格式正確的 [!DNL JSON] 物件。[!DNL Audience Manager] 回應 [!DNL JSON] 格式資料。伺服器回應可以包含要求的資料、狀態代碼或兩者。

* **存取：**[!DNL Audience Manager] 您的顧問會提供客戶ID和金鑰，讓您 [!DNL API] 可以提出要求。

* **說明文件和程式碼範例：***斜體文字* 代表您在製作或接收 [!DNL API] 資料時提供或傳入的變數。Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. 未系結至特定員工的一般帳戶可協助您避免此問題。

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>如果您將Token儲存在資料庫中，請加密並重新整理Token。

### 步驟1：要求API存取

聯絡您的合作夥伴解決方案管理員。They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### 步驟2：要求Token

Pass in a token request with your preferred [!DNL JSON] client. 當您建立請求時：

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 將您的用戶端ID和密碼轉換為base-64編碼字串。在轉換程序期間使用冒號分隔ID和密碼。For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 設定請求主體如下：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### 步驟3：接收Token

[!DNL JSON] 回應包含您的存取Token。回應應該看起來像這樣：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` 索引鍵代表存取Token過期之前的秒數。最佳作法是使用簡短的過期時間，在Token公開時限制曝光度。

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. 如果您未收到重新整理Token，請透過密碼驗證程序建立新的Token。

您也可以使用重新整理Token，在現有存取Token過期之前產生新Token。

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### 步驟1：請求新Token

Pass in a refresh token request with your preferred [!DNL JSON] client. 當您建立請求時：

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* 將您的用戶端ID和密碼轉換為base-64編碼字串。在轉換程序期間使用冒號分隔ID和密碼。For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### 步驟2：接收新Token

[!DNL JSON] 回應包含您的新存取Token。回應應該看起來像這樣：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_贊_ this]
>
>* [OAuth2.0](https://oauth.net/2/)
>* [OAuth簡化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_贊_ this]
>
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

將可選參數設定為傳回物件所有屬性的方法。

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| 參數 | 說明 |
|--- |--- |
| 頁面 | 依頁碼傳回結果。編號開始於0。 |
| pageSize | 設定請求傳回的回應結果數(預設為10)。 |
| SortBy | Sorts and returns results according to the specified [!DNL JSON] property. |
| 遞減遞減 | 排序並傳回結果遞減順序。遞增是預設值。 |
| 搜尋 | 根據您要用作搜尋參數的指定字串傳回結果。例如，假設您想尋找所有該項目值欄位中字詞「Test」的所有模型的結果。Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  您可以搜尋「get all」方法傳回的任何值。 |
| FolderId | 傳回指定資料夾內特徵的所有ID。不適用於所有方法。 |
| 權限 | 根據指定的權限傳回區段清單。預設為READ。權限包括：<ul><li>`READ` ：傳回並檢視區段相關資訊。</li><li>`WRITE` ：用於 `PUT` 更新區段。</li><li>`CREATE` ：用於 `POST` 建立區段。</li><li>`DELETE` : 刪除區段. 需要存取基本特徵(如果有的話)。例如，如果您要移除區段，您將需要刪除屬於區段的特徵。</li></ul><br>指定具有個別索引鍵值配對的多個權限。For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includPermissions | (布林)設為true，以傳回區段的權限。設值為 false。 |

### 關於頁面選項的附註

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. 使用頁面選項的範例請求看起來類似下列：

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 請求、測試和生產環境以及版本。

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| 演算法模型 | `https://api.demdex.com/v1/models/` |
| 資料來源 | `https://api.demdex.com/v1/datasources/` |
| 衍生訊號 | `https://api.demdex.com/v1/signals/derived/` |
| 目的地 | `https://api.demdex.com/v1/destinations/` |
| 網域 | `https://api.demdex.com/v1/partner-sites/` |
| 資料夾 | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| 結構描述 | `https://api.demdex.com/v1/schemas/` |
| 區段 | `https://api.demdex.com/v1/segments/` |
| 特徵 | `https://api.demdex.com/v1/traits/` |
| 特徵類型 | `https://api.demdex.com/v1/customer-trait-types` |
| 分類法 | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. 這些環境可協助您對個別資料庫進行程式碼測試，而不會影響即時生產資料。The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| 環境 | 主機名稱 |
|---|---|
| **生產** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Audience Manager beta版環境是小型獨立版本的生產環境。您要測試的所有資料都必須在此環境中輸入並收集。

## 版本 {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` 狀態代碼和Audience Manager傳回的回應文字 [!UICONTROL REST API]。

<!-- r_api_http_response_codes.xml -->

| 回應代碼ID | 回應文字 | 定義 |
|---|---|---|
| 200 | OK | 請求已成功處理。視需要傳回預期的內容或資料。 |
| 201 | 已建立 | 資源已建立。Returns for `PUT` and `POST` requests. |
| 204 | 沒有內容 | 資源已刪除。回應主體將為空白。 |
| 400 | Bad Request | 伺服器不瞭解要求。通常因為語法錯誤。請檢查您的要求，然後再試一次。 |
| 403 | 禁止用途 | 您沒有資源的存取權。 |
| 404 | 找不到 | 找不到指定路徑的資源。 |
| 409 | 衝突 | 由於資源與資源的狀態衝突，所以無法完成請求。 |
| 500 | 伺服器錯誤 | 伺服器遇到未預期的錯誤，無法滿足要求。 |