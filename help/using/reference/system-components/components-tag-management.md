---
description: Audience Manager標籤管理元件包括使用者端入口網站、Adobe Tag Manager (已淘汰，改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management元件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Tag Management元件{#tag-management-components}

Audience Manager標籤管理元件包括使用者端入口網站、Adobe Tag Manager (已淘汰，改用Adobe Experience Platform標籤)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [使用者端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制項資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 使用者端入口網站 {#client-portal}

使用者端入口網站是標籤和資料管理的主要使用者介面(UI)。 客戶可使用此入口網站處理標籤、建立特徵和區段、設定目的地，以及透過報表監控行銷活動績效。

## DIL/TIM容器 {#dil-tim}

[!UICONTROL DIL]容器可協助將[!DNL Audience Manager]資料收集程式碼部署到您的網站。 [!UICONTROL TIM]是已過時的標籤插入管理員。 [!DNL Audience Manager]已不再使用它。 請改用[Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html)中的[!DNL Audience Manager]擴充功能來設定並產生您放置在詳細目錄頁面的容器代碼。

## Data Integration Library (DIL) {#dil}

[資料資訊庫](../../dil/dil-overview.md) (DIL)是從網站收集資料的自包含API模組。 [!UICONTROL DIL]可協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值以及復原頁面資料等作業。 [!UICONTROL DIL]會自動執行這些動作。 此外，[!UICONTROL DIL]是精簡的。 這是獨立的程式碼程式庫，有助於減少收集資訊所需的程式碼數量。 最後，[!UICONTROL DIL]會協助您將[!DNL Audience Manager]與[!DNL Adobe]Experience Cloud中的其他產品整合。

## Akamai {#akamai}

[!DNL Audience Manager]使用[Akamai](https://www.akamai.com/us/en/about/)，從我們自己的標籤管理平台（稱為[!UICONTROL TIM (Tag Insertion Manager)]）代管及傳遞容器程式碼。 不過，使用[!UICONTROL TIM]的程式碼部署已逐步淘汰，而改為[!DNL Adobe Experience Platform Tags]。

## 控制項資料庫 {#control-database}

控制項資料庫：

* 處理來自入口網站的使用者端輸入（例如，建立特徵和目的地）。
* 將資料傳輸至Akamai，其中包括用來建置容器範本和目的地發佈iFrame的資料。
* 傳回UI報表系統的資料。
