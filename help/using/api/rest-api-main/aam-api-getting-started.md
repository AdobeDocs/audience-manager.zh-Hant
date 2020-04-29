---
description: 有關一般需求、驗證、選用查詢參數、請求URL和其他參考的資訊。
seo-description: 有關一般需求、驗證、選用查詢參數、請求URL和其他參考的資訊。
seo-title: REST API快速入門
solution: Audience Manager
title: REST API快速入門
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: 1bbfa4b537a344d58f20763bb40ebe0827ad8698

---


# REST API快速入門 {#getting-started-with-rest-apis}

有關一般需求、驗證、選用查詢參數、請求URL和其他參考的資訊。

<!-- c_rest_api_overview.xml -->

## API需求與建議 {#api-requirements-recommendations}

使用Audience Manager時，您必須且應做的 [!DNL API]事。

<!-- aam-api-requirements.xml -->

使用 [Audience Manager API程式碼時請注意](https://bank.demdex.com/portal/swagger/index.html#/) :

* **請求參數：** 除非另有指定，否則所有請求參數都是必要的。
* **請求標題**:使用 [Adobe I/O Token時](https://www.adobe.io/) ，您必須提供標 `x-api-key` 題。 您可依照「服務帳戶整合」頁面中的指示，取 [得您的API金鑰](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* **[!DNL JSON]內容類型：**在程`content-type: application/json`式碼&#x200B;*中指*`accept: application/json`定和指定。

* **要求與回應：** 以格式正確的物件傳送 [!DNL JSON] 請求。 [!DNL Audience Manager] 以格式化資 [!DNL JSON] 料回應。 伺服器回應可包含要求的資料、狀態碼或兩者。

* **存取：** 您的 [!DNL Audience Manager] 顧問會提供您用戶端ID和金鑰，讓您提出 [!DNL API] 要求。

* **檔案和程式碼範例：** 斜體 *文字* ，代表您在製作或接收資料時提供或傳入的變 [!DNL API] 數。 以您 *自己的程式碼* 、參數或其他必要資訊取代斜體文字。

## 驗證 {#authentication}

Audience Manager REST API支援兩種驗證方法。

* [JWT（服務帳戶）驗證](#jwt)。 這是建議的驗證方法。
* [OAuth驗證（已過時）](#oauth)。 雖然此方法已不再提倡，但具有現有OAuth整合的客戶仍可繼續使用此方法。

>[!IMPORTANT]
>
>視您的驗證方法而定，您需要相應調整您的請求URL。 有關應 [使用的主機名](#environments) ，請參見「環境」部分。

## JWT（服務帳戶）驗證 {#jwt}

若要建立安全的服務對服務Adobe I/O API作業，您必須建立JSON網頁Token(JWT)，以封裝整合的身分，然後交換它以取用Token。 每次向Adobe服務提出要求時，都必須在「授權」標題中包含存取Token，以及您在 [Adobe I/O主控台中建立「服務帳戶整合」時產生的API金鑰（用戶端ID）](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)[](https://console.adobe.io/)。

有關如 [何配置身份驗證的詳細說明](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) ，請參閱JWT（服務帳戶）身份驗證。

## OAuth驗證（已過時） {#oauth}

>[!WARNING]
> Audience Manager代 [!UICONTROL REST API] 號驗證和透過續約的 [!DNL OAuth 2.0] 功能現已過時。
>
> 請改用 [JWT（服務帳戶）驗證](#jwt-service-account-authentication-jwt) 。

Audience Manager遵循 [!UICONTROL REST API] 代號驗 [!DNL OAuth 2.0] 證和續約的標準。 以下各節將說明如何驗證並開始使用 [!DNL API]。

### 建立一般API使用者 {#requirements}

我們建議您建立個別的技術使用者帳戶，以便使用Audience Manager [!DNL API]。這是一般帳戶，不會系結至您組織中的特定使用者或與其關聯。 此類型的使 [!DNL API] 用者帳戶可協助您完成2項工作：

* 識別呼叫的服務 [!DNL API] (例如，來自使用我們的應用程式或提出請 [!DNL API]求的其他工具的呼 [!DNL API] 叫)。
* 不間斷地存取 [!DNL API]s。當系結至特定人員的帳戶離開您的公司時，可能會將其刪除。 這會使您無法使用可用的程 [!DNL API] 式碼。 未系結至特定員工的一般帳戶可協助您避免此問題。

舉例來說，假設您想要使用批量管理工具一次變更許多區段，或是用於此類型 [的帳戶](../../reference/bulk-management-tools/bulk-management-intro.md)。 為此，您的使用者帳戶需要存 [!DNL API] 取權。 請建立非特定的使用者帳戶，該帳戶具有適當的認證、金鑰 [!DNL API] 和密碼，以進行呼叫，而不是新增權限給特定 [!DNL API] 使用者。 如果您開發使用Audience Manager的自己應用程式，這也會很有 [!DNL API]用。

與您的Audience Manager顧問合作，以設定一般、僅 [!DNL API]限使用者帳戶。

### 密碼驗證工作流程 {#password-authentication-workflow}

<!-- oath-authentication.xml -->

密碼驗證安全存取我們 [!DNL REST API]的。 以下步驟概述瀏覽器中用戶端密碼驗 [!DNL JSON] 證的工作流程。

>[!TIP]
>
>如果將存取和重新整理Token儲存在資料庫中，請加密這些Token。

#### 步驟1:請求API存取

請洽詢您的合作夥伴解決方案經理。 他們會提供您用戶端 [!DNL API] ID和機密。 ID和機密會向驗證您身分 [!DNL API]。

注意：如果您想要接收重新整理Token，請在您要求存取時指 [!DNL API] 定。

#### 步驟2:請求代號

將Token請求傳入您偏好的用戶 [!DNL JSON] 端。 建立請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`。
* 將您的用戶端ID和密碼轉換為基本64編碼字串。 在轉換程式中，以冒號分隔ID和密碼。 例如，憑證會 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入頁 [!DNL HTTP] 首 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded` 。 例如，您的標題可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式設定請求正文：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3:接收Token

回應 [!DNL JSON] 包含您的存取Token。 回應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

金 `expires_in` 鑰代表存取Token過期前的秒數。 最佳實務是，使用較短的過期時間，在代號曝光時限制曝光。

### 重新整理Token {#refresh-token}

重新整理Token, [!DNL API] 在原始Token過期後續約存取權。 如果請求，密碼工作 [!DNL JSON] 流中的響應包括刷新令牌。 如果您未收到重新整理Token，請透過密碼驗證程式建立新Token。

您也可以使用重新整理Token，在現有存取Token過期之前產生新Token。

如果您的存取Token已過期，您會在回 `401 Status Code` 應中收到下列標題：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟概述使用重新整理Token從瀏覽器用戶端建立新存取Token [!DNL JSON] 的工作流程。

#### 步驟1:請求新Token

將重新整理Token請求傳入您偏好的用 [!DNL JSON] 戶端。 建立請求時：

* 使用 `POST` 呼叫方法 `https://api.demdex.com/oauth/token`。
* 將您的用戶端ID和密碼轉換為基本64編碼字串。 在轉換程式中，以冒號分隔ID和密碼。 例如，憑證會 `testId : testSecret` 轉換為 `dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入HTTP標題 `Authorization:Basic <base-64 clientID:clientSecret>` 和 `Content-Type: application/x-www-form-urlencoded`。 例如，您的標題可能如下所示： <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* 在請求內文中，指定 `grant_type:refresh_token` 並傳入您先前存取請求中收到的重新整理Token。 請求應如下所示： <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2:接收新Token

回 [!DNL JSON] 應包含您的新存取Token。 回應應如下所示：

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

Audience Manager支援授 [!UICONTROL REST API] 權碼和隱式驗證。 若要使用這些存取方法，您的使用者必須登入才能取 `https://api.demdex.com/oauth/authorize` 得存取和重新整理Token。

## 發出驗證的API請求 {#authenticated-api-requests}

在您收到驗 [!DNL API] 證Token後呼叫方法的要求。

<!-- c_oauth_call_methods.xml -->

若要對可用方法進行呼 [!DNL API] 叫：

* 在標題 `HTTP` 中，設定 `Authorization: Bearer <token>`。
* 使用 [JWT（服務帳戶）驗證](#jwt)，您需要提供與 `x-api-key` 您相同的標頭 `client_id`。 您可從 `client_id`[Adobe I/O整合頁面取得](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) 。
* 呼叫所需 [!DNL API] 方法。

## 可選API查詢參數 {#optional-api-query-parameters}

設定可用於返回對象所有屬性的方法的可選參數。

<!-- c_rest_api_optional.xml -->

您可將這些可選參數與傳 [!DNL API] 回物件所 *有屬性* 的方法搭配使用。 將查詢傳入請求字串中時，請在請求字串中設定這些選項 [!DNL API]。

| 參數 | 說明 |
|--- |--- |
| 頁面 | 依頁碼傳回結果。 編號從0開始。 |
| pageSize | 設定請求傳回的回應結果數目（預設為10）。 |
| sortBy | 根據指定的屬性排序並返回 [!DNL JSON] 結果。 |
| 降序 | 以遞減順序排序和傳回結果。 預設為遞增。 |
| 搜尋 | 根據您要用作搜尋參數的指定字串傳回結果。 例如，假設您想要在該項目的任何值欄位中，尋找具有「測試」字詞的所有模型的結果。 您的範例要求可能如下所示：  `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜尋「get all」方法傳回的任何值。 |
| folderId | 傳回指定資料夾內特徵的所有ID。 並非所有方法都適用。 |
| 權限 | 根據指定的權限傳回區段清單。  READ為預設值。 權限包括：<ul><li>`READ` :傳回並檢視區段的相關資訊。</li><li>`WRITE` :使用 `PUT` 來更新區段。</li><li>`CREATE` :用 `POST` 來建立區段。</li><li>`DELETE` : 刪除區段. 需要存取基本特徵（如果有）。 例如，若您要移除屬於某個群體的特徵，您需要有權利加以刪除。</li></ul><br>使用個別的索引鍵值配對指定多個權限。 例如，若要傳回僅具有和權限的 `READ` 區 `WRITE` 段清單，請傳入 `"permissions":"READ"`、 `"permissions":"WRITE"` 。 |
| includePermissions | （布林值）設為true可傳回區段的權限。 設值為 false。 |

### 關於頁面選項的附註

未指定頁 *面資訊* ，請求會傳回純 [!DNL JSON] 結果為陣列。 如果指定 *了頁面資訊* ，則傳回的清單會包裝在物件中，該物件包含 [!DNL JSON] 關於總結果和目前頁面的資訊。 您使用頁面選項的範例要求看起來可能類似下列：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] 請求、測試和生產環境以及版本。

<!-- r_rest_urls.xml -->

## 請求URL {#request-urls}

下表依方法列出用來傳入請求 [!DNL API] 的請求URL。

根據您使用的驗證方法，您必鬚根據下表調整請求URL。

### 請求JWT驗證的URL {#request-urls-jwt}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| 演算法模型 | `https://aam.adobe.io/v1/models/` |
| 資料來源 | `https://aam.adobe.io/v1/datasources/` |
| 衍生信號 | `https://aam.adobe.io/v1/signals/derived/` |
| 目的地 | `https://aam.adobe.io/v1/destinations/` |
| 網域 | `https://aam.adobe.io/v1/partner-sites/` |
| 資料夾 | 特徵： 區 `https://aam.adobe.io/v1/folders/traits /`<br>段：  `https://aam.adobe.io/v1/folders/segments /` |
| 架構 | `https://aam.adobe.io/v1/schemas/` |
| 區段 | `https://aam.adobe.io/v1/segments/` |
| 特徵 | `https://aam.adobe.io/v1/traits/` |
| 特徵類型 | `https://aam.adobe.io/v1/customer-trait-types` |
| 分類法 | `https://aam.adobe.io/v1/taxonomies/0/` |

### 申請OAuth驗證的URL（已過時） {#request-urls-oauth}

| [!DNL API] 方法 | 請求 [!DNL URL] |
|--- |--- |
| 演算法模型 | `https://api.demdex.com/v1/models/` |
| 資料來源 | `https://api.demdex.com/v1/datasources/` |
| 衍生信號 | `https://api.demdex.com/v1/signals/derived/` |
| 目的地 | `https://api.demdex.com/v1/destinations/` |
| 網域 | `https://api.demdex.com/v1/partner-sites/` |
| 資料夾 | 特徵： 區 `https://api.demdex.com/v1/folders/traits /`<br>段：  `https://api.demdex.com/v1/folders/segments /` |
| 架構 | `https://api.demdex.com/v1/schemas/` |
| 區段 | `https://api.demdex.com/v1/segments/` |
| 特徵 | `https://api.demdex.com/v1/traits/` |
| 特徵類型 | `https://api.demdex.com/v1/customer-trait-types` |
| 分類法 | `https://api.demdex.com/v1/taxonomies/0/` |

## 環境 {#environments}

這些 [!DNL Audience Manager] 功能 [!DNL API]可讓您存取不同的工作環境。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時的生產資料。 下表列出了可用環境 [!DNL API] 和相應的資源主機名。

根據您使用的驗證方法，您需要根據下表調整您的環境URL。

| 環境 | JWT驗證的主機名 | OAuth驗證的主機名稱 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **測試版** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |


>[!NOTE]
>
>Audience Manager測試版環境是生產環境的小型獨立版。 您必須在此環境中輸入並收集您要測試的所有資料。

## 版本 {#versions}

這些新版 [!DNL API]本會定期發行。 新版本會增加版 [!DNL API] 本號。 請求URL中參考版本號碼，如 `v<version number>` 下列範例所示：

`https://<host>/v1/...`

## 已定義響應代碼 {#response-codes-defined}

`HTTP` 狀態代碼和Audience Manager傳回的回應文字 [!UICONTROL REST API]。

<!-- r_api_http_response_codes.xml -->

| 回應碼ID | 回應文字 | 定義 |
|---|---|---|
| 200 | OK | 請求已成功處理。 將視需要傳回預期的內容或資料。 |
| 201 | 已建立 | 已建立資源。 傳回 `PUT` 和請 `POST` 求。 |
| 204 | 沒有內容 | 已刪除資源。 回應主體將為空。 |
| 400 | Bad Request | 伺服器不瞭解請求。 通常是由於語法格式錯誤所致。 請檢查您的要求，然後再試一次。 |
| 403 | 禁止 | 您沒有資源的存取權。 |
| 404 | 找不到 | 找不到指定路徑的資源。 |
| 409 | 衝突 | 由於資源狀態衝突，無法完成請求。 |
| 500 | 伺服器錯誤 | 伺服器遇到意外錯誤，無法完成請求。 |

>[!MORELIKETHIS]
>
>* [JWT（服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2簡化版](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

