---
description: 此地圖包含主要Audience Manager系統。 以視覺化方式呈現資料在Audience Manager元件中流入、流出和之間的流動情形。
seo-description: 此地圖包含主要Audience Manager系統。 以視覺化方式呈現資料在Audience Manager元件中流入、流出和之間的流動情形。
seo-title: 平台架構資料流圖
solution: Audience Manager
title: 平台架構資料流圖
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 系統元件
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# 平台架構：資料流量圖{#platform-architecture-data-flow-map}

此地圖包含主要Audience Manager系統。 以視覺化方式呈現資料在Audience Manager元件中流入、流出和之間的流動情形。

## 如何閱讀此地圖 {#compmap}

<!-- 

c_compmap.xml

 -->

在地圖中，灰色框包含[!DNL Audience Manager]系統。 有些元件完全為內部元件，而其他元件則位於[!DNL Audience Manager]與外部世界之間的邊界。 作為[!DNL Audience Manager]客戶，內部元件通常是透明的或無法存取的。 不過，有時候您可能會透過使用者介面或資料整合與這些系統互動。 盒邊緣的系統會收集並傳送[!DNL Audience Manager]與外部世界之間的資料。

顏色定義流入和流出[!DNL Audience Manager]的資料類型。 綠色代表用戶端資料，藍色代表客戶資料（造訪您網站的人員），橘色代表用於報告的資料。

有關係統說明和摘要，請參閱資料[action](../../reference/system-components/components-data-action.md)、[collection](../../reference/system-components/components-data-collection.md)、[processing](../../reference/system-components/components-data-processing.md)和[標籤管理](../../reference/system-components/components-tag-management.md)部分。

![](assets/flowmap.png)
