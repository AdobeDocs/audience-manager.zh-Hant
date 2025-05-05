---
description: 有關一般需求、驗證、選用查詢參數、請求 URL 和其他參考的資訊。
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: REST API 快速入門
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 1%

---

# 開始使用[!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

關於一般需求、驗證、選擇性查詢引數、要求[!DNL URLs]和其他參考的資訊。

## API需求與Recommendations {#api-requirements-recommendations}

使用[Audience ManagerAPI](https://bank.demdex.com/portal/swagger/index.html#/)程式碼時，請注意下列事項：

* **要求引數：**&#x200B;除非另有指定，否則所有要求引數都是必要的。
* **要求標頭**：使用[Adobe Developer](https://www.adobe.io/)權杖時，您必須提供`x-api-key`標頭。 您可以依照[服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面中的指示來取得您的[!DNL API]金鑰。
* **[!DNL JSON]內容型別：**&#x200B;在您的程式碼中指定`content-type: application/json` *和* `accept: application/json`。
* **要求與回應：**&#x200B;以正確格式化的[!DNL JSON]物件傳送要求。 [!DNL Audience Manager]以[!DNL JSON]格式化的資料回應。 伺服器回應可包含要求的資料、狀態代碼或兩者。
* **存取：**&#x200B;您的[!DNL Audience Manager]顧問會提供您使用者端ID和金鑰，讓您提出[!DNL API]個請求。
* **檔案和程式碼範例：**&#x200B;斜體&#x200B;*的文字*&#x200B;代表您在製作或接收[!DNL API]資料時提供或傳入的變數。 將&#x200B;*斜體的*&#x200B;文字取代為您自己的程式碼、引數或其他必要資訊。

## 驗證 {#authentication}

[!DNL Audience Manager] [!DNL REST APIs]支援三種驗證方法。

* [!BADGE 建議]{type=positive}[OAuth伺服器對伺服器驗證](#oauth-adobe-developer)使用[Adobe開發人員主控台](https://www.adobe.io/)。 [!DNL Adobe Developer]是Adobe的開發人員生態系統和社群。 它包含所有Adobe產品[&#128279;](https://developer.adobe.com/apis/)的API。 這是設定及使用[!DNL Adobe] [!DNL APIs]的建議方式。 在Adobe開發人員檔案中進一步瞭解[OAuth伺服器對伺服器驗證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)。
* [!BADGE 已棄用]{type=negative}[JWT （服務帳戶）驗證](#jwt)使用[Adobe開發人員主控台](https://www.adobe.io/)。 [!DNL Adobe Developer]是Adobe的開發人員生態系統和社群。 它包含所有Adobe產品[&#128279;](https://developer.adobe.com/apis/)的API。
* [!BADGE 已棄用]{type=negative}[舊版OAuth驗證](#oauth-deprecated)。 雖然此方法已過時，但擁有現有[!DNL OAuth]整合的客戶可以繼續使用此方法。

>[!IMPORTANT]
>
>根據您的驗證方法，您需要相應地調整您的要求[!DNL URLs]。 如需您應使用之主機名稱的詳細資訊，請參閱[環境](#environments)區段。

## 使用Adobe Developer的OAuth伺服器對伺服器驗證 {#oauth-adobe-developer}

本節說明如何收集驗證Audience ManagerAPI呼叫所需的認證，如下方流程圖所述。 您可以在初始的一次性設定中收集大部分必要的認證。 然而，存取權杖必須每24小時重新整理一次。

![Audience Manager驗證流程圖。](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer概觀 {#developer-overview}

[!DNL Adobe Developer]是Adobe的開發人員生態系統和社群。 它包含所有Adobe產品[&#128279;](https://developer.adobe.com/apis)的API。

這是設定及使用[!DNL Adobe] [!DNL APIs]的建議方式。

### 必備條件 {#prerequisites-server-to-server}

設定[!DNL OAuth Server-to-Server]驗證之前，請確定您擁有[Adobe Developer](https://developer.adobe.com/)中[Adobe Developer Console](https://developer.adobe.com/console/home)的存取權。 如需存取要求，請聯絡您的組織管理員。

### 驗證 {#oauth}

請依照下列步驟，使用[!DNL Adobe Developer]設定[!DNL OAuth Server-to-Server]驗證：

1. 登入[Adobe Developer Console](https://developer.adobe.com/console/home)。
1. 請依照[OAuth伺服器對伺服器認證實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)中的步驟操作。
   * 在[步驟2：使用服務帳戶驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)新增API至您的專案，請選擇[!DNL Audience Manager] [!DNL API]選項。
1. 根據[步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)的指示，進行您的第一個[!DNL API]呼叫以嘗試連線。

>[!NOTE]
>
>若要以自動方式設定及使用[!DNL Audience Manager] [!DNL REST APIs]，您可以以程式設計方式輪換使用者端密碼。 如需詳細指示，請參閱[開發人員檔案](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically)。

### 將Audience Manager API新增至專案 {#add-aam-api-to-project}

移至[Adobe Developer Console](https://www.adobe.com/go/devs_console_ui)並使用您的Adobe ID登入。 接下來，請依照教學課程中概述的步驟，在Adobe Developer Console檔案中建立[空白專案](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/)。

建立新專案後，請在&#x200B;**[!UICONTROL Project Overview]**&#x200B;畫面上選取&#x200B;**[!UICONTROL Add API]**。

>[!TIP]
>
>如果您已布建多個組織，請使用介面右上角的組織選擇器，以確保您位於所需的組織中。

![Developer Console熒幕，醒目提示「新增API」選項。](/help/using/api/rest-api-main/assets/add-api.png)

**[!UICONTROL Add an API]**&#x200B;畫面會出現。 選取Adobe Experience Cloud的產品圖示，然後選擇&#x200B;**[!UICONTROL Audience Manager API]**&#x200B;再選取&#x200B;**[!UICONTROL Next]**。

![選取Audience ManagerAPI。](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>選取&#x200B;**[!UICONTROL View docs]**&#x200B;選項，在個別瀏覽器視窗中導覽至完整的[Audience ManagerAPI參考檔案](https://bank.demdex.com/portal/swagger/index.html#)。

### 選取OAuth伺服器對伺服器驗證型別 {#select-oauth-server-to-server}

接著，選取驗證型別以產生存取權杖並存取Audience ManagerAPI。

>[!IMPORTANT]
>
>選取&#x200B;**[!UICONTROL OAuth Server-to-Server]**&#x200B;方法，因為這是唯一支援向前移動的方法。 **[!UICONTROL Service Account (JWT)]**&#x200B;方法已過時。 雖然使用JWT驗證方法的整合功能在2025年1月1日之前將繼續運作，但Adobe強烈建議您在該日期之前將現有整合功能移轉至新的OAuth伺服器對伺服器方法。

![選取OAuth驗證方法。](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### 選取要整合的產品設定檔 {#select-product-profiles}

在&#x200B;**[!UICONTROL Configure API]**&#x200B;畫面中，選取所需的產品設定檔。 您整合的服務帳戶可透過此處選取的產品設定檔存取精細功能。

![選取整合的產品設定檔。](/help/using/api/rest-api-main/assets/select-product-profiles.png)

準備好後選取&#x200B;**[!UICONTROL Save configured API]**。

### 收集認證 {#gather-credentials}

將API新增至專案後，專案的&#x200B;**[!UICONTROL Audience Manager API]**&#x200B;頁面會顯示所有呼叫Audience ManagerAPI時所需的下列認證：

在Developer Console中新增API後的![整合資訊。](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## 產生存取權杖 {#generate-access-token}

下一個步驟是產生`{ACCESS_TOKEN}`認證以用於Audience ManagerAPI呼叫。 不像`{API_KEY}`和`{ORG_ID}`的值，必須每24小時產生一次新Token，才能繼續使用Audience ManagerAPI。 選取&#x200B;**[!UICONTROL Generate access token]**，如下所示。

![顯示如何產生存取權杖](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## 測試API呼叫 {#test-api-call}

取得驗證持有人權杖後，請執行API呼叫以測試您現在可以存取Audience ManagerAPI。

1. 瀏覽至[API參考檔案](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_)。
2. 選取&#x200B;**[!UICONTROL Authorize]**&#x200B;並貼上您在[產生存取權杖](#generate-access-token)步驟中取得的存取權杖。

   ![授權API呼叫](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. 執行`/datasources` API端點的GET呼叫，以擷取所有全域可用的資料來源清單，如[API參考檔案](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_)中所述。 選取&#x200B;**[!UICONTROL Try it out]**，接著選取&#x200B;**[!UICONTROL Execute]**，如下所示。

   ![執行API呼叫](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API要求]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB 如果使用正確的持有人權杖，則為API回應]


使用有效的存取Token時，API端點會傳回200回應，以及包含您的組織有權存取之所有全域資料來源的回應主體。

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE 已棄用]{type=negative}使用Adobe Developer的[!DNL JWT] ([!DNL Service Account])驗證 {#jwt}

+++ 檢視已棄用的[!DNL JWT] ([!DNL Service Account])取得驗證權杖方法的相關資訊。

### Adobe Developer概觀 {#adobeio}

[!DNL Adobe Developer]是Adobe的開發人員生態系統和社群。 它包含所有Adobe產品[&#128279;](https://www.adobe.io/apis.html)的API。

這是設定及使用[!DNL Adobe] [!DNL APIs]的建議方式。

### 必備條件 {#prerequisites}

設定[!DNL JWT]驗證之前，請確定您擁有[Adobe Developer](https://www.adobe.io/)中[Adobe Developer Console](https://console.adobe.io/)的存取權。 如需存取要求，請聯絡您的組織管理員。

### 驗證 {#auth}

請依照下列步驟，使用[!DNL Adobe Developer]設定[!DNL JWT (Service Account)]驗證：

1. 登入[Adobe Developer Console](https://console.adobe.io/)。
1. 請依照[服務帳戶連線](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中的步驟操作。
   * 在[步驟2：使用服務帳戶驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)新增API至您的專案，請選擇[!DNL Audience Manager] [!DNL API]選項。
1. 根據[步驟3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)的指示，進行您的第一個[!DNL API]呼叫以嘗試連線。

>[!NOTE]
>
>若要以自動方式設定及使用[!DNL Audience Manager] [!DNL REST APIs]，您可以以程式設計方式產生[!DNL JWT]。 如需詳細指示，請參閱[JWT （服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)。

### 技術帳戶RBAC許可權

如果您的Audience Manager帳戶使用[角色型存取控制](../../features/administration/administration-overview.md)，您必須建立Audience Manager技術使用者帳戶，並將其新增至將進行API呼叫的Audience ManagerRBAC群組。

請依照下列步驟建立技術使用者帳戶，並將其新增至RBAC群組：

1. 對`https://aam.adobe.io/v1/users/self`進行`GET`呼叫。 通話將會建立您可以在[!UICONTROL Users]頁面的[!UICONTROL Admin Console]中看到的技術使用者帳戶。

   ![技術帳戶](assets/technical-account.png)

1. 登入您的Audience Manager帳戶，然後[將技術使用者帳戶](../../features/administration/administration-overview.md#create-group)新增到將進行API呼叫的使用者群組。

+++

## [!BADGE 已棄用]{type=negative}[!DNL OAuth]驗證（已棄用） {#oauth-deprecated}

+++ 檢視已棄用的舊版[!DNL OAuth]取得驗證Token的驗證方法相關資訊。

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API]權杖驗證和透過[!DNL OAuth 2.0]的續約現在已被取代。
>
> 請改用[JWT （服務帳戶）驗證](#jwt-service-account-authentication-jwt)。

[!DNL Audience Manager] [!UICONTROL REST API]遵循權杖驗證和更新的[!DNL OAuth 2.0]標準。 以下各節說明如何驗證並開始使用[!DNL API]。

### 建立一般[!DNL API]使用者 {#requirements}

建議您建立個別的技術使用者帳戶來使用[!DNL Audience Manager] [!DNL API]。這是一般帳戶，不會繫結至組織中的特定使用者或與其相關聯。 此型別的[!DNL API]使用者帳戶可協助您完成2件事：

* 識別呼叫[!DNL API]的服務（例如，使用我們[!DNL API]的應用程式呼叫，或其他發出[!DNL API]要求的工具呼叫）。
* 提供對[!DNL API]的不中斷存取。繫結至特定人員的帳戶可能會在離開您的公司時刪除。 這會使您無法使用可用的[!DNL API]程式碼。 未與特定員工繫結的一般帳戶可協助您避免此問題。

此型別帳戶的範例或使用案例，假設您想使用[大量管理工具](../../reference/bulk-management-tools/bulk-management-intro.md)一次變更許多區段。 若要這麼做，您的使用者帳戶需要[!DNL API]存取權。 請建立具有適當認證、金鑰和密碼的非特定[!DNL API]使用者帳戶，以進行[!DNL API]呼叫，而不新增許可權給特定使用者。 如果您開發自己的使用[!DNL Audience Manager] [!DNL API]的應用程式，這也很有用。

與您的[!DNL Audience Manager]顧問合作，設定僅限[!DNL API]的通用使用者帳戶。

### 密碼驗證工作流程 {#password-authentication-workflow}

密碼驗證可安全存取我們的[!DNL REST API]。 以下步驟概述來自瀏覽器中[!DNL JSON]使用者端的密碼驗證工作流程。

>[!TIP]
>
>如果您將Token儲存在資料庫中，請加密存取並重新整理Token。

#### 步驟1：要求[!DNL API]存取權

請連絡您的合作夥伴解決方案經理。 他們將會提供[!DNL API]使用者端ID和密碼。 ID和密碼會驗證[!DNL API]的身份。

注意：如果您想要收到重新整理權杖，請在您要求[!DNL API]存取權時指定。

#### 步驟2：要求權杖

傳入權杖要求給您偏好的[!DNL JSON]使用者端。 當您建置請求時：

* 使用`POST`方法呼叫`https://api.demdex.com/oauth/token`。
* 將您的使用者端ID和密碼轉換為base-64編碼字串。 在轉換過程中使用冒號分隔ID和密碼。 例如，認證`testId : testSecret`已轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入[!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded` 。 例如，您的標頭可能如下所示： <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* 設定要求內文，如下所示：
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### 步驟3：接收權杖

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

`expires_in`金鑰代表存取Token到期前的秒數。 如果代號公開時，最佳做法就是使用較短的到期時間來限制曝光。

### 重新整理Token {#refresh-token}

重新整理Token在原始的Token過期後更新[!DNL API]存取權。 若有要求，密碼工作流程中的回應[!DNL JSON]會包含重新整理權杖。 如果您沒有收到重新整理權杖，請透過密碼驗證程式建立新的權杖。

您也可以使用重新整理權杖，在現有存取權杖過期之前產生新權杖。

如果您的存取Token已過期，您會在回應中收到`401 Status Code`和下列標頭：

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

下列步驟概述使用重新整理權杖從瀏覽器中的[!DNL JSON]使用者端建立新存取權杖的工作流程。

#### 步驟1：要求新Token

傳入重新整理Token要求給您偏好的[!DNL JSON]使用者端。 當您建置請求時：

* 使用`POST`方法呼叫`https://api.demdex.com/oauth/token`。
* 將您的使用者端ID和密碼轉換為base-64編碼字串。 在轉換過程中使用冒號分隔ID和密碼。 例如，認證`testId : testSecret`已轉換為`dGVzdElkOnRlc3RTZWNyZXQ=`。
* 傳入HTTP標頭`Authorization:Basic <base-64 clientID:clientSecret>`和`Content-Type: application/x-www-form-urlencoded`。 例如，您的標頭可能如下所示： <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* 在要求內文中，指定`grant_type:refresh_token`並傳入您先前存取要求中收到的重新整理權杖。 要求應該如下所示： <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### 步驟2：接收新Token

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

### 授權代碼和隱含驗證 {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API]支援授權碼與隱含驗證。 若要使用這些存取方法，您的使用者需要登入`https://api.demdex.com/oauth/authorize`才能取得存取權杖並重新整理。

+++

## 提出已驗證的[!DNL API]要求 {#authenticated-api-requests}

收到驗證Token後呼叫[!DNL API]方法的需求。

若要對可用的[!DNL API]方法進行呼叫：

* 在`HTTP`標頭中，設定`Authorization: Bearer <token>`。
* 使用[JWT （服務帳戶）驗證](#jwt)時，您需要提供`x-api-key`標頭，此標頭將與您的`client_id`相同。 您可以從[Adobe Developer整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)頁面取得您的`client_id`。
* 呼叫必要的[!DNL API]方法。

## 選用的[!DNL API]查詢引數 {#optional-api-query-parameters}

設定傳回物件所有屬性的方法可用的選用引數。

您可以使用這些選擇性引數搭配[!DNL API]方法，傳回物件的&#x200B;*所有*&#x200B;屬性。 將該查詢傳入[!DNL API]時，在要求字串中設定這些選項。

| 參數 | 說明 |
|--- |--- |
| `page` | 依頁碼傳回結果。 編號從0開始。 |
| `pageSize` | 設定要求傳回的回應結果數目（預設為10）。 |
| `sortBy` | 根據指定的[!DNL JSON]屬性排序並傳回結果。 |
| `descending` | 以遞減順序排序並傳回結果。 `ascending`為預設值。 |
| `search` | 根據您要用作搜尋引數的指定字串傳回結果。 例如，假設您想要尋找在該專案的任何值欄位中有「Test」字詞的所有模型的結果。 您的範例請求可能如下所示：   `GET https://aam.adobe.io/v1/models/?search=Test`。  您可以搜尋&quot;[!DNL get all]&quot;方法傳回的任何值。 |
| `folderId` | 傳回指定資料夾中[!UICONTROL traits]的所有識別碼。 並非所有方法都可使用。 |
| `permissions` | 根據指定的許可權傳回區段清單。 `READ`為預設值。 許可權包括：<ul><li>`READ` ：傳回並檢視區段的相關資訊。</li><li>`WRITE` ：使用`PUT`更新區段。</li><li>`CREATE` ：使用`POST`建立區段。</li><li>`DELETE` ：刪除區段。 需要存取基礎特徵（如果有）。 例如，如果您想要移除區段，則需要擁有刪除屬於該區段之特徵的許可權。</li></ul><br>請以個別的索引鍵值配對指定多個許可權。 例如，若要傳回僅具有`READ`和`WRITE`許可權的區段清單，請傳入`"permissions":"READ"`、`"permissions":"WRITE"` 。 |
| `includePermissions` | ([!DNL Boolean])設為`true`以傳回您對區段的許可權。 預設值為`false`。 |

{style="table-layout:auto"}

### 關於頁面選項的附註

當未指定頁面資訊&#x200B;*時*，要求會傳回陣列中的純[!DNL JSON]結果。 如果指定頁面資訊&#x200B;**，則傳回的清單會包裝在包含總結果和目前頁面相關資訊的[!DNL JSON]物件中。 您使用頁面選項的範例請求看起來可能類似這樣：

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

請求、中繼和生產環境及版本的[!DNL URLs]。

## 要求[!DNL URLs] {#request-urls}

下表列出用來以方法傳入[!DNL API]個要求的要求[!DNL URLs]。

根據您使用的驗證方法，您需要根據下表調整您的要求[!DNL URLs]。

### 要求[!DNL URLs] [!BADGE 建議]{type=positive}[!BADGE 已棄用]{type=negative}透過Adobe Developer進行[!DNL JWT]驗證 {#request-urls-jwt}

| [!DNL API]方法 | 要求[!DNL URL] |
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

{style="table-layout:auto"}

### 要求[!BADGE 的[!DNL URLs]已棄用]&lbrace;type=negative&rbrace;[!DNL OAuth]驗證 {#request-urls-oauth}

| [!DNL API]方法 | 要求[!DNL URL] |
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

{style="table-layout:auto"}

## 環境 {#environments}

[!DNL Audience Manager] [!DNL API]提供不同工作環境的存取權。 這些環境可協助您針對個別資料庫測試程式碼，而不會影響即時生產資料。 下表列出可用的[!DNL API]環境和對應的資源主機名稱。

根據您使用的驗證方法，您需要根據下表調整您的環境[!DNL URLs]。

| 環境 | [!DNL JWT]驗證的主機名稱 | [!DNL OAuth]驗證的主機名稱 |
|---|---|---|
| **生產** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>[!DNL Audience Manager] Beta版環境是生產環境的較小規模、獨立版本。 您想要測試的所有資料都必須在此環境中輸入和收集。

## 版本 {#versions}

這些[!DNL API]的新版本會定期發行。 新發行版本會增加[!DNL API]版本編號。 請求[!DNL URL]中以`v<version number>`參照的版本號碼，如下列範例所示：

`https://<host>/v1/...`

## 已定義的回應代碼 {#response-codes-defined}

[!DNL Audience Manager] [!UICONTROL REST API]傳回的`HTTP`狀態代碼和回應文字。

| 回應代碼ID | 回應文字 | 定義 |
|---|---|---|
| `200` | `OK` | 已成功處理要求。 如有必要，將傳回預期的內容或資料。 |
| `201` | `Created` | 已建立資源。 傳回`PUT`與`POST`的要求。 |
| `204` | `No Content` | 已刪除資源。 回應本文將為空白。 |
| `400` | `Bad Request` | 伺服器不瞭解此要求。 通常是因為語法錯誤。 請檢查您的請求，然後再試一次。 |
| `403` | `Forbidden` | 您無權存取資源。 |
| `404` | `Not Found` | 找不到指定路徑的資源。 |
| `409` | `Conflict` | 由於與資源的狀態衝突，無法完成要求。 |
| `500` | `Server Error` | 伺服器發生未預期的錯誤，因此無法完成要求。 |

>[!MORELIKETHIS]
>
>* [JWT （服務帳戶）驗證](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth驗證](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [簡化的OAuth 2](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
