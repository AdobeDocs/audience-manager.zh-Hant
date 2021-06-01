---
description: 概述如何使用Google發佈商代碼(GPT)整合Google Ad Manager。
seo-description: 概略說明如何在Adobe Audience Manager(AAM)中使用Google發佈商代碼(GPT)整合Google Ad Manager。
seo-title: 在Adobe Audience Manager(AAM)中使用Google發佈商代碼(GPT)整合Google Ad Manager
title: 使用Google發佈商代碼(GPT)整合Google廣告管理員
feature: 協力廠商整合
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 使用Google發佈商代碼(GPT)整合[!DNL Google Ad Manager]（原稱DFP）

下列文章概述如何使用Google發佈商代碼(GPT)整合[!DNL Google Ad Manager]。 您可以使用伺服器端整合，也可以設定GPT作為傳送Audience Manager區段資料至[!DNL Google Ad Manager]的目的地。 您也將了解內嵌[!DNL Google Ad Manager]記錄檔以進行Audience Manager報告的所需步驟。

* [使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以透過用戶端或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]。 以下列出兩種方法的需求和相關資訊。

* [建立 GPT 目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]。 如果您選擇用戶端整合，則必須為Audience Manager中的Google發佈商標籤建立Cookie型目的地。

* [修改 GPT setTargeting API 呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在呼叫Google Publisher Tag .setTargeting方法之前，新增if陳述式以檢查Audience ManagerCookie。

* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是JavaScript函式，可讀取Audience ManagerCookie資料並將該資訊傳送至Google發佈商標籤。
