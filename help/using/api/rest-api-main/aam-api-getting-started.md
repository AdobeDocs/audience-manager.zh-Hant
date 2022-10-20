---
description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: REST API 快速入門
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 3%

---

# 開始使用 [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有關一般需求、驗證、可選查詢參數、請求的資訊 [!DNL URLs]和其他參考。

<!-- c_rest_api_overview.xml -->

## API 需求與建議 {#api-requirements-recommendations}

使用時，您必須且應該執行的事項 [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

使用時請注意下列事項 [Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/) 代碼：

* **要求參數：** 除非另有指定，否則所有要求參數都是必要的。
* **要求標題**:使用 [Adobe Developer](https://www.adobe.io/) 代號，您必須提供 `x-api-key` 頁首。 你可以 [!DNL API] 鍵 [服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 頁面。
* **[!DNL JSON]內容類型：** 指定 `content-type: application/json`  *和*  `accept: application/json` 在程式碼中。
* **請求和回應：** 以格式正確的方式傳送請求 [!DNL JSON] 物件。 [!DNL Audience Manager] 回應 [!DNL JSON] 格式化資料。 伺服器回應可包含請求的資料、狀態代碼或兩者。
* **訪問：** 您的 [!DNL Audience Manager] 顧問會提供您用戶端ID和金鑰，讓您 [!DNL API] 要求。
* **檔案和程式碼範例：** 中的文字 *斜體* 代表您在產生或接收時提供或傳入的變數 [!DNL API] 資料。 取代 *斜體* 使用您自己的程式碼、參數或其他必要資訊的文字。

## 驗證 {#authentication}

此 [!DNL Audience Manager] [!DNL REST APIs] 支援兩種驗證方法。

* [JWT（服務帳戶）驗證](#jwt) 使用 [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] 是Adobe的開發人員生態系統和社群。 包括 [所有Adobe產品的API](https://www.adobe.io/apis.html). 這是設定和使用的建議方式 [!DNL Adobe] [!DNL APIs].
* [OAuth驗證（已廢止）](#oauth). 雖然此方法已淘汰，但現有的客戶 [!DNL OAuth] 整合可繼續使用此方法。

>[!IMPORTANT]
>
>您需要根據驗證方法調整請求 [!DNL URLs] 因此。 請參閱 [環境](#environments) 一節，以取得您應使用之主機名稱的詳細資訊。

## [!DNL JWT] ([!DNL Service Account])使用Adobe Developer進行驗證 {#jwt}

### Adobe Developer概述 {#adobeio}

[!DNL Adobe Developer] 是Adobe的開發人員生態系統和社群。 包括 [所有Adobe產品的API](https://www.adobe.io/apis.html).

這是設定和使用的建議方式 [!DNL Adobe] [!DNL APIs].

### 必要條件 {#prerequisites}

設定之前 [!DNL JWT] 驗證，確定您擁有 [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). 如需存取請求，請聯絡貴組織的管理員。

### 驗證 {#auth}

請依照下列步驟來設定 [!DNL JWT (Service Account)] 驗證使用 [!DNL Adobe Developer]:

1. 登入 [Adobe Developer Console](https://console.adobe.io/).
1. 請依照 [服務帳戶連接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * 期間 [步驟2:使用服務帳戶驗證將API新增至您的專案](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)，選擇 [!DNL Audience Manager] [!DNL API] 選項。
1. 請先嘗試連接 [!DNL API] 根據 [步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>若要設定及使用 [!DNL Audience Manager] [!DNL REST APIs] 您可以自動產生 [!DNL JWT] 程式設計。 請參閱 [JWT（服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 以取得詳細指示。

### 技術帳戶RBAC權限

如果您的Audience Manager帳戶使用 [角色型存取控制](../../features/administration/administration-overview.md)，您必須建立Audience Manager技術使用者帳戶，並將其新增至將進行API呼叫的Audience ManagerRBAC群組。

請依照下列步驟建立技術使用者帳戶，並將其新增至RBAC群組：

1. 建立 `GET` 呼叫 `https://aam.adobe.io/v1/users/self`. 此呼叫將建立技術使用者帳戶，您可在 [!UICONTROL Admin Console]，在 [!UICONTROL Users] 頁面。

   ![技術帳戶](assets/technical-account.png)

1. 登入您的Audience Manager帳戶，並 [新增技術使用者帳戶](../../features/administration/administration-overview.md#create-group) 至將進行API呼叫的使用者群組。

## [!DNL OAuth] 驗證（已廢止） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 代號驗證和續約，透過 [!DNL OAuth 2.0] 現已過時。
>
> 請使用 [JWT（服務帳戶）驗證](#jwt-service-account-authentication-jwt) 。

此 [!DNL Audience Manager] [!UICONTROL REST API] 如下 [!DNL OAuth 2.0] 代號驗證和續約的標準。 以下各節說明如何驗證及開始使用 [!DNL API]s.

### 建立通用 [!DNL API] 使用者 {#requirements}

建議您建立個別的技術使用者帳戶，以搭配 [!DNL Audience Manager] [!DNL API]s.這是一般帳戶，不會系結至組織中的特定使用者，或與其建立關聯。 此類 [!DNL API] 使用者帳戶可協助您完成下列兩件事：

* 識別呼叫的服務 [!DNL API] (例如，來自您使用 [!DNL API]或來自其他製造 [!DNL API] 要求)。
* 提供對 [!DNL API]s.與特定人員系結的帳戶可能會在他們離開您的公司時刪除。 這會使您無法使用可用的 [!DNL API] 程式碼。 未與特定員工綁定的通用帳戶有助於您避免此問題。

作為此類帳戶的範例或使用案例，假設您想要使用 [大量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md). 為此，您的使用者帳戶需要 [!DNL API] 存取權。 建立非特定的、 [!DNL API] 具有可建立的適當憑證、金鑰和機密的使用者帳戶 [!DNL API] 呼叫。 如果您開發的應用程式使用 [!DNL Audience Manager] [!DNL API]s.

與您的 [!DNL Audience Manager] 顧問來設定通用， [!DNL API] — 僅限用戶帳戶。

### 密碼驗證工作流程 {#password-authentication-workflow}

密碼驗證安全訪問我們的 [!DNL REST API]. 下列步驟將概述密碼驗證的工作流程，來自 [!DNL JSON] 用戶端。

>[!TIP]
>
>如果您將權杖儲存在資料庫中，請加密存取和重新整理權杖。

#### 步驟1:要求 [!DNL API] 存取

請連絡您的合作夥伴解決方案經理。 他們會提供 [!DNL API] 用戶端ID和密碼。 ID和機密會驗證您 [!DNL API].

注意：如果您想要接收重新整理Token，請在您提出要求時指定 [!DNL API] 存取權。

#### 步驟2:要求Token

使用您偏好的傳遞Token要求 [!DNL JSON] 用戶端。 建置請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`.
* 將用戶端ID和密碼轉換為base-64編碼字串。 在轉換過程中以冒號分隔ID和機密。 例如，憑證 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 傳入 [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` . 例如，標題可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 設定要求內文，如下所示：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3:接收代號

此 [!DNL JSON] 回應包含您的存取權杖。 回應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

此 `expires_in` key代表存取權杖過期的秒數。 最佳作法是，如果代號曾公開，請使用短的到期時間來限制曝光。

### 重新整理Token {#refresh-token}

重新整理代號續約 [!DNL API] 原始代號過期後的存取。 如有要求，則回應 [!DNL JSON] 在密碼工作流程中包含重新整理Token。 如果您未收到重新整理Token，請透過密碼驗證程式建立新Token。

您也可以使用重新整理Token，在現有存取Token過期之前產生新Token。

如果您的存取權杖已過期，您會收到 `401 Status Code` 和回應中的下列標題：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟將概述使用重新整理Token，以從 [!DNL JSON] 用戶端。

#### 步驟1:請求新代號

使用您偏好的傳遞重新整理Token請求 [!DNL JSON] 用戶端。 建置請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`.
* 將用戶端ID和密碼轉換為base-64編碼字串。 在轉換過程中以冒號分隔ID和機密。 例如，憑證 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`.
* 傳入HTTP標題 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`. 例如，標題可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在請求內文中，指定 `grant_type:refresh_token` 並傳入您先前存取請求中收到的重新整理Token。 請求應如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2:接收新代號

此 [!DNL JSON] 回應包含您的新存取權杖。 回應應如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授權碼與隱式驗證 {#authentication-code-implicit}

此 [!DNL Audience Manager] [!UICONTROL REST API] 支援授權碼和隱式驗證。 若要使用這些存取方法，您的使用者必須登入 `https://api.demdex.com/oauth/authorize` 以取得存取權並重新整理權杖。

## 驗證 [!DNL API] 請求 {#authenticated-api-requests}

呼叫需求 [!DNL API] 方法。

對可用進行呼叫的方式 [!DNL API] 方法：

* 在 `HTTP` 標題，設定 `Authorization: Bearer <token>`.
* 使用時 [JWT（服務帳戶）驗證](#jwt)，您必須提供 `x-api-key` 標題，其與 `client_id`. 你可以 `client_id` 從 [Adobe Developer整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 頁面。
* 呼叫必要 [!DNL API] 方法。

## 可選 [!DNL API] 查詢參數 {#optional-api-query-parameters}

設定可用於方法的可選參數，這些方法將返回對象的所有屬性。

您可以搭配使用這些選用參數 [!DNL API] 傳回的方法 *all* 對象的屬性。 將查詢傳入至 [!DNL API].

| 參數 | 說明 |
|--- |--- |
| `page` | 按頁碼返回結果。 編號從0開始。 |
| `pageSize` | 設定請求傳回的回應結果數（預設為10）。 |
| `sortBy` | 根據指定的 [!DNL JSON] 屬性。 |
| `descending` | 按降序排序和返回結果。 `ascending` 為預設值。 |
| `search` | 根據您要用作搜索參數的指定字串返回結果。 例如，假設您想在該項目的任何值欄位中，找到所有具有「Test」字詞之模型的結果。 您的範例要求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`.  您可以搜尋「[!DNL get all]」方法。 |
| `folderId` | 傳回 [!UICONTROL traits] 在指定的資料夾內。 不適用於所有方法。 |
| `permissions` | 根據指定的權限傳回區段清單。 `READ` 為預設值。 權限包括：<ul><li>`READ` :傳回和檢視區段的相關資訊。</li><li>`WRITE` :使用  `PUT`  以更新區段。</li><li>`CREATE` :使用  `POST`  來建立區段。</li><li>`DELETE` : 刪除區段. 需要存取基礎特徵（如果有）。 例如，如果您想要移除某個區段，則需要刪除該區段所屬特徵的權限。</li></ul><br>使用個別的索引鍵值配對指定多個權限。 例如，若要傳回具有  `READ`  和  `WRITE`  僅限權限，傳入  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean])設為 `true` 以傳回區段的權限。 預設為 `false`. |

### 關於頁面選項的附註

頁面資訊時 *不是* 指定，則請求會傳回純 [!DNL JSON] 產生陣列。 如果頁面資訊 *is* 指定，則傳回的清單會包裝在 [!DNL JSON] 包含總結果和當前頁資訊的對象。 使用頁面選項的範例請求看起來可能類似這樣：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 適用於請求、測試和生產環境及版本。

## 請求 [!DNL URLs] {#request-urls}

下表列出請求 [!DNL URLs] 過去傳入 [!DNL API] 請求，依方法。

您需要根據您使用的驗證方法調整請求 [!DNL URLs] 根據下表。

### 要求 [!DNL URLs] for [!DNL JWT] 驗證 {#request-urls-jwt}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://aam.adobe.io/v1/folders/traits /`<br>區段：  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 要求 [!DNL URLs] for [!DNL OAuth] 驗證（已廢止） {#request-urls-oauth}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://api.demdex.com/v1/folders/traits /`<br>區段：  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

此 [!DNL Audience Manager] [!DNL API]提供對不同工作環境的存取。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時的生產資料。 下表列出可用 [!DNL API] 環境和對應的資源主機名。

您需要根據您使用的驗證方法調整環境 [!DNL URLs] 根據下表。

| 環境 | 的主機名 [!DNL JWT] 驗證 | 的主機名 [!DNL OAuth] 驗證 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>此 [!DNL Audience Manager] 測試版環境是生產環境的較小規模的獨立版本。 必須在此環境中輸入並收集您要測試的所有資料。

## 版本 {#versions}

新版本 [!DNL API]會定期發行。 新發行將 [!DNL API] 版本號。 請求中參考的版本編號 [!DNL URL] as `v<version number>` 如下列範例所示：

`https://<host>/v1/...`

## 已定義的回應代碼 {#response-codes-defined}

`HTTP` 狀態代碼和由返回的響應文本 [!DNL Audience Manager] [!UICONTROL REST API].

| 回應代碼ID | 回應文字 | 定義 |
|---|---|---|
| `200` | `OK` | 已成功處理請求。 會視需要傳回預期的內容或資料。 |
| `201` | `Created` | 已建立資源。 傳回 `PUT` 和 `POST` 要求。 |
| `204` | `No Content` | 已刪除資源。 回應內文將為空白。 |
| `400` | `Bad Request` | 伺服器不理解該請求。 通常是因為語法格式不正確。 請檢查您的請求，然後重試。 |
| `403` | `Forbidden` | 您沒有資源的存取權。 |
| `404` | `Not Found` | 找不到指定路徑的資源。 |
| `409` | `Conflict` | 由於與資源狀態衝突，無法完成請求。 |
| `500` | `Server Error` | 伺服器遇到錯誤，使其無法完成請求。 |

>[!MORELIKETHIS]
>
>* [JWT（服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2簡化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

