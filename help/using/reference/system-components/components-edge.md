---
description: Audience Manager使用分散式邊緣運算拓撲，滿足外部來源對我們的系統的需求。
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: 瞭解Edge資料中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 瞭解Edge資料中心{#understanding-the-edge-data-center}

Audience Manager使用分散式邊緣運算拓撲，滿足外部來源對我們的系統的需求。

## Edge資料中心基本需知 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge運算提供更優異的效能，因應網際網路廣泛擴散的需求，因為「邊緣」本身就是全球邊界。 這表示[!DNL Audience Manager]會以動態方式將處理置於最接近需求來源的位置，並以最短的可能路徑傳回資料。 Edge運算有助於維持網站效能，進而保留網站上的使用者體驗。 邊緣資料中心是移入和移出[!DNL Audience Manager]的資料的重要閘道。

[!DNL Audience Manager]邊緣資料中心包含：

* **核心伺服器：**&#x200B;這些是主要[!DNL Audience Manager]系統。 它們會更新並提供資料給Edge伺服器。

* **Edge伺服器：**&#x200B;通常是指應用程式和/或Web伺服器。 它們位於[!DNL Audience Manager]與網際網路之間的邊界。 Edge伺服器（例如[!DNL DCS]或Akamai系統）通常會處理流入和流出[!DNL Audience Manager]的資料和請求。

* **負載平衡器：**&#x200B;管理網際網路應用程式本身不均衡的運算/處理需求。 這些平衡器可防止伺服器叢集超載，而其他叢集則維持閒置狀態。

下圖說明Audience Manager邊緣資料中心環境。

![](assets/edge_data_center.png)

## 地理分佈與負載平衡 {#geo-dist-balance}

檢視[資料收集元件](../../reference/system-components/components-data-collection.md)中的[!DNL DCS]區段。
