---
description: 說明驗證需求和類別層級DIL檔案中使用的文字格式。
seo-description: 說明驗證需求和類別層級DIL檔案中使用的文字格式。
seo-title: 類別層級 DIL API 快速入門
solution: Audience Manager
title: 類別層級 DIL API 快速入門
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 15%

---


# 類別層級 DIL API 快速入門{#getting-started-with-class-level-dil-apis}

類別層級的DIL API可讓您以程式設計方式建立及使用Audience Manager物件。 類別層級的API可與其他例項層級的函式搭配使用，以設定值或傳回資料。

## 類別層級 DIL API 快速入門 {#get-started}

說明驗證要求以及類別級[!UICONTROL DIL]檔案中使用的文字格式。

<!-- 

c_class_start.xml

 -->

使用類別級別[!UICONTROL DIL] API時：

* 存取需要合作夥伴名稱和容器名稱空間ID(NSID)。 請連絡您的Audience Manager客戶經理以取得此資訊。
* 使用值、ID或您使用之方法所需的其他變數，取代API檔案中任何斜體&#x200B;*文字範例。*
* [!UICONTROL DIL] 將編碼資料寫入目標Cookie。例如，空格會編碼為`%20`，分號則編碼為`%3B`。

