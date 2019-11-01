---
description: 可讓您以程式設計方式處理目標功能的方法。
seo-description: 可讓您以程式設計方式處理目標功能的方法。
seo-title: 目標API方法
solution: Audience Manager
title: 目標API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 目標API方法 {#destination-api-methods}

可讓您以程式設計方式處理目標功能的方法。

<!-- c_destinations_api.xml -->

在Audience Manager中，目標是任何其他系統(廣告伺服器、廣告網 [!DNL DSP]路、Exchange、您自己的第一方Cookie等)您想要與其共用資料。

## 目標類型：URL和Cookie {#destination-types}

列出參數所使用的 `destinationType` 變數。 指 `push` 定或 `ADS` 以搭配或 [!UICONTROL URL] 使用 [!UICONTROL cookie destination]。 您無法使用 [!UICONTROL server-to-server destinations] 可用的目標方法 [!DNL API] 建立。

<!-- r_destination_types.xml -->

| API目標類型 | UI目標類型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [如何選擇目標類型](../../../features/destinations/destinations.md)

