---
description: 用於讓DIL知道它會在視窗載入後載入。
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超出此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，則應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

用於讓DIL知道它會在視窗載入後載入。

**函式簽章：** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## 程式碼範例

```
DIL.isAddedPostWindowLoad();
```
