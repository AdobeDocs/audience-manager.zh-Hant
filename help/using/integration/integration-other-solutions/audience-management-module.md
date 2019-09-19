---
description: 將觀眾管理模組新增至Adobe Analytics appMeasurement，將Analytics資料轉送至Audience Manager，而不是讓Audience Manager資料整合庫(DIL)程式碼從頁面傳送像素。
keywords: 受眾分析；分析；ssf;伺服器端轉發
seo-description: 將觀眾管理模組新增至Adobe Analytics appMeasurement，將Analytics資料轉送至Audience Manager，而不是讓Audience Manager資料整合庫(DIL)程式碼從頁面傳送像素。
seo-title: ' 實作觀眾管理模組'
solution: Audience Manager
title: ' 實作觀眾管理模組'
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# 實作觀眾管理模組 {#implement-the-audience-management-module}

新增至 [!UICONTROL Audience Management Module] 以將資 [!DNL Adobe Analytics] 料轉送至Audience Manager，而不是讓Audience Manager [!UICONTROL AppMeasurement] ( [!DNL Analytics][!UICONTROL Data Integration Library][!UICONTROL DIL])程式碼從頁面傳送像素。

## 必備條件 {#prereqs}

除了實作本檔案所述的程式碼外，您還必須：

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* 在 [!UICONTROL Server-Side Forwarding] 中啟用報表套裝 [!UICONTROL Adobe Analytics Admin Console]。

## 實施 {#implementation}

要實施以下操 [!UICONTROL Audience Management Module]作：

1. 使用 [!UICONTROL AppMeasurement] Analytics代碼 [管理器](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) （需要1.5版或更新版本）下載。
1. 將您的 [!UICONTROL AppMeasurement] 程式碼更新為下載的zip檔案所包含的版本。
1. 從zip檔案複製所 `AppMeasurement_Module_AudienceManagement.js` 有程式碼。 貼到文字正 `appMeasurement.js` 上方的檔案中， `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 新增程式碼， `s.loadModule("AudienceManagement");`就在您剛在上 `AppMeasurement_Module_AudienceManagement.js` 一步驟中新增的程式碼上方。
1. 更新並複製下面的程式碼，並將它新增至檔 `doPlugins` 案的函式 `AppMeasurement.js` 中。

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>此函 `audienceManagement.setup` 數會與Audience manager函式共用參數， `DIL.create` 您可在此程式碼中設定此函式。 如需這些參數的詳細資訊，請參 [閱DIL create](../../dil/dil-class-overview/dil-create.md#dil-create)。

## 定義的代碼元素 {#code-elements-defined}

下表定義程式碼範例中的重要變數。

| 參數 | 說明 |
|--- |--- |
| `partner` | 必填。這是Adobe指派給您的合作夥伴名稱。 它有時稱為「合作夥伴ID」或「合作夥伴子網域」。  如果您不知道您的 [合作夥伴名稱](https://helpx.adobe.com/marketing-cloud/contact-support.html) ，請連絡您的Adobe顧問或客戶服務。 |
| `containerNSID` | 必填。大部份的客戶都可以設定 `"containerNSID":0` 。 不過，如果您的公司需要使用不同的容器自訂ID同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 選填。此設定可讓您在第一方網域中設定Adobe Cookie。 此Cookie包含 [UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必填。如果 `namespace` 您使用2.10版或更新版本隨附的AudienceManagement模 [!UICONTROL AppMeasurement] 組，則需要此參數。 此模 [!UICONTROL AudienceManagement] 塊要求您使用 [!UICONTROL Experience Cloud ID Service] 3.3或更新版本。 <br> 公 [!UICONTROL Experience Cloud Organization ID] 司註冊時提供的ID [!UICONTROL Experience Cloud]。 在「組織」和「帳戶連結」中尋找您公 [司的組織ID](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)。 |

## 結果：資料轉送至Audience Manager {#results-data-forwarding}

您的 [!DNL Analytics] 實作會在您擁有下列功能後，將資料傳送至Audience Manager:

* 啟用( [!UICONTROL Server-Side Forwarding] 請洽詢您的顧問有關此功能的資訊);
* 實作ID服務；
* 已安裝 [!UICONTROL Audience Management Module]。

此程式將資料發送到 [!DNL Audience Manager]:

* 頁面檢視呼叫；
* 從追蹤的連結；
* 從視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>從使用特殊字首傳送至Audience manager [!DNL Analytics] 的變數。 在建立Audience manager特徵時，您需要瞭解並考慮這些前置詞。 有關這些前置詞的詳細資訊，請參 [閱關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)。