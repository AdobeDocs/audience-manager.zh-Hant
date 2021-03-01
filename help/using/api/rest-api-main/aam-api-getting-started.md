---
description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-title: REST API 快速入門
solution: Audience Manager
title: REST API 快速入門
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---


# 開始使用[!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

有關一般需求、驗證、可選查詢參數、請求[!DNL URLs]和其他參考的資訊。

<!-- c_rest_api_overview.xml -->

## API 需求與建議{#api-requirements-recommendations}

使用[!DNL Audience Manager] [!DNL API]時，您必須且應該執行的操作。

<!-- aam-api-requirements.xml -->

使用[Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/)代碼時，請注意以下事項：

* **請求參數：除** 非另有指定，否則所有請求參數都是必要的。
* **請求標題**:使用 [AdobeI/](https://www.adobe.io/) Otoken時，您必須提供 `x-api-key` 標題。您可依照[服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面中的指示，取得[!DNL API]金鑰。
* **[!DNL JSON]內容類型：** 指定 `content-type: application/json`  **  `accept: application/json` 並在程式碼中。
* **請求和回應：以** 正確格式化的物件傳送 [!DNL JSON] 請求。[!DNL Audience Manager] 以格式化 [!DNL JSON] 資料回應。伺服器回應可包含要求的資料、狀態碼或兩者。
* **存取：** 您的 [!DNL Audience Manager] 顧問會提供您用戶端ID和金鑰，讓您提出 [!DNL API] 要求。
* **檔案和程式碼範例：** 斜體 ** 文字代表您在製作或接收資料時提供或傳入的 [!DNL API] 變數。以您自己的程式碼、參數或其他必要資訊取代&#x200B;*斜體*&#x200B;文字。

## 驗證{#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支援兩種驗證方法。

* [JWT（服務帳戶）](#jwt) 驗證 [Adobe I/O](https://www.adobe.io/)。[!DNL Adobe I/O] 是Adobe的開發人員生態系統和社群。它包含[Adobe I/O開發人員工具，以及所有Adobe產品的](https://www.adobe.io/apis/experienceplatform.html)和[API。 ](https://www.adobe.io/apis.html)這是設定和使用[!DNL Adobe] [!DNL APIs]的建議方式。
* [OAuth驗證（已過時）](#oauth)。雖然此方法已不再提倡，但具有現有[!DNL OAuth]整合的客戶仍可繼續使用此方法。

>[!IMPORTANT]
>
>根據您的驗證方法，您需要相應調整請求[!DNL URLs]。 有關您應使用的主機名的詳細資訊，請參見[Environments](#environments)部分。

## [!DNL JWT] ([!DNL Service Account])使用Adobe I/O的驗證  {#jwt}

### Adobe I/O概述{#adobeio}

[!DNL Adobe I/O] 是Adobe的開發人員生態系統和社群。它包含[Adobe I/O開發人員工具，以及所有Adobe產品的](https://www.adobe.io/apis/experienceplatform.html)和[API。](https://www.adobe.io/apis.html)

這是設定和使用[!DNL Adobe] [!DNL APIs]的建議方式。

### 必要條件 {#prerequisites}

在配置[!DNL JWT]驗證之前，請務必存取[Adobe](https://www.adobe.io/)中的[Adobe I/O開發人員控制台](https://console.adobe.io/)。 請洽詢您的組織管理員以取得存取要求。

### 驗證{#auth}

請遵循下列步驟，使用[!DNL Adobe I/O]配置[!DNL JWT (Service Account)]驗證：

1. 登入[Adobe開發人員主控台](https://console.adobe.io/)。
1. 按照[服務帳戶連接](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步驟操作。
   * 在[步驟2:使用服務帳戶驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)將API新增至您的專案，請選擇[!DNL Audience Manager] [!DNL API]選項。
1. 根據[步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的指示進行第一個[!DNL API]呼叫，以嘗試連接。

>[!NOTE]
>
>要以自動方式配置和使用[!DNL Audience Manager] [!DNL REST APIs]，可以寫程式生成[!DNL JWT]。 有關詳細說明，請參見[JWT（服務帳戶）Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

## [!DNL OAuth] 驗證（已過時）  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] 現在已不建議使用Token驗 [!DNL OAuth 2.0] 證和續約方式。
>
> 請改用[JWT（服務帳戶）驗證](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循代號驗證和續約的[!DNL OAuth 2.0]標準。 以下各節將說明如何驗證和開始使用[!DNL API]。

### 建立一般[!DNL API]用戶{#requirements}

我們建議您建立個別的技術使用者帳戶，以搭配[!DNL Audience Manager] [!DNL API]使用。這是一般帳戶，不會系結至您組織中的特定使用者或與其關聯。 此類[!DNL API]使用者帳戶可協助您完成下列2項工作：

* 識別呼叫[!DNL API]的服務（例如，來自使用我們[!DNL API]的應用程式或來自發出[!DNL API]請求的其他工具的呼叫）。
* 不間斷地訪問[!DNL API]。當系結至特定人員的帳戶離開您的公司時，可能會將其刪除。 這會使您無法使用可用的[!DNL API]程式碼。 未系結至特定員工的一般帳戶可協助您避免此問題。

舉例來說，假設您想要使用[大量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次變更許多區段，做為此類帳戶的使用案例。 為此，您的使用者帳戶需要[!DNL API]存取權。 請建立非特定的[!DNL API]使用者帳戶，該帳戶具有適當的認證、金鑰和機密，以進行[!DNL API]呼叫，而不是新增權限給特定使用者。 如果您開發使用[!DNL Audience Manager] [!DNL API]的自己應用程式，這也很有用。

與您的[!DNL Audience Manager]顧問合作，以設定一般[!DNL API]僅限使用者帳戶。

### 密碼驗證工作流{#password-authentication-workflow}

密碼驗證安全訪問我們的[!DNL REST API]。 以下步驟概述瀏覽器中[!DNL JSON]用戶端的密碼驗證工作流程。

>[!TIP]
>
>如果將存取和重新整理Token儲存在資料庫中，請加密這些Token。

#### 步驟1:請求[!DNL API]訪問

請洽詢您的合作夥伴解決方案經理。 他們會提供您[!DNL API]用戶端ID和密碼。 ID和密碼會將您驗證給[!DNL API]。

注意：如果您想要收到重新整理Token，請在您要求[!DNL API]存取時指定。

#### 步驟2:請求代號

將Token請求傳入您偏好的[!DNL JSON]用戶端。 建立請求時：

* 使用`POST`方法調用`https://api.demdex.com/oauth/token`。
* 將您的用戶端ID和密碼轉換為基本64編碼字串。 在轉換程式中，以冒號分隔ID和密碼。 例如，憑據`testId : testSecret`轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的標題可能如下所示：<br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 按如下方式設定請求正文：
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3:接收Token

[!DNL JSON]回應包含您的存取Token。 回應應如下所示：

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in`金鑰代表存取Token過期前的秒數。 最佳實務是，使用較短的過期時間，在代號曝光時限制曝光。

### 重新整理Token {#refresh-token}

重新整理Token會在原始Token過期後續約[!DNL API]存取權。 如果請求，密碼工作流中的響應[!DNL JSON]包括刷新標籤。 如果您未收到重新整理Token，請透過密碼驗證程式建立新Token。

您也可以使用重新整理Token，在現有存取Token過期之前產生新Token。

如果您的存取Token已過期，您會在回應中收到`401 Status Code`和下列標題：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟概述了使用重新整理Token從瀏覽器的[!DNL JSON]用戶端建立新存取Token的工作流程。

#### 步驟1:請求新Token

將重新整理Token請求傳入您偏好的[!DNL JSON]用戶端。 建立請求時：

* 使用`POST`方法調用`https://api.demdex.com/oauth/token`。
* 將您的用戶端ID和密碼轉換為基本64編碼字串。 在轉換程式中，以冒號分隔ID和密碼。 例如，憑據`testId : testSecret`轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入HTTP標題`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的標題可能如下所示：<br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在請求內文中，指定`grant_type:refresh_token`並傳遞您在先前存取請求中收到的重新整理Token。 請求應如下所示：<br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2:接收新Token

[!DNL JSON]回應包含您的新存取Token。 回應應如下所示：

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### 授權碼與隱式驗證{#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支援授權碼和隱式驗證。 若要使用這些存取方法，您的使用者必須登入`https://api.demdex.com/oauth/authorize`才能取得存取和重新整理Token。

## 進行驗證[!DNL API]請求{#authenticated-api-requests}

在您收到驗證Token後呼叫[!DNL API]方法的需求。

要對可用[!DNL API]方法進行調用，請執行以下操作：

* 在`HTTP`標題中，設定`Authorization: Bearer <token>`。
* 使用[JWT（服務帳戶）Authentication](#jwt)時，您需要提供`x-api-key`標題，該標題與您的`client_id`相同。 您可從[Adobe I/O整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面取得`client_id`。
* 呼叫所需的[!DNL API]方法。

## 可選[!DNL API]查詢參數{#optional-api-query-parameters}

設定可用於返回對象所有屬性的方法的可選參數。

您可以將這些可選參數與返回對象&#x200B;*all*&#x200B;屬性的[!DNL API]方法一起使用。 將查詢傳入[!DNL API]時，請在請求字串中設定這些選項。

| 參數 | 說明 |
|--- |--- |
| `page` | 依頁碼傳回結果。 編號從0開始。 |
| `pageSize` | 設定請求傳回的回應結果數目（預設值為10）。 |
| `sortBy` | 根據指定的[!DNL JSON]屬性排序並返回結果。 |
| `descending` | 以遞減順序排序和傳回結果。 `ascending` 為預設值。 |
| `search` | 根據您要用作搜尋參數的指定字串傳回結果。 例如，假設您想要在該項目的任何值欄位中，尋找具有「測試」字詞的所有模型的結果。 您的範例要求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜尋&quot;[!DNL get all]&quot;方法傳回的任何值。 |
| `folderId` | 傳回指定資料夾內[!UICONTROL traits]的所有ID。 並非所有方法都適用。 |
| `permissions` | 根據指定的權限傳回區段清單。 `READ` 為預設值。權限包括：<ul><li>`READ` :傳回並檢視區段的相關資訊。</li><li>`WRITE` :用  `PUT`  於更新區段。</li><li>`CREATE` :用  `POST`  於建立區段。</li><li>`DELETE` : 刪除區段. 需要存取基本特徵（如果有）。 例如，若您要移除屬於某個群體的特徵，您需要有權利加以刪除。</li></ul><br>使用個別的索引鍵值配對指定多個權限。例如，若要傳回僅具有`READ`和`WRITE`權限的區段清單，請傳入`"permissions":"READ"`、`"permissions":"WRITE"`。 |
| `includePermissions` | ([!DNL Boolean])設為`true`以傳回區段的權限。 預設為 `false`. |

### 關於頁面選項的附註

當未指定頁面資訊&#x200B;*時，請求會傳回純[!DNL JSON]，產生陣列。*&#x200B;如果指定了頁面資訊&#x200B;**，則返回的清單將被包在[!DNL JSON]對象中，該對象包含有關總結果和當前頁面的資訊。 您使用頁面選項的範例要求看起來可能類似下列：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] 請求、測試和生產環境以及版本。

## 請求 [!DNL URLs] {#request-urls}

下表按方法列出用於傳入[!DNL API]請求的請求[!DNL URLs]。

根據您使用的驗證方法，您需要根據下表調整您的請求[!DNL URLs]。

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

### 要求[!DNL OAuth]驗證[!DNL URLs]（已過時）{#request-urls-oauth}

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

## 環境{#environments}

[!DNL Audience Manager] [!DNL API]提供對不同工作環境的訪問。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時的生產資料。 下表列出了可用的[!DNL API]環境和相應的資源主機名。

根據您使用的驗證方法，您需要根據下表調整您的環境[!DNL URLs]。

| 環境 | [!DNL JWT]驗證的主機名 | [!DNL OAuth]驗證的主機名 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **測試版** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager]測試版環境是生產環境的較小規模的獨立版本。 您必須在此環境中輸入並收集您要測試的所有資料。

## 版本 {#versions}

這些[!DNL API]的新版本會定期發行。 新版本會遞增[!DNL API]版本號碼。 在請求[!DNL URL]中，版本號被引用為`v<version number>`，如下例所示：

`https://<host>/v1/...`

## 已定義的響應代碼{#response-codes-defined}

`HTTP` 狀態代碼和由返回的響應文本 [!DNL Audience Manager] [!UICONTROL REST API]。

| 回應碼ID | 回應文字 | 定義 |
|---|---|---|
| `200` | `OK` | 請求已成功處理。 將視需要傳回預期的內容或資料。 |
| `201` | `Created` | 已建立資源。 傳回`PUT`和`POST`請求。 |
| `204` | `No Content` | 已刪除資源。 回應主體將為空。 |
| `400` | `Bad Request` | 伺服器不瞭解請求。 通常是由於語法格式錯誤所致。 請檢查您的要求，然後再試一次。 |
| `403` | `Forbidden` | 您沒有資源的存取權。 |
| `404` | `Not Found` | 找不到指定路徑的資源。 |
| `409` | `Conflict` | 由於資源狀態衝突，無法完成請求。 |
| `500` | `Server Error` | 伺服器遇到意外錯誤，無法完成請求。 |

>[!MORELIKETHIS]
>
>* [JWT（服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2簡化版](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

