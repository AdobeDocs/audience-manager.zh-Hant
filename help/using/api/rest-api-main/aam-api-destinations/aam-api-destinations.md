---
description: 可讓您以程式設計方式使用目標功能的方法。
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 目的地API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: 'https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: 7dee9651-deb5-5d4d-acfd-fbc10040467f
    internal-label: API
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 0%
---
# 目的地API方法 {#destination-api-methods}

可讓您以程式設計方式使用目標功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目的地是您想要與其共用資料的 [!DNL DSP]任何其他系統（廣告伺服器、DSP）。

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
