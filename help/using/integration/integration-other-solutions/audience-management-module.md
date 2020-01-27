---
description: 將觀眾管理模組新增至Adobe Analytics appMeasurement，將Analytics資料轉送至Audience Manager，而不是讓Audience Manager資料整合庫(DIL)程式碼從頁面傳送像素。
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: 將觀眾管理模組新增至Adobe Analytics appMeasurement，將Analytics資料轉送至Audience Manager，而不是讓Audience Manager資料整合庫(DIL)程式碼從頁面傳送像素。
seo-title: 實作觀眾管理模組
solution: Audience Manager
title: 實作觀眾管理模組
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7e8ba292f2f901b1323d30d682066b49df885a0c

---


# 如何將資料從Adobe Analytics轉送至Audience Manager {#implement-the-audience-management-module}

請依照本教學課程中的步驟， [!DNL Analytics] 將資料轉送至Audience Manager，而不是讓Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL])程式碼從頁面傳送像素。

>[!TIP]
>
>我們建議您使用 [!UICONTROL Adobe Launch] 來將資 [!UICONTROL Analytics] 料轉送至Audience Manager。 使用 [!UICONTROL Launch]時，您不必手動將程式碼複製 [!UICONTROL AppMeasurement]至，如本頁所示。

## 必備條件 {#prereqs}

除了啟用擴充功能或實作本檔案所述的程式碼外，您還必須：

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* 在中 [為報表套裝啟用](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 「伺服器端轉送」 [!UICONTROL Adobe Analytics Admin Console]。

## 實施 {#implementation}

根據您使用的標籤管理解決方案，有兩種方法可實作從Adobe Analytics到Audience manager的資料轉送。

### 使用Adobe Launch進行實作

Adobe建議您使用 [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) 擴充功能，在屬性上測量Adobe Analytics和Audience Manager。 在這種情況下，您不需要手動複製任何代碼。 您必須改為在Analytics Launch擴充功能中啟用資料共用，如下圖所示。 另請參閱 [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 檔案。

>[!TIP]
>
>如果您安裝Adobe Analytics擴充功能， *請勿安裝* Audience Manager擴充功能。 從Analytics擴充功能轉送資料會取代Audience Manager擴充功能。

![如何啟用從Adobe Analytics擴充功能到Audience manager的資料共用](/help/using/integration/assets/analytics-to-aam.png)

### 使用Adobe數位標籤管理(DTM)或任何其他標籤管理解決方案的實作


>[!WARNING]
>
>Adobe已於2020年底發佈日落DTM計畫。 如需詳細資訊和排程，請參閱 [Adobe社群論壇的DTM日落計畫](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)。

若要實作使 [!UICONTROL Audience Management Module] 用 [Adobe DTM或其他標籤管理解決方案](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) :

1. 使用 [!UICONTROL AppMeasurement] Analytics代碼 [管理器](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) （需要1.5版或更新版本）下載。
1. 將您的 [!UICONTROL AppMeasurement] 程式碼更新為下載的zip檔案所包含的版本。
1. 從zip檔案複製所 `AppMeasurement_Module_AudienceManagement.js` 有程式碼。 貼到文字正 `appMeasurement.js` 上方的檔案中， `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 新增程式碼， `s.loadModule("AudienceManagement");`就在您剛在上 `AppMeasurement_Module_AudienceManagement.js` 一步驟中新增的程式碼上方。
1. 更新並複製下面的程式碼，並將它新增至檔 `doPlugins` 案的函式 `AppMeasurement.js` 中。

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
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
* 實作Experience Cloud ID服務；
* 已遵循本教學課程中的實施步驟。

此程式將資料發送到 [!DNL Audience Manager]:

* 頁面檢視呼叫；
* 從追蹤的連結；
* 從視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>從使用特殊字首傳送至Audience manager [!DNL Analytics] 的變數。 在建立Audience manager特徵時，您需要瞭解並考慮這些前置詞。 有關這些前置詞的詳細資訊，請參 [閱關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)。