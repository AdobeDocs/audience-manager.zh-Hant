---
description: 可讓您以程式設計方式使用目的地功能的方法。
seo-description: 可讓您以程式設計方式使用目的地功能的方法。
seo-title: 目標API方法
solution: Audience Manager
title: 目標API方法
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bb06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination API Methods {#destination-api-methods}

可讓您以程式設計方式使用目的地功能的方法。

<!-- c_destinations_api.xml -->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) 您要與其共用資料。

## Destination Types: URL and Cookie {#destination-types}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!DNL API] methods.

<!-- r_destination_types.xml -->

| API目的地類型 | UI目的地類型 |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_贊_ this]
>
>* [如何選擇目的地類型](../../../features/destinations/destinations.md)

