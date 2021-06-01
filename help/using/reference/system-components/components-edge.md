---
description: Audience Manager使用分佈式邊緣計算拓撲，以滿足外部源對我們系統的需求。
seo-description: Audience Manager使用分佈式邊緣計算拓撲，以滿足外部源對我們系統的需求。
seo-title: 瞭解邊緣資料中心
solution: Audience Manager
title: 瞭解邊緣資料中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 系統元件
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 瞭解邊緣資料中心{#understanding-the-edge-data-center}

Audience Manager使用分佈式邊緣計算拓撲，以滿足外部源對我們系統的需求。

## 邊緣資料中心基本介紹{#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

邊緣計算可提供改善的效能，以響應分散的網際網路範圍需求，因為「邊緣」本身是全球邊界。 這表示[!DNL Audience Manager]會以動態方式將處理放置在最接近需求來源的位置，並以盡可能最短的路徑傳回資料。 邊緣運算有助於維持網站效能，進而保留您網站上的使用者體驗。 邊緣資料中心是將資料移入和移出[!DNL Audience Manager]的關鍵網關。

[!DNL Audience Manager]邊緣資料中心包括：

* **核心伺服器：** 這些是主要 [!DNL Audience Manager] 系統。它們會更新並向邊緣伺服器提供資料。

* **邊緣伺服器：** 通常是應用程式和/或Web伺服器。它們位於[!DNL Audience Manager]和Internet之間的邊界。 邊緣伺服器（例如[!DNL DCS]或Akamai系統）通常會處理流入或流出[!DNL Audience Manager]的資料和請求。

* **負載平衡器：** 管理網際網路應用程式中固有的不均衡計算/處理需求。這些平衡器防止了伺服器群集在其他群集保持空閒時過載。

下圖說明Audience Manager邊緣資料中心環境。

![](assets/edge_data_center.png)

## 地理分佈與負載平衡{#geo-dist-balance}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)中的[!DNL DCS]區段。
