---
description: 概觀如何使用Google Publisher標籤(GPT)整合DFP。
seo-description: 概觀如何使用Adobe Audience Manager(AAM)中的Google Publisher標籤(GPT)整合DFP。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher標籤(GPT)整合DFP
title: 使用Google Publisher標籤(GPT)整合DFP
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# 使用Google Publisher標籤(GPT)整合DFP

下列文章提供如何使用Google Publisher標籤(GPT)整合DFP的概觀。 您可以使用伺服器端整合，或將GPT設定為目的地，以傳送Audience manager區段資料至DFP。 您也將學習在Audience manager中擷取DFP記錄檔以進行報告的必要步驟。

* [使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以透過用戶端或伺服器端整合，將合格的區段傳送至DFP。 以下列出兩種方法的需求和相關資訊。

* [建立GPT目標](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至DFP。 如果您選擇用戶端整合，您必須在Audience manager中為Google Publisher標籤建立Cookie型目標。

* [修改GPT setTargeting API呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience Manager Cookie。

* [Google Publisher標籤的Audience Manager代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是JavaScript函式，可讀取Audience Manager cookie資料並將該資訊傳送至Google Publisher標籤。
