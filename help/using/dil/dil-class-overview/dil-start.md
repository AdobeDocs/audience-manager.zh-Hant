---
description: 說明類別層級DIL檔案中使用的驗證需求和文字格式。
seo-description: 說明類別層級DIL檔案中使用的驗證需求和文字格式。
seo-title: 類別層級 DIL API 快速入門
solution: Audience Manager
title: 類別層級 DIL API 快速入門
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL實作
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 15%

---

# 類別層級 DIL API 快速入門{#getting-started-with-class-level-dil-apis}

類別層級的DILAPI可讓您以程式設計方式建立及使用Audience Manager物件。 類別層級API可與其他執行個體層級的函式搭配使用，以設定值或傳回資料。

## 類別層級 DIL API 快速入門 {#get-started}

描述類級[!UICONTROL DIL]文檔中使用的身份驗證要求和文本格式。

<!-- 

c_class_start.xml

 -->

使用類別層級[!UICONTROL DIL] API時：

* 存取需要合作夥伴名稱和容器命名空間ID(NSID)。 請連絡您的Audience Manager客戶經理以取得此資訊。
* 根據您使用的方法的需要，將API檔案中任何斜體&#x200B;*文字範例取代為值、ID或其他變數。*
* [!UICONTROL DIL] 將編碼資料寫入目的地cookie。例如，空格會編碼為`%20`，分號則編碼為`%3B`。
