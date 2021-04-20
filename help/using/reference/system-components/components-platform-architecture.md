---
description: 此地圖包含主要的Audience Manager系統。 它以視覺化方式呈現資料在Audience Manager元件之間的流入、流出方式。
seo-description: 此地圖包含主要的Audience Manager系統。 它以視覺化方式呈現資料在Audience Manager元件之間的流入、流出方式。
seo-title: 平台架構資料流圖
solution: Audience Manager
title: 平台架構資料流圖
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# 平台架構：資料流量圖{#platform-architecture-data-flow-map}

此地圖包含主要的Audience Manager系統。 它以視覺化方式呈現資料在Audience Manager元件之間的流入、流出方式。

## 如何讀取此映射{#compmap}

<!-- 

c_compmap.xml

 -->

在映射中，灰色框包含[!DNL Audience Manager]系統。 有些元件完全內在，有些則位於[!DNL Audience Manager]與外部世界之間的邊界。 作為[!DNL Audience Manager]客戶，內部元件通常是透明的或無法訪問的。 不過，有時您可能會透過使用者介面或資料整合與這些系統互動。 位於包裝盒邊緣的系統會收集並傳送[!DNL Audience Manager]和外部世界之間的資料。

顏色定義流入和流出[!DNL Audience Manager]的資料類型。 綠色是客戶資料，藍色是客戶資料（造訪您網站的訪客），橙色是用於報告的資料。

如需系統說明和摘要，請參閱資料[action](../../reference/system-components/components-data-action.md)、[collection](../../reference/system-components/components-data-collection.md)、[processing](../../reference/system-components/components-data-processing.md)和[標籤管理](../../reference/system-components/components-tag-management.md)區段。

![](assets/flowmap.png)
