---
description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe Dynamic Tag Manager和Adobe Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe Dynamic Tag Manager和Adobe Launch)、DIL、Akamai和控制資料庫。
seo-title: 標籤管理元件
solution: Audience Manager
title: 標籤管理元件
uuid: e5059478-6ba7-4e1a-afec-e41 ad7 a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe Dynamic Tag Manager和Adobe Launch)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [用戶端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

用戶端入口網站是標籤和資料管理的主要使用者介面(UI)。客戶可使用入口網站來處理標記、建立特性和區段、設定目的地，以及使用報表監控促銷活動績效。

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] 容器有助於將 [!DNL Audience Manager] 資料收集程式碼部署至您的網站。[!UICONTROL TIM] 是已過時的「標籤插入管理器」。It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] 容器可搭配從您 [!UICONTROL Data Information Library (DIL)] 的網站收集資料並傳送給 [!DNL Audience Manager]該容器。

## 資料整合程式庫 (DIL) {#dil}

[資料資訊庫](../../dil/dil-overview.md) (DIL)是一個獨立的API模組，可收集您網站的資料。[!UICONTROL DIL] 協助免除編寫資料收集、整合、讀取Cookie值及恢復頁面資料的特殊程式碼。[!UICONTROL DIL] 自動執行這些動作。Additionally, [!UICONTROL DIL] is compact. 它是一個獨立的程式碼庫，可協助減少收集資訊所需的程式碼數量。Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/html/about/index.html) 從我們自己的標籤管理平台來托管並提供容器代碼 [!UICONTROL TIM (Tag Insertion Manager)]。However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

控制資料庫：

* 從入口網站處理用戶端輸入(例如建立特性和目的地)。
* 將資料傳送至Akamai，其中包含用來建立容器範本和目的地發佈IFrame的資料。
* 傳回UI報告系統的資料。

