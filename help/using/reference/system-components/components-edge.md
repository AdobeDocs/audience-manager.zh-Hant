---
description: Audience Manager使用分佈式邊緣計算拓撲來滿足外部源對系統的需求。
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: 瞭解邊緣資料中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# 瞭解邊緣資料中心{#understanding-the-edge-data-center}

Audience Manager使用分佈式邊緣計算拓撲來滿足外部源對系統的需求。

## 邊緣資料中心基礎知識 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

邊緣計算可提供更高的效能，以響應分散的網際網路範圍的需求，因為「邊緣」本身是全球邊界。 這意味著 [!DNL Audience Manager] 動態地將處理位置置於最接近需求源的位置，並按盡可能短的路徑返回資料。 邊緣計算有助於保持網站效能，而這反過來又會保留您網站上的用戶體驗。 邊緣資料中心是移入和移出資料的關鍵網關 [!DNL Audience Manager]。

的 [!DNL Audience Manager] 邊緣資料中心包括：

* **核心伺服器：** 這些是 [!DNL Audience Manager] 系統。 它們更新並向邊緣伺服器提供資料。

* **邊緣伺服器：** 通常，這些是應用程式和/或Web伺服器。 他們坐在 [!DNL Audience Manager] 和網際網路。 邊緣伺服器，如 [!DNL DCS] 或Akamai系統，通常處理進出的資料和請求 [!DNL Audience Manager]。

* **負載平衡器：** 管理網際網路應用程式固有的不均衡計算/處理需求。 這些平衡器可防止伺服器群集過載，而其他伺服器群集則保持空閒。

下圖說明了Audience Manager邊緣資料中心環境。

![](assets/edge_data_center.png)

## 地理分佈與負載平衡 {#geo-dist-balance}

查看 [!DNL DCS] 部分 [資料收集元件](../../reference/system-components/components-data-collection.md)。
