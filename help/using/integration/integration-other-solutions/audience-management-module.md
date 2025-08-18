---
description: 將「對象管理模組」新增至Adobe Analytics AppMeasurement，以將Analytics資料轉送至Audience Manager，而非讓Audience Manager Data Integration Library (DIL)程式碼從頁面傳送畫素。
keywords: audience analytics； analytics； ssf；伺服器端轉送
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 實作對象管理模組
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# 如何將資料從[!DNL Adobe Analytics]轉送至[!DNL Audience Manager] {#implement-the-audience-management-module}

依照本教學課程中的步驟，將[!DNL Analytics]資料轉送至[!DNL Audience Manager]，而非讓[!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])程式碼從頁面傳送畫素。

>[!TIP]
>
>建議您使用[!DNL Adobe Experience Platform Tags]將[!UICONTROL Analytics]資料轉送至[!DNL Audience Manager]。 使用[!UICONTROL Tags]後，您不必手動將程式碼複製到[!DNL AppMeasurement]，如本頁所示。

## 先決條件 {#prereqs}

除了啟用擴充功能或實作本檔案所述的程式碼外，您還必須：

* 實作[Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
* 為[中的報表套裝啟用](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html)伺服器端轉送[!UICONTROL Adobe Analytics Admin Console]。

## 實施 {#implementation}

根據您使用的標籤管理解決方案，有兩種方法可實作從[!DNL Adobe Analytics]到[!DNL Audience Manager]的資料轉送。

### 使用[!DNL Adobe Experience Platform Tags]的實作

[!DNL Adobe]建議您使用[標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en)延伸來檢測[!DNL Adobe Analytics]和[!DNL Audience Manager]的屬性。 在此情況下，您不需要手動複製任何程式碼。 相反地，您必須在[!DNL Analytics]擴充功能中啟用資料共用，如下圖所示。 另請參閱[Adobe Analytics擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager)檔案。

>[!TIP]
>
>如果您安裝[!DNL Adobe Analytics]擴充功能，*不要*&#x200B;也安裝[!DNL Audience Manager]擴充功能。 從[!DNL Analytics]擴充功能轉送資料會取代[!DNL Audience Manager]擴充功能。

![如何啟用從Adobe Analytics擴充功能到Audience Manager的資料共用](/help/using/integration/assets/analytics-to-aam.png)

## 定義的程式碼元素 {#code-elements-defined}

下表定義程式碼範例中的重要變數。

| 參數 | 說明 |
|--- |--- |
| `partner` | 必填。這是[!DNL Adobe]指派給您的合作夥伴名稱。 它有時稱為您的[!UICONTROL partner ID]或合作夥伴子網域。  如果您不知道您的合作夥伴名稱，請連絡您的[!DNL Adobe]顧問或[客戶服務](https://helpx.adobe.com/tw/marketing-cloud/contact-support.html)。 |
| `containerNSID` | 必填。大部分客戶只需設定`"containerNSID":0` 。 不過，如果您的公司需要以不同的容器自訂ID同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 可選。此設定可讓您在第一方網域中設定[!DNL Adobe] Cookie。 此[!DNL cookie]包含[UUID](../../reference/ids-in-aam.md) 。 |
| `visitorService` - `namespace` | 必填。如果您使用`namespace` 2.10或更新版本隨附的[!DNL AudienceManagement]模組，則需要[!UICONTROL AppMeasurement]引數。 此[!UICONTROL AudienceManagement]模組需要您使用[!UICONTROL Adobe Experience Platform Identity Service] 3.3或更新版本。 <br><br> [!UICONTROL Experience Cloud Organization ID]是公司註冊[!UICONTROL Experience Cloud]時所提供的ID。 在[組織與帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)中找出您公司的組織識別碼。 |

## 結果：資料轉送至[!DNL Audience Manager] {#results-data-forwarding}

您的[!DNL Analytics]實作會在下列情況發生後傳送資料給[!DNL Audience Manager]：

* 啟用[!UICONTROL Server-Side Forwarding] （與您的顧問討論此功能）；
* 已實作[!DNL Adobe Experience Platform Identity Service]；
* 已按照本教學課程中的實作步驟進行。

此程式會將資料傳送至[!DNL Audience Manager]：

* 在頁面檢視呼叫上；
* 從追蹤的連結；
* 從視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>從[!DNL Audience Manager]傳送至[!DNL Analytics]的變數使用特殊首碼。 建立[!DNL Audience Manager]特徵時，您需要瞭解並考量這些字首。 如需這些首碼的詳細資訊，請參閱[索引鍵變數的首碼需求](../../features/traits/trait-variable-prefixes.md)。
