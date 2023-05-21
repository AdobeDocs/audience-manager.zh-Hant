---
description: Audience Manager標籤管理元件包括客戶端門戶、Adobe Tag Manager(不建議使用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
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

Audience Manager標籤管理元件包括客戶端門戶、Adobe Tag Manager(不建議使用Adobe Experience Platform標籤)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含以下元件：

* [客戶端門戶](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [資料資訊庫(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 客戶端門戶 {#client-portal}

客戶端入口是用於標籤和資料管理的主要用戶介面(UI)。 客戶使用門戶來處理標籤、構建特徵和段、設定目標以及使用報告監控市場活動績效。

## DIL/TIM容器 {#dil-tim}

的 [!UICONTROL DIL] 容器部署 [!DNL Audience Manager] 資料收集代碼到您的網站。 [!UICONTROL TIM] 是已棄用的標籤插入管理器。 它不再被 [!DNL Audience Manager]。 相反，您使用 [!DNL Audience Manager] 擴展 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 配置並生成庫存中的頁面上的容器代碼。

## Data Integration Library (DIL) {#dil}

的 [資料資訊庫](../../dil/dil-overview.md) (DIL)是一個自包含的API模組，用於從您的網站收集資料。 [!UICONTROL DIL] 有助於消除為資料收集、整合、讀取cookie值和恢復頁資料編寫特殊代碼的需要。 [!UICONTROL DIL] 自動執行這些操作。 此外， [!UICONTROL DIL] 緊湊。 它是一個自包含的代碼庫，有助於減少收集資訊所需的代碼量。 終於， [!UICONTROL DIL] 幫助您整合 [!DNL Audience Manager] 和其他產品 [!DNL Adobe] Experience Cloud。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [阿卡邁](https://www.akamai.com/us/en/about/) 從我們自己的標籤管理平台托管和交付容器代碼 [!UICONTROL TIM (Tag Insertion Manager)]。 但是，代碼部署 [!UICONTROL TIM] 已逐步淘汰，轉而 [!DNL Adobe Experience Platform Tags]。

## 控制資料庫 {#control-database}

控制資料庫：

* 處理從門戶輸入的客戶端（例如，建立特徵和目標）。
* 將資料傳輸到Akamai，其中包括用於構建容器模板和目標發佈iFrame的資料。
* 返回UI報告系統的資料。
