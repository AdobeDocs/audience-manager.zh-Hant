---
description: 此地圖包含主要的Audience Manager系統。 它以視覺化方式呈現資料如何流入、流出及在Audience Manager元件之間流動。
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Platform架構資料流程圖
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# 平台架構：資料流量圖{#platform-architecture-data-flow-map}

此地圖包含主要的Audience Manager系統。 它以視覺化方式呈現資料如何流入、流出及在Audience Manager元件之間流動。

## 如何讀取此地圖 {#compmap}

<!-- 

c_compmap.xml

 -->

在地圖中，灰色方塊包含[!DNL Audience Manager]個系統。 有些元件完全是內部元件，而其他元件則位於[!DNL Audience Manager]和外部世界的邊界上。 作為[!DNL Audience Manager]客戶，內部元件通常為透明或無法存取。 不過，有時您可以透過使用者介面或資料整合來與這些系統互動。 位於盒子邊緣的系統會在[!DNL Audience Manager]和外部世界之間收集並傳送資料。

顏色定義進出於[!DNL Audience Manager]的資料型別。 綠色代表使用者端資料，藍色代表客戶資料（造訪您網站的人），橘色代表用於報告的資料。

如需系統說明與摘要，請參閱資料[動作](../../reference/system-components/components-data-action.md)、[集合](../../reference/system-components/components-data-collection.md)、[處理](../../reference/system-components/components-data-processing.md)以及[標籤管理](../../reference/system-components/components-tag-management.md)區段。

![](assets/flowmap.png)
