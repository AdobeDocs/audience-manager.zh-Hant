---
description: 將觀眾管理模組新增至Adobe Analytics AppMeasurement，將Analytics資料轉送至Audience Manager，而非讓Audience Manager Data Integration Library(DIL)程式碼從頁面傳送像素。
keywords: 受眾分析；分析；sf；伺服器端轉送
seo-description: 將觀眾管理模組新增至Adobe Analytics AppMeasurement，將Analytics資料轉送至Audience Manager，而非讓Audience Manager Data Integration Library(DIL)程式碼從頁面傳送像素。
seo-title: 實作觀眾管理模組
solution: Audience Manager
title: 實作觀眾管理模組
uuid: 0884627-def3-4a15-88e5-08882d8 d57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## 必備條件 {#prereqs}

除了實作本文件所述的程式碼以外，您還必須：

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## 實施 {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

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
>`audienceManagement.setup` 函數會與Audience Manager `DIL.create` 函數共用參數，您可以在此程式碼中設定。For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

下表定義程式碼範例中的重要變數。

| 參數 | 說明 |
|--- |--- |
| `partner` | 必填。這是Adobe指派給您的合作夥伴名稱。有時稱為「合作夥伴ID」或「合作夥伴子網域」。Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | 必填。Most customers can just set  `"containerNSID":0` . 不過，如果您的公司需要使用不同容器自訂ID同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 選填。此設定可讓您在第一方網域中設定Adobe Cookie。This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 必填。The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>這 [!UICONTROL Experience Cloud Organization ID] 是公司在註冊時提供的ID [!UICONTROL Experience Cloud]。Find out your company&#39;s Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

[!DNL Analytics] 實作後，您的實施會傳送資料至Audience Manager：

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* 實作ID服務；
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* 頁面檢視呼叫；
* 從追蹤連結；
* 來自視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. 您需要瞭解並在建立Audience Manager特徵時考量這些字首。For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).