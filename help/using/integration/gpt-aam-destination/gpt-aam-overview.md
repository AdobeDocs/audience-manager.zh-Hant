---
description: 概述如何使用Google發佈商代碼(GPT)整合Google廣告管理員。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 使用Google發佈商代碼(GPT)整合Google廣告管理員
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# 使用Google發佈商代碼(GPT)整合[!DNL Google Ad Manager] （原稱DFP）

下列文章概述如何使用Google發佈商代碼(GPT)整合[!DNL Google Ad Manager]。 您可以使用伺服器端整合，或將GPT設定為將Audience Manager區段資料傳送至[!DNL Google Ad Manager]的目的地。 您還將瞭解在Audience Manager中擷取[!DNL Google Ad Manager]個記錄檔以進行報告所需的步驟。

* [使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  您可以透過使用者端或伺服器端整合將合格的區段傳送至[!DNL Google Ad Manager]。 以下列出這兩種方法的需求和相關資訊。

* [建立GPT目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  您可以透過使用者端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至[!DNL Google Ad Manager]。 如果您選擇使用者端整合，則必須在Audience Manager中為Google發佈商廣告代碼建立Cookie型目的地。

* [修改GPT setTargeting API呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  新增if陳述式，在呼叫Audience Manager Publisher標籤.setTargeting方法之前檢查Google Cookie。

* [適用於Google發佈商廣告代碼的Audience Manager代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt是JavaScript函式，可讀取Audience Manager Cookie資料並將該資訊傳送至Google發佈商廣告代碼。
