---
description: Audience Manager使用分散式邊緣運算式拓撲來滿足外部來源對我們系統的需求。
seo-description: Audience Manager使用分散式邊緣運算式拓撲來滿足外部來源對我們系統的需求。
seo-title: 瞭解Edge Data Center
solution: Audience Manager
title: 瞭解Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager使用分散式邊緣運算式拓撲來滿足外部來源對我們系統的需求。

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge運算改善了回應擴散、全網際需求的效能，因為「Edge」本身是一個全域邊界。This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. Edge運算可協助維護網站效能，進而保留網站上的使用者體驗。The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

[!DNL Audience Manager] 邊緣資料中心包括：

* **核心伺服器：** 這些是主要 [!DNL Audience Manager] 系統。他們會更新並提供資料至邊緣伺服器。

* **Edge伺服器：** 通常，這些是應用程式和/或Web伺服器。They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **負載平衡器：** 管理網際網路應用程式中固有的運算/處理需求不一致。這些平衡器可防止叢集叢集超載，而有些伺服器則會閒置。

下圖說明Audience Manager Edge資料中心環境。

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
