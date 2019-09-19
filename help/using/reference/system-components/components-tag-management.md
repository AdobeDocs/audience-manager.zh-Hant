---
description: Audience manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager（不再提倡使用Adobe Dynamic Tag Manager和Adobe Launch）、DIL、Akamai和控制資料庫。
seo-description: Audience manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager（不再提倡使用Adobe Dynamic Tag Manager和Adobe Launch）、DIL、Akamai和控制資料庫。
seo-title: 標籤管理元件
solution: Audience Manager
title: 標籤管理元件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# 標籤管理元件{#tag-management-components}

Audience manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager（不再提倡使用Adobe Dynamic Tag Manager和Adobe Launch）、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience manager包含下列元件：

* [用戶端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 用戶端入口網站 {#client-portal}

用戶端入口網站是標籤與資料管理的主要使用者介面(UI)。 客戶使用入口網站來處理標籤、建立特徵和區段、設定目標，並透過報表監控促銷活動績效。

## DIL/TIM容器 {#dil-tim}

容器 [!UICONTROL DIL] 可協助將資料 [!DNL Audience Manager] 收集程式碼部署至您的網站。 [!UICONTROL TIM] 是已過時的「標籤插入管理器」。 它不再被使用 [!DNL Audience Manager]。 您可以改用 [動態標籤管理](https://marketing.adobe.com/resources/help/en_US/dtm/) ，或 [!DNL Audience Manager] Adobe Launch [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 中的擴充功能來設定並產生您置入庫存頁面的容器代碼。 容 [!UICONTROL DTM] 器可與一起 [!UICONTROL Data Information Library (DIL)] 從網站收集資料並傳送至 [!DNL Audience Manager]。

## 資料整合程式庫 (DIL) {#dil}

資 [料資訊庫](../../dil/dil-overview.md) (DIL)是可從您網站收集資料的獨立API模組。 [!UICONTROL DIL] 協助您免除撰寫資料收集、整合、讀取Cookie值和復原頁面資料的特殊程式碼。 [!UICONTROL DIL] 自動執行這些動作。 此外， [!UICONTROL DIL] 它小巧。 它是獨立的程式碼庫，可協助降低收集資訊所需的程式碼量。 最後， [!UICONTROL DIL] 協助您整 [!DNL Audience Manager] 合Experience cloud中的其他 [!DNL Adobe] 產品。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/html/about/index.html) ，從我們自己的標籤管理平台（稱為「Akamai」）代管和傳送容器代碼 [!UICONTROL TIM (Tag Insertion Manager)]。 但是，已逐 [!UICONTROL TIM] 步淘汰使用的程式碼部 [!UICONTROL Adobe Dynamic Tag Management] 署 [!UICONTROL Adobe Launch]。

## 控制資料庫 {#control-database}

控制資料庫：

* 處理來自入口網站的用戶端輸入（例如，建立特徵和目標）。
* 傳送資料至Akamai，其中包含用來建立容器範本和目標發佈iFrame的資料。
* 傳回UI報表系統的資料。

