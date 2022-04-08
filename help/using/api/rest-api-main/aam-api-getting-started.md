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

# 入門 [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有關一般要求、驗證、可選查詢參數、請求的資訊 [!DNL URLs]、和其他引用。

<!-- c_rest_api_overview.xml -->

## API 需求與建議 {#api-requirements-recommendations}

與 [!DNL Audience Manager] [!DNL API]s

<!-- aam-api-requirements.xml -->

使用時請注意以下事項 [Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/) 代碼：

* **請求參數：** 除非另有指定，否則所有請求參數都是必需的。
* **請求標題**:使用 [Adobe開發人員](https://www.adobe.io/) 令牌，必須提供 `x-api-key` 標題。 你可以 [!DNL API] 按照 [服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 的子菜單。
* **[!DNL JSON]內容類型：** 指定 `content-type: application/json`  *和*  `accept: application/json` 你的密碼。
* **請求和響應：** 以格式正確的方式發送請求 [!DNL JSON] 的雙曲餘切值。 [!DNL Audience Manager] 響應 [!DNL JSON] 格式化資料。 伺服器響應可以包含請求的資料、狀態代碼或兩者。
* **訪問：** 您 [!DNL Audience Manager] 顧問將為您提供客戶端ID和密鑰，以便您 [!DNL API] 請求。
* **文檔和代碼示例：** 文本 *斜體* 表示在生成或接收時提供或傳遞的變數 [!DNL API] 資料。 替換 *斜體* 包含您自己的代碼、參數或其他必需資訊的文本。

## 驗證 {#authentication}

的 [!DNL Audience Manager] [!DNL REST APIs] 支援兩種驗證方法。

* [JWT（服務帳戶）身份驗證](#jwt) 使用 [Adobe開發人員](https://www.adobe.io/)。 [!DNL Adobe Developer] 是Adobe的開發者生態系統和社區。 包括 [所有Adobe產品的API](https://www.adobe.io/apis.html)。 這是設定和使用的推薦方法 [!DNL Adobe] [!DNL APIs]。
* [OAuth身份驗證（不建議使用）](#oauth)。 雖然此方法已棄用，但現有客戶 [!DNL OAuth] 整合可以繼續使用此方法。

>[!IMPORTANT]
>
>根據您的身份驗證方法，您需要調整請求 [!DNL URLs] 因此。 查看 [環境](#environments) 的子菜單。

## [!DNL JWT] ([!DNL Service Account])使用Adobe開發人員進行身份驗證 {#jwt}

### Adobe開發人員概述 {#adobeio}

[!DNL Adobe Developer] 是Adobe的開發者生態系統和社區。 包括 [所有Adobe產品的API](https://www.adobe.io/apis.html)。

這是設定和使用的推薦方法 [!DNL Adobe] [!DNL APIs]。

### 必要條件 {#prerequisites}

在配置之前 [!DNL JWT] 驗證，確保您有權訪問 [Adobe開發人員控制台](https://console.adobe.io/) 在 [Adobe開發人員](https://www.adobe.io/)。 請與組織管理員聯繫以獲取訪問請求。

### 驗證 {#auth}

按照以下步驟配置 [!DNL JWT (Service Account)] 驗證 [!DNL Adobe Developer]:

1. 登錄到 [Adobe開發人員控制台](https://console.adobe.io/)。
1. 按照中的步驟操作 [服務帳戶連接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。
   * 期間 [步驟2:使用服務帳戶驗證將API添加到項目](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)的子菜單。 [!DNL Audience Manager] [!DNL API] 的雙曲餘切值。
1. 首先嘗試連接 [!DNL API] 根據來自 [步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!NOTE]
>
>配置和使用 [!DNL Audience Manager] [!DNL REST APIs] 以自動方式生成 [!DNL JWT] 程式。 請參閱 [JWT（服務帳戶）身份驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) 的上界。

### 技術帳戶RBAC權限

如果您的Audience Manager帳戶使用 [基於角色的訪問控制](../../features/administration/administration-overview.md)，您必須建立Audience Manager技術用戶帳戶，並將其添加到Audience ManagerRBAC組中，該組將調用API。

按照以下步驟建立技術用戶帳戶並將其添加到RBAC組：

1. 製作 `GET` 呼叫 `https://aam.adobe.io/v1/users/self`。 該呼叫將建立您可以在 [!UICONTROL Admin Console]，也請參見Wiki頁。 [!UICONTROL Users] 的子菜單。

   ![技術帳戶](assets/technical-account.png)

1. 登錄到您的Audience Manager帳戶 [添加技術用戶帳戶](../../features/administration/administration-overview.md#create-group) 調用API的用戶組。

## [!DNL OAuth] 身份驗證（不建議使用） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 令牌認證和更新 [!DNL OAuth 2.0] 現在已棄用。
>
> 請使用 [JWT（服務帳戶）身份驗證](#jwt-service-account-authentication-jwt) 的雙曲餘切值。

的 [!DNL Audience Manager] [!UICONTROL REST API] 如下 [!DNL OAuth 2.0] 令牌驗證和續訂標準。 以下各節介紹如何驗證和開始使用 [!DNL API]s

### 建立泛型 [!DNL API] 用戶 {#requirements}

我們建議您建立一個單獨的技術用戶帳戶，以便使用 [!DNL Audience Manager] [!DNL API]s這是一個普通帳戶，它不與組織中的特定用戶關聯或關聯。 此類型 [!DNL API] 用戶帳戶可幫助您完成以下兩項任務：

* 確定呼叫的服務 [!DNL API] (例如，來自使用我們 [!DNL API]或來自其他工具 [!DNL API] 請求)。
* 提供對 [!DNL API]s與特定人員關聯的帳戶在離開公司時可能會被刪除。 這將阻止您使用可用 [!DNL API] 代碼。 不與特定員工關聯的通用帳戶有助於您避免此問題。

作為此類帳戶的示例或使用案例，假設您要同時使用 [批量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)。 為此，您的用戶帳戶需要 [!DNL API] 訪問。 不是向特定用戶添加權限，而是建立非特定用戶， [!DNL API] 具有相應憑據、密鑰和機密的用戶帳戶 [!DNL API] 呼叫。 如果您開發自己的應用程式，並使用 [!DNL Audience Manager] [!DNL API]s

與 [!DNL Audience Manager] 建立泛型， [!DNL API]-only用戶帳戶。

### 密碼驗證工作流 {#password-authentication-workflow}

密碼身份驗證安全訪問我們的 [!DNL REST API]。 以下步驟概述了來自 [!DNL JSON] 客戶端。

>[!TIP]
>
>如果將訪問和刷新令牌儲存在資料庫中，則加密它們。

#### 步驟1:請求 [!DNL API] 訪問

請與合作夥伴解決方案經理聯繫。 他們會給你 [!DNL API] 客戶端ID和密碼。 ID和機密將您驗證到 [!DNL API]。

注：如果要接收刷新令牌，請在請求時指定 [!DNL API] 訪問。

#### 步驟2:請求令牌

將令牌請求傳遞給您的首選 [!DNL JSON] 客戶端。 生成請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`。
* 將客戶端ID和機密轉換為base-64編碼字串。 在轉換過程中，用冒號分隔ID和機密。 例如，憑據 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入 [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` 。 例如，您的標題可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式設定請求正文：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 第3步：接收令牌

的 [!DNL JSON] 響應包含您的訪問令牌。 響應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

的 `expires_in` key表示在訪問令牌過期之前的秒數。 最佳做法是，在令牌暴露時使用較短的過期時間來限制暴露。

### 刷新令牌 {#refresh-token}

刷新令牌續訂 [!DNL API] 原始令牌過期後的訪問。 如果請求，響應 [!DNL JSON] 在密碼工作流中包括刷新標籤。 如果未收到刷新令牌，請通過密碼驗證過程建立新令牌。

您還可以使用刷新令牌在現有訪問令牌過期之前生成新令牌。

如果訪問令牌已過期，則您將收到 `401 Status Code` 以及響應中的以下標題：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

以下步驟概述了使用刷新令牌從 [!DNL JSON] 客戶端。

#### 步驟1:請求新令牌

使用首選項傳遞刷新令牌請求 [!DNL JSON] 客戶端。 生成請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`。
* 將客戶端ID和機密轉換為base-64編碼字串。 在轉換過程中，用冒號分隔ID和機密。 例如，憑據 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳遞HTTP標頭 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`。 例如，您的標題可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在請求正文中，指定 `grant_type:refresh_token` 並傳遞您先前訪問請求中收到的刷新令牌。 請求應如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2:接收新令牌

的 [!DNL JSON] 響應包含您的新訪問令牌。 響應應如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授權碼與隱式認證 {#authentication-code-implicit}

的 [!DNL Audience Manager] [!UICONTROL REST API] 支援授權碼和隱式身份驗證。 要使用這些訪問方法，您的用戶需要登錄到 `https://api.demdex.com/oauth/authorize` 獲取訪問和刷新令牌。

## 驗證 [!DNL API] 請求 {#authenticated-api-requests}

呼叫要求 [!DNL API] 方法。

針對可用的呼叫 [!DNL API] 方法：

* 在 `HTTP` 標題，設定 `Authorization: Bearer <token>`。
* 使用時 [JWT（服務帳戶）身份驗證](#jwt)，您需要提供 `x-api-key` 標題，與 `client_id`。 你可以 `client_id` 從 [Adobe開發人員整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 的子菜單。
* 呼叫所需 [!DNL API] 的雙曲餘切值。

## 可選 [!DNL API] 查詢參數 {#optional-api-query-parameters}

設定可用於返回對象所有屬性的方法的可選參數。

可將這些可選參數與 [!DNL API] 返回的方法 *全部* 對象的屬性。 將查詢傳遞到 [!DNL API]。

| 參數 | 說明 |
|--- |--- |
| `page` | 按頁碼返回結果。 編號從0開始。 |
| `pageSize` | 設定請求返回的響應結果數（預設值為10）。 |
| `sortBy` | 根據指定的 [!DNL JSON] 屬性。 |
| `descending` | 按降序排序並返回結果。 `ascending` 為預設值。 |
| `search` | 根據要用作搜索參數的指定字串返回結果。 例如，假設您要查找所有模型的結果，這些模型在該項目的任何值欄位中都使用「Test」一詞。 您的示例請求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  可以搜索「」返回的任何值[!DNL get all]」對話框。 |
| `folderId` | 返回的所有ID [!UICONTROL traits] 資料夾中。 並非所有方法都可用。 |
| `permissions` | 返回基於指定權限的段清單。 `READ` 為預設值。 權限包括：<ul><li>`READ` :返回並查看有關段的資訊。</li><li>`WRITE` :使用  `PUT`  更新段。</li><li>`CREATE` :使用  `POST`  的子菜單。</li><li>`DELETE` : 刪除區段. 需要訪問基礎特徵（如果有）。 例如，如果要刪除段，則需要刪除屬於段的特徵的權限。</li></ul><br>指定具有單獨鍵值對的多個權限。 例如，返回段清單  `READ`  和  `WRITE`  僅權限，傳入  `"permissions":"READ"`。 `"permissions":"WRITE"` 。 |
| `includePermissions` | ([!DNL Boolean])設定為 `true` 返回段的權限。 預設為 `false`. |

### 關於頁面選項的注釋

頁面資訊 *不是* 指定，請求返回純 [!DNL JSON] 結果。 如果頁面資訊 *是* 指定，則返回的清單將包裝在 [!DNL JSON] 包含有關總結果和當前頁面的資訊的對象。 使用頁面選項的示例請求可能與以下內容類似：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 請求、轉移和生產環境以及版本。

## 請求 [!DNL URLs] {#request-urls}

下表列出了請求 [!DNL URLs] 過去 [!DNL API] 請求，按方法。

根據您使用的驗證方法，您需要調整請求 [!DNL URLs] 按下表列出。

### 請求 [!DNL URLs] 為 [!DNL JWT] 驗證 {#request-urls-jwt}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://aam.adobe.io/v1/folders/traits /`<br>段：  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### 請求 [!DNL URLs] 為 [!DNL OAuth] 身份驗證（不建議使用） {#request-urls-oauth}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特徵：  `https://api.demdex.com/v1/folders/traits /`<br>段：  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

的 [!DNL Audience Manager] [!DNL API]提供對不同工作環境的訪問。 這些環境可幫助您針對不同的資料庫test代碼，而不會影響即時生產資料。 下表列出了 [!DNL API] 環境和相應的資源主機名。

根據您使用的驗證方法，您需要調整環境 [!DNL URLs] 下表所示。

| 環境 | 的主機名 [!DNL JWT] 認證 | 的主機名 [!DNL OAuth] 認證 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **β** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>的 [!DNL Audience Manager] beta環境是生產環境的較小規模的獨立版本。 必須在此環境中輸入和收集要test的所有資料。

## 版本 {#versions}

這些版本的新版本 [!DNL API]定期發放。 新版本將增加 [!DNL API] 版本號。 請求中引用了版本號 [!DNL URL] 如 `v<version number>` 如下例所示：

`https://<host>/v1/...`

## 已定義響應代碼 {#response-codes-defined}

`HTTP` 狀態代碼和由返回的響應文本 [!DNL Audience Manager] [!UICONTROL REST API]。

| 響應代碼ID | 響應文本 | 定義 |
|---|---|---|
| `200` | `OK` | 已成功處理請求。 如果需要，將返回預期內容或資料。 |
| `201` | `Created` | 已建立資源。 返回 `PUT` 和 `POST` 請求。 |
| `204` | `No Content` | 已刪除資源。 響應正文將為空。 |
| `400` | `Bad Request` | 伺服器未理解請求。 通常是由於語法格式不正確。 請檢查您的請求，然後重試。 |
| `403` | `Forbidden` | 您無權訪問資源。 |
| `404` | `Not Found` | 找不到指定路徑的資源。 |
| `409` | `Conflict` | 由於與資源狀態衝突，無法完成請求。 |
| `500` | `Server Error` | 伺服器遇到錯誤，導致無法完成請求。 |

>[!MORELIKETHIS]
>
>* [JWT（服務帳戶）身份驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth身份驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2簡化版](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

