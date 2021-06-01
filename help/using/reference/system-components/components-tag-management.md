---
description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(已淘汰，改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(已淘汰，改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-title: Tag Management 元件
solution: Audience Manager
title: Tag Management 元件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 系統元件
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# Tag Management 元件{#tag-management-components}

Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(已淘汰，改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [用戶端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 客戶端門戶{#client-portal}

用戶端入口網站是標籤和資料管理的主要使用者介面(UI)。 客戶可使用入口網站來處理標籤、建立特徵和區段、設定目的地，以及透過報表監控促銷活動績效。

## DIL/TIM容器{#dil-tim}

[!UICONTROL DIL]容器可協助將[!DNL Audience Manager]資料收集程式碼部署至您的網站。 [!UICONTROL TIM] 是過時的「標籤插入管理器」。[!DNL Audience Manager]不再使用。 請改為使用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)中的[!DNL Audience Manager]擴充功能，設定並產生您放置在庫存頁面上的容器代碼。

## Data Integration Library (DIL) {#dil}

[資料資訊庫](../../dil/dil-overview.md)(DIL)是可從您的網站收集資料的獨立API模組。 [!UICONTROL DIL] 有助於避免編寫特殊程式碼以用於資料收集、整合、讀取cookie值及恢復頁面資料的需求。[!UICONTROL DIL] 自動執行這些動作。此外， [!UICONTROL DIL]也很緊湊。 這是獨立的程式碼程式庫，可協助減少收集資訊所需的程式碼量。 最後，[!UICONTROL DIL]可幫助您將[!DNL Audience Manager]與[!DNL Adobe]Experience Cloud中的其他產品整合。

## Akamai {#akamai}

[!DNL Audience Manager] 使 [](https://www.akamai.com/us/en/about/) 用Akamaito來托管及傳送來自我們自己的標籤管理平台(稱為 [!UICONTROL TIM (Tag Insertion Manager)])的容器代碼。不過，已逐步淘汰[!UICONTROL TIM]的程式碼部署，改用[!DNL Adobe Experience Platform Launch]。

## 控制資料庫{#control-database}

控制資料庫：

* 從入口網站處理用戶端輸入（例如建立特徵和目的地）。
* 將資料傳輸至Akamai，其中包括用來建立容器範本和發佈iFrame的目的地資料。
* 傳回UI報表系統的資料。
