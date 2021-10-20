---
description: Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(已淘汰，改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management 元件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# Tag Management 元件{#tag-management-components}

Audience Manager標籤管理元件包括用戶端入口網站、Adobe Tag Manager(已淘汰，改用Adobe Experience Platform標籤)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [用戶端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 用戶端入口網站 {#client-portal}

用戶端入口網站是標籤和資料管理的主要使用者介面(UI)。 客戶可使用入口網站來處理標籤、建立特徵和區段、設定目的地，以及透過報表監控促銷活動績效。

## DIL/TIM容器 {#dil-tim}

此 [!UICONTROL DIL] 容器可部署 [!DNL Audience Manager] 資料收集程式碼。 [!UICONTROL TIM] 是過時的「標籤插入管理器」。 不再使用 [!DNL Audience Manager]. 請改為使用 [!DNL Audience Manager] 擴充功能 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 設定並產生您放置在清單頁面上的容器代碼。

## Data Integration Library (DIL) {#dil}

此 [資料資訊庫](../../dil/dil-overview.md) (DIL)是可從您的網站收集資料的獨立API模組。 [!UICONTROL DIL] 有助於避免編寫特殊程式碼以用於資料收集、整合、讀取cookie值及恢復頁面資料的需求。 [!UICONTROL DIL] 自動執行這些動作。 此外， [!UICONTROL DIL] 緊湊。 這是獨立的程式碼程式庫，可協助減少收集資訊所需的程式碼量。 最後， [!UICONTROL DIL] 協助您整合 [!DNL Audience Manager] 與 [!DNL Adobe] Experience Cloud。

## Akamai {#akamai}

[!DNL Audience Manager] uses [Akamai](https://www.akamai.com/us/en/about/) 從我們自己的標籤管理平台(稱為 [!UICONTROL TIM (Tag Insertion Manager)]. 不過，程式碼部署 [!UICONTROL TIM] 已逐步淘汰 [!DNL Adobe Experience Platform Tags].

## 控制資料庫 {#control-database}

控制資料庫：

* 從入口網站處理用戶端輸入（例如建立特徵和目的地）。
* 將資料傳輸至Akamai，其中包括用來建立容器範本和發佈iFrame的目的地資料。
* 傳回UI報表系統的資料。
