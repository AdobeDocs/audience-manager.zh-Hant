---
description: 說明類別層級DIL檔案中使用的驗證需求和文字格式。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: 類別層級DILAPI快速入門
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# 類別層級DILAPI快速入門{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe在此點之後不會開發[!DNL DIL]。 建議客戶針對[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)。

類別層級DILAPI可讓您以程式設計方式建立及使用Audience Manager物件。 類別層級API與其他執行個體層級函式搭配使用，以設定值或傳回資料。

## 類別層級DILAPI快速入門 {#get-started}

說明類別層級[!UICONTROL DIL]檔案中使用的驗證需求和文字格式。

<!-- 

c_class_start.xml

 -->

使用類別層級[!UICONTROL DIL] API時：

* 存取需要合作夥伴名稱和容器名稱空間ID (NSID)。 請連絡您的Audience Manager客戶經理，以取得此資訊。
* 將API檔案中的任何範例&#x200B;*斜體化*&#x200B;文字取代為您使用的方法所需的值、識別碼或其他變數。
* [!UICONTROL DIL]會將已編碼的資料寫入目的地Cookie。 例如，空格會編碼為`%20`，分號會編碼為`%3B`。
