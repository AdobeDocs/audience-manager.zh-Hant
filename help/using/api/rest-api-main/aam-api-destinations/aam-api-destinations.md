---
description: 用於以寫程式方式處理目標功能的方法。
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: 目的地 API 方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 14%

---

# 目的地 API 方法 {#destination-api-methods}

用於以寫程式方式處理目標功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目標是任何其他系統(廣告伺服器、 [!DNL DSP]、ad network 、 exchange 、您自己的第一方cookie等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。

## 目標類型：URL和Cookie {#destination-types}

列出由 `destinationType` 的下界。 指定 `push` 或 `ADS` 與 [!UICONTROL URL] 或 [!UICONTROL cookie destination]。 無法建立 [!UICONTROL server-to-server destinations] 具有可用目標 [!DNL API] 的雙曲餘切值。

<!-- r_destination_types.xml -->

| API目標類型 | UI目標類型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [如何選擇目標類型](../../../features/destinations/destinations.md)

