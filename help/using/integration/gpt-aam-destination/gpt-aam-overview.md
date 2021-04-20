---
description: 概觀如何使用Google Publisher標籤(GPT)整合Google廣告管理器。
seo-description: 概觀如何使用Adobe Audience Manager()的Google Publisher標籤(GPT)整合Google廣告AAM管理員。
seo-title: 使用Adobe Audience Manager()的Google Publisher Tags(GPT)整合Google Ad Manager(AAMGoogle Publisher Tags)
title: 使用Google Publisher標籤(GPT)整合Google Ad Manager
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 使用Google Publisher標籤(GPT)整合[!DNL Google Ad Manager]（先前稱為DFP）

下列文章提供如何使用Google Publisher標籤(GPT)整合[!DNL Google Ad Manager]的概觀。 您可以使用伺服器端整合，或將GPT設為目的地，以傳送Audience Manager區段資料至[!DNL Google Ad Manager]。 您還將學習如何收錄[!DNL Google Ad Manager]記錄檔，以便在Audience Manager中報告。

* [使用Google Publisher標籤(GPT)將區段傳送至Google廣告管理員的需求與方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以透過用戶端或伺服器端整合，將合格的區段傳送至[!DNL Google Ad Manager]。 以下列出兩種方法的需求和相關資訊。

* [建立 GPT 目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]。 如果您選擇用戶端整合，則必須為Audience Manager中的Google Publisher標籤建立Cookie型目標。

* [修改 GPT setTargeting API 呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience ManagerCookie。

* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是JavaScript函式，可讀取Audience ManagerCookie資料並將該資訊傳送至Google Publisher標籤。
