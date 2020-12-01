---
description: Audience Manager使用分散式邊緣運算拓撲，以滿足外部來源對我們系統的需求。
seo-description: Audience Manager使用分散式邊緣運算拓撲，以滿足外部來源對我們系統的需求。
seo-title: 瞭解邊緣資料中心
solution: Audience Manager
title: 瞭解邊緣資料中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# 瞭解邊緣資料中心{#understanding-the-edge-data-center}

Audience Manager使用分散式邊緣運算拓撲，以滿足外部來源對我們系統的需求。

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

邊緣運算可改善效能，以因應分散的網際網路需求，因為「邊緣」本身是全域邊界。 這表示[!DNL Audience Manager]會動態將處理位置最靠近需求來源，並透過最短的路徑傳回資料。 邊緣運算可協助維持網站效能，進而保留您網站的使用者體驗。 邊緣資料中心是用於在[!DNL Audience Manager]中移入和移出資料的關鍵網關。

[!DNL Audience Manager]邊緣資料中心包括：

* **核心伺服** 器：這些是主要 [!DNL Audience Manager] 系統。它們會更新並提供資料給邊緣伺服器。

* **邊緣伺服器：** 通常這些是應用程式和／或網頁伺服器。他們坐在[!DNL Audience Manager]和Internet之間的邊界上。 邊緣伺服器（例如[!DNL DCS]或Akamai系統）通常會處理流入或流出[!DNL Audience Manager]的資料和要求。

* **負載平衡器：管** 理網際網路應用程式中固有的不均衡運算／處理需求。這些平衡器可防止伺服器群集過載，而其他伺服器則保持空閒。

下圖說明Audience Manager邊緣資料中心環境。

![](assets/edge_data_center.png)

## 地理分佈與負載平衡{#geo-dist-balance}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)中的[!DNL DCS]章節。
