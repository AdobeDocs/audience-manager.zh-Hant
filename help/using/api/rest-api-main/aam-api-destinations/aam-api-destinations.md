---
description: 可讓您以程式設計方式使用目標功能的方法。
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 目的地API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# 目的地API方法 {#destination-api-methods}

可讓您以程式設計方式使用目標功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目的地是您想要與其共用資料的任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路、exchange、您自己的第一方Cookie等） 任何其他系統（廣告伺服器、DSP）。

## 目的地型別： URL和Cookie {#destination-types}

列出`destinationType`引數使用的變數。 指定`push`或`ADS`以搭配[!UICONTROL URL]或[!UICONTROL cookie destination]使用。 您無法使用可用的目的地[!DNL API]方法建立[!UICONTROL server-to-server destinations]。

<!-- r_destination_types.xml -->

| API目的地型別 | UI目的地型別 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [如何選擇目的地型別](../../../features/destinations/destinations.md)
