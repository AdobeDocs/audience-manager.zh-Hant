---
description: 說明類別層級DIL檔案中使用的驗證需求和文字格式。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: 類別層級 DIL API 快速入門
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# 類別層級 DIL API 快速入門{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

類別層級DILAPI可讓您以程式設計方式建立及使用Audience Manager物件。 類別層級API與其他執行個體層級函式搭配使用，以設定值或傳回資料。

## 類別層級 DIL API 快速入門 {#get-started}

說明類別層級中使用的驗證需求和文字格式 [!UICONTROL DIL] 說明檔案。

<!-- 

c_class_start.xml

 -->

使用類別層級時 [!UICONTROL DIL] API：

* 存取需要合作夥伴名稱和容器名稱空間ID (NSID)。 請聯絡您的Audience Manager客戶經理，以取得此資訊。
* 取代任何範例 *斜體* API檔案中的文字，其中包含值、ID或您使用的方法所需的其他變數。
* [!UICONTROL DIL] 將編碼資料寫入目的地Cookie。 例如，空格會編碼為 `%20` 和分號為 `%3B`.
