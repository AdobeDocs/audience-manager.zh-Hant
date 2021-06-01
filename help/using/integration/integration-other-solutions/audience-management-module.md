---
description: 將「對象管理模組」新增至Adobe Analytics AppMeasurement，以將Analytics資料轉送至Audience Manager，而非讓Audience ManagerData Integration Library(DIL)程式碼從頁面傳送像素。
keywords: audience analytics;analytics;ssf;伺服器端轉送
seo-description: 將「對象管理模組」新增至Adobe Analytics AppMeasurement，以將Analytics資料轉送至Audience Manager，而非讓Audience ManagerData Integration Library(DIL)程式碼從頁面傳送像素。
seo-title: 實作對象管理模組
solution: Audience Manager
title: 實作對象管理模組
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics 整合功能
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# 如何將資料從[!DNL Adobe Analytics]轉發到[!DNL Audience Manager] {#implement-the-audience-management-module}

請依照本教學課程中的步驟，將[!DNL Analytics]資料轉送至[!DNL Audience Manager]，而非讓[!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL])程式碼從頁面傳送像素。

>[!TIP]
>
>建議您使用[!DNL Adobe Experience Platform Launch]將[!UICONTROL Analytics]資料轉送至[!DNL Audience Manager]。 使用[!UICONTROL Launch]，您不必手動將程式碼複製到[!DNL AppMeasurement]，如本頁所示。

## 必要條件 {#prereqs}

除了啟用擴充功能或實作本檔案所述的程式碼外，您還必須：

* 實作[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)。
* 為[!UICONTROL Adobe Analytics Admin Console]中的報表套裝啟用[伺服器端轉送](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)。

## 實施 {#implementation}

實作從[!DNL Adobe Analytics]到[!DNL Audience Manager]的資料轉送有兩種方法，視您使用的標籤管理解決方案而定。

### 使用[!DNL Adobe Experience Platform Launch]實作

[!DNL Adobe] 建議您使用 [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launch擴充功能，對 [!DNL Adobe Analytics] 您的 [!DNL Audience Manager] 屬性進行測試和。在此情況下，您不需要手動複製任何代碼。 請改為在[!DNL Analytics Launch]擴充功能中啟用資料共用，如下圖所示。 另請參閱[Adobe Analytics擴充功能](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager)檔案。

>[!TIP]
>
>如果安裝[!DNL Adobe Analytics]擴充功能，*不要*&#x200B;也要安裝[!DNL Audience Manager]擴充功能。 從[!DNL Analytics]擴充功能轉送資料會取代[!DNL Audience Manager]擴充功能。

![如何從Adobe Analytics擴充功能將資料共用至Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## 定義的代碼元素{#code-elements-defined}

下表定義程式碼範例中的重要變數。

| 參數 | 說明 |
|--- |--- |
| `partner` | 必填。這是[!DNL Adobe]指派給您的合作夥伴名稱。 有時稱為您的[!UICONTROL partner ID]或合作夥伴子網域。  如果您不知道您的合作夥伴名稱，請聯絡您的[!DNL Adobe]顧問或[客戶服務](https://helpx.adobe.com/tw/marketing-cloud/contact-support.html)。 |
| `containerNSID` | 必填。大部分的客戶只能設定`"containerNSID":0` 。 不過，如果您的公司需要自訂ID與不同容器同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 選填。此設定可讓您在第一方網域中設定[!DNL Adobe] Cookie。 此[!DNL cookie]包含[UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必填。如果您使用與[!UICONTROL AppMeasurement]版本2.10或更新版本捆綁的[!DNL AudienceManagement]模組，則需要`namespace`參數。 此[!UICONTROL AudienceManagement]模組要求您使用[!UICONTROL Adobe Experience Platform Identity Service] 3.3或更新版本。 <br><br>是 [!UICONTROL Experience Cloud Organization ID] 公司在註冊時獲得的ID  [!UICONTROL Experience Cloud]。在[組織和帳戶連結](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)中查找您公司的組織ID。 |

## 結果：資料轉送至[!DNL Audience Manager] {#results-data-forwarding}

您的[!DNL Analytics]實作會在您具備下列條件後，將資料傳送至[!DNL Audience Manager]:

* 啟用[!UICONTROL Server-Side Forwarding]（與您的顧問討論此功能）;
* 實作[!DNL Adobe Experience Platform Identity Service];
* 請依照本教學課程中的實作步驟操作。

此進程將資料發送到[!DNL Audience Manager]:

* 在頁面檢視呼叫上；
* 從追蹤的連結；
* 從視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>從[!DNL Analytics]傳送至[!DNL Audience Manager]的變數使用特殊前置詞。 建立[!DNL Audience Manager]特徵時，您需要了解並考慮這些前置詞。 如需這些前置詞的詳細資訊，請參閱關鍵變數的[前置詞要求](../../features/traits/trait-variable-prefixes.md)。
