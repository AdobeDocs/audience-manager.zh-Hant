---
description: 用於告知DIL它會在視窗載入後載入。
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowsLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
TQID: https://experienceleague.adobe.com/gLycCnA5nwb-91miUts-VvlFK4YfVxvju7GAl-NZW8w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 98
ht-degree: 2%

---

# isAddedPostWindowsLoad{#isaddedpostwindowload}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe不會在此時間點之後開發[!DNL DIL]。 建議客戶針對[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，應改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

用於告知DIL它會在視窗載入後載入。

**函式簽章：** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## 程式碼範例

```
DIL.isAddedPostWindowLoad();
```
