---
description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe動態標籤管理器和Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe動態標籤管理器和Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-title: Tag Management 元件
solution: Audience Manager
title: Tag Management 元件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 系統元件
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---


# Tag Management 元件{#tag-management-components}

Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(不再提倡Adobe動態標籤管理器和Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [用戶端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 客戶端入口{#client-portal}

用戶端入口網站是標籤與資料管理的主要使用者介面(UI)。 客戶使用入口網站來處理標籤、建立特徵和區段、設定目標，並透過報表監控促銷活動績效。

## DIL/TIM容器{#dil-tim}

[!UICONTROL DIL]容器可協助將[!DNL Audience Manager]資料收集程式碼部署至您的網站。 [!UICONTROL TIM] 是已過時的「標籤插入管理器」。[!DNL Audience Manager]不再使用它。 請改用[動態標籤管理](https://docs.adobe.com/content/help/zh-Hant/dtm/using/dtm-home.html)或[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)中的[!DNL Audience Manager]擴充功能，以設定並產生您置入清單頁面上的容器代碼。 [!UICONTROL DTM]容器可與[!UICONTROL Data Information Library (DIL)]搭配運作，從您的網站收集資料並傳送至[!DNL Audience Manager]。

## Data Integration Library (DIL) {#dil}

[資料資訊庫](../../dil/dil-overview.md)(DIL)是自含的API模組，可從您的網站收集資料。 [!UICONTROL DIL] 協助您免除撰寫資料收集、整合、讀取Cookie值和復原頁面資料的特殊程式碼。[!UICONTROL DIL] 自動執行這些動作。此外，[!UICONTROL DIL]還小巧。 它是獨立的程式碼庫，可協助降低收集資訊所需的程式碼量。 最後，[!UICONTROL DIL]可協助您將[!DNL Audience Manager]與[!DNL Adobe]Experience Cloud中的其他產品整合。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [](https://www.akamai.com/us/en/about/) Akamaito從我們自己的標籤管理平台（稱為「Akamaito」）代管和傳送容器程式碼 [!UICONTROL TIM (Tag Insertion Manager)]。但是，[!UICONTROL TIM]的程式碼部署已逐步淘汰，以利於[!DNL Adobe Dynamic Tag Management]和[!DNL Adobe Experience Platform Launch]。

## 控制資料庫{#control-database}

控制資料庫：

* 處理來自入口網站的用戶端輸入（例如，建立特徵和目標）。
* 傳送資料至Akamai，其中包含用來建立容器範本和目的地發佈iFrame的資料。
* 傳回UI報表系統的資料。

