---
description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-title: REST API 快速入門
solution: Audience Manager
title: REST API 快速入門
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---

# [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}快速入門

有關一般需求、驗證、選用查詢參數、要求[!DNL URLs]和其他參考的資訊。

<!-- c_rest_api_overview.xml -->

## API 需求與建議{#api-requirements-recommendations}

使用[!DNL Audience Manager] [!DNL API]s時，您必須且應該執行的操作。

<!-- aam-api-requirements.xml -->

使用[Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/)程式碼時，請注意下列事項：

* **請求參數：** 除非另有指定，否則所有請求參數都為必要。
* **要求標題**:使用 [AdobeI/](https://www.adobe.io/) Otoken時，您必須提供標 `x-api-key` 題。您可以依照[服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面中的指示，取得[!DNL API]金鑰。
* **[!DNL JSON]內容類型：** 在您 `content-type: application/json`  **  `accept: application/json` 的程式碼中指定和。
* **請求和回應：** 以格式正確的物件傳送 [!DNL JSON] 請求。[!DNL Audience Manager] 使用格式化 [!DNL JSON] 資料進行響應。伺服器回應可包含請求的資料、狀態代碼或兩者。
* **存取：** 您的 [!DNL Audience Manager] 顧問會提供您用戶端ID和金鑰，讓您提出 [!DNL API] 要求。
* **檔案和程式碼範例：** 斜體 ** 文字代表您在製作或接收資料時提供或傳入的 [!DNL API] 變數。將&#x200B;*斜體*&#x200B;文字取代為您自己的程式碼、參數或其他必要資訊。

## 驗證 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支援兩種驗證方法。

* [JWT（服務帳戶）](#jwt) 使用 [Adobe I/O](https://www.adobe.io/)。[!DNL Adobe I/O] 是Adobe的開發人員生態系統和社群。其中包含適用於所有Adobe產品](https://www.adobe.io/apis.html)的[Adobe I/O開發工具和API](https://www.adobe.io/apis/experienceplatform.html)及[API。 這是設定和使用[!DNL Adobe] [!DNL APIs]的建議方法。
* [OAuth驗證（已淘汰）](#oauth)。雖然此方法已遭取代，但現有[!DNL OAuth]整合的客戶可繼續使用此方法。

>[!IMPORTANT]
>
>您需要根據您的驗證方法調整請求[!DNL URLs]。 如需您應使用之主機名稱的詳細資訊，請參閱[環境](#environments)區段。

## [!DNL JWT] ([!DNL Service Account])使用Adobe I/O進行驗證 {#jwt}

### Adobe I/O概述 {#adobeio}

[!DNL Adobe I/O] 是Adobe的開發人員生態系統和社群。其中包含適用於所有Adobe產品](https://www.adobe.io/apis.html)的[Adobe I/O開發工具和API](https://www.adobe.io/apis/experienceplatform.html)及[API。

這是設定和使用[!DNL Adobe] [!DNL APIs]的建議方法。

### 必要條件 {#prerequisites}

在配置[!DNL JWT]身份驗證之前，請確保您有權訪問[Adobe I/O](https://www.adobe.io/)中的[Adobe開發人員控制台](https://console.adobe.io/)。 如需存取請求，請聯絡貴組織的管理員。

### 驗證 {#auth}

請依照下列步驟使用[!DNL Adobe I/O]配置[!DNL JWT (Service Account)]身份驗證：

1. 登入[Adobe開發人員控制台](https://console.adobe.io/)。
1. 按照[服務帳戶連接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步驟操作。
   * 在[步驟2:使用服務帳戶驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)新增API至您的專案，選擇[!DNL Audience Manager] [!DNL API]選項。
1. 根據[步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的指示發出第一個[!DNL API]呼叫，以嘗試連接。

>[!NOTE]
>
>要以自動方式配置和使用[!DNL Audience Manager] [!DNL REST APIs]，可以以程式設計方式生成[!DNL JWT]。 有關詳細說明，請參閱[JWT（服務帳戶）Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

## [!DNL OAuth] 驗證（已廢止） {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 代號驗證和透過的續 [!DNL OAuth 2.0] 約現已過時。
>
> 請改用[JWT（服務帳戶）Authentication](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循令牌驗證和續約的[!DNL OAuth 2.0]標準。 以下各節說明如何驗證和開始使用[!DNL API]s。

### 建立通用[!DNL API]用戶 {#requirements}

建議您建立個別的技術使用者帳戶，以搭配[!DNL Audience Manager] [!DNL API]s使用。這是一般帳戶，不會系結至組織中的特定使用者，或與其建立關聯。 此類型的[!DNL API]使用者帳戶可協助您完成下列兩件事：

* 識別呼叫[!DNL API]的服務（例如，來自使用[!DNL API]的應用程式或來自提出[!DNL API]請求的其他工具的呼叫）。
* 不間斷地訪問[!DNL API]s。與特定人員系結的帳戶可能會在他們離開您的公司時刪除。 這會阻止您使用可用的[!DNL API]代碼。 未與特定員工綁定的通用帳戶有助於您避免此問題。

以此類帳戶的範例或使用案例為例，假設您想使用[大量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次變更許多區段。 為此，您的用戶帳戶需要[!DNL API]訪問權限。 請建立非特定的[!DNL API]使用者帳戶，該帳戶具有進行[!DNL API]呼叫的適當憑證、金鑰和機密，而非將權限新增至特定使用者。 如果您開發自己的應用程式來使用[!DNL Audience Manager] [!DNL API]s，這也很有用。

與您的[!DNL Audience Manager]顧問合作，設定僅限[!DNL API]的一般使用者帳戶。

### 密碼驗證工作流{#password-authentication-workflow}

密碼身份驗證安全訪問我們的[!DNL REST API]。 以下步驟概述瀏覽器中[!DNL JSON]用戶端的密碼驗證工作流程。

>[!TIP]
>
>如果您將權杖儲存在資料庫中，請加密存取和重新整理權杖。

#### 步驟1:請求[!DNL API]訪問

請連絡您的合作夥伴解決方案經理。 它們會提供您[!DNL API]用戶端ID和密碼。 ID和機密會驗證您[!DNL API]。

注意：如果要接收刷新令牌，請在請求[!DNL API]訪問時指定。

#### 步驟2:要求Token

使用您慣用的[!DNL JSON]用戶端傳遞Token要求。 建置請求時：

* 使用`POST`方法呼叫`https://api.demdex.com/oauth/token`。
* 將用戶端ID和密碼轉換為base-64編碼字串。 在轉換過程中以冒號分隔ID和機密。 例如，憑據`testId : testSecret`轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded` 。 例如，標題可能如下所示：<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 設定要求內文，如下所示：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3:接收代號

[!DNL JSON]回應包含您的存取權杖。 回應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in`金鑰代表存取權杖過期前的秒數。 最佳作法是，如果代號曾公開，請使用短的到期時間來限制曝光。

### 重新整理Token {#refresh-token}

在原始Token過期後，重新整理Token會續訂[!DNL API]存取權。 如果請求，密碼工作流中的響應[!DNL JSON]將包括刷新令牌。 如果您未收到重新整理Token，請透過密碼驗證程式建立新Token。

您也可以使用重新整理Token，在現有存取Token過期之前產生新Token。

如果您的存取權杖已過期，您會在回應中收到`401 Status Code`和下列標題：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟概述使用重新整理Token，從瀏覽器的[!DNL JSON]用戶端建立新存取Token的工作流程。

#### 步驟1:請求新代號

使用您偏好的[!DNL JSON]用戶端傳遞重新整理Token請求。 建置請求時：

* 使用`POST`方法呼叫`https://api.demdex.com/oauth/token`。
* 將用戶端ID和密碼轉換為base-64編碼字串。 在轉換過程中以冒號分隔ID和機密。 例如，憑據`testId : testSecret`轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入HTTP標題`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，標題可能如下所示：<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在要求內文中，指定`grant_type:refresh_token` ，並傳入您先前存取要求中收到的重新整理Token。 請求應如下所示：<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2:接收新代號

[!DNL JSON]回應包含您的新存取權杖。 回應應如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授權碼和隱式驗證{#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支援授權碼和隱式驗證。 若要使用這些存取方法，您的使用者必須登入`https://api.demdex.com/oauth/authorize`才能取得存取權並重新整理權杖。

## 發出已驗證的[!DNL API]請求{#authenticated-api-requests}

在收到驗證Token後呼叫[!DNL API]方法的需求。

要對可用的[!DNL API]方法進行呼叫：

* 在`HTTP`標題中，設定`Authorization: Bearer <token>`。
* 使用[JWT（服務帳戶）Authentication](#jwt)時，您需要提供`x-api-key`標題，該標題與`client_id`相同。 您可以從[Adobe I/O整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面取得`client_id`。
* 呼叫所需的[!DNL API]方法。

## 可選[!DNL API]查詢參數{#optional-api-query-parameters}

設定可用於方法的可選參數，這些方法返回對象的所有屬性。

您可以將這些可選參數與[!DNL API]方法搭配使用，這些方法會傳回物件的&#x200B;*all*&#x200B;屬性。 將查詢傳遞至[!DNL API]時，請在要求字串中設定這些選項。

| 參數 | 說明 |
|--- |--- |
| `page` | 按頁碼返回結果。 編號從0開始。 |
| `pageSize` | 設定請求傳回的回應結果數（預設為10）。 |
| `sortBy` | 根據指定的[!DNL JSON]屬性對結果進行排序並返回。 |
| `descending` | 按降序排序和返回結果。 `ascending` 為預設值。 |
| `search` | 根據您要用作搜索參數的指定字串返回結果。 例如，假設您想在該項目的任何值欄位中，找到所有具有「Test」字詞之模型的結果。 您的範例要求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜尋「[!DNL get all]」方法傳回的任何值。 |
| `folderId` | 傳回指定資料夾內[!UICONTROL traits]的所有ID。 不適用於所有方法。 |
| `permissions` | 根據指定的權限傳回區段清單。 `READ` 為預設值。權限包括：<ul><li>`READ` :傳回和檢視區段的相關資訊。</li><li>`WRITE` :使  `PUT`  用更新區段。</li><li>`CREATE` :使  `POST`  用建立區段。</li><li>`DELETE` : 刪除區段. 需要存取基礎特徵（如果有）。 例如，如果您想要移除某個區段，則需要刪除該區段所屬特徵的權限。</li></ul><br>使用個別的索引鍵值配對指定多個權限。例如，若要僅傳回具有`READ`和`WRITE`權限的區段清單，請傳入`"permissions":"READ"`、`"permissions":"WRITE"` 。 |
| `includePermissions` | ([!DNL Boolean])設為`true`以傳回區段的權限。 預設為 `false`. |

### 關於頁面選項的附註

當頁面資訊&#x200B;*未指定*&#x200B;時，要求會傳回純[!DNL JSON]，結果為陣列。 如果指定了頁資訊&#x200B;**，則返回的清單將包裝在[!DNL JSON]對象中，該對象包含有關總結果和當前頁的資訊。 使用頁面選項的範例請求看起來可能類似這樣：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 適用於請求、測試和生產環境及版本。

## 請求 [!DNL URLs] {#request-urls}

下表列出用於傳遞[!DNL API]請求的請求[!DNL URLs]，依方法分列。

根據您使用的驗證方法，您需要根據下表調整請求[!DNL URLs]。

### [!DNL JWT]驗證{#request-urls-jwt}的請求[!DNL URLs]

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | 特徵： `https://aam.adobe.io/v1/folders/traits /`<br>區段： `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### [!DNL OAuth]驗證的請求[!DNL URLs]（已廢止）{#request-urls-oauth}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | 特徵： `https://api.demdex.com/v1/folders/traits /`<br>區段： `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

[!DNL Audience Manager] [!DNL API]s提供對不同工作環境的訪問。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時的生產資料。 下表列出可用的[!DNL API]環境和相應的資源主機名。

根據您使用的驗證方法，您需要根據下表調整環境[!DNL URLs]。

| 環境 | [!DNL JWT]驗證的主機名 | [!DNL OAuth]驗證的主機名 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager]測試版環境是生產環境的較小規模的獨立版本。 必須在此環境中輸入並收集您要測試的所有資料。

## 版本 {#versions}

這些[!DNL API]s的新版本會定期發行。 新版本會增加[!DNL API]版本號碼。 請求[!DNL URL]中參考的版本號碼為`v<version number>`，如下列範例所示：

`https://<host>/v1/...`

## 定義的響應代碼{#response-codes-defined}

`HTTP` 狀態代碼和由傳回的回應文 [!DNL Audience Manager] [!UICONTROL REST API]字。

| 回應代碼ID | 回應文字 | 定義 |
|---|---|---|
| `200` | `OK` | 已成功處理請求。 會視需要傳回預期的內容或資料。 |
| `201` | `Created` | 已建立資源。 傳回`PUT`和`POST`要求。 |
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
* [OAuth 2.0](https://oauth.net/2/)
* [OAuth 2簡化](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

