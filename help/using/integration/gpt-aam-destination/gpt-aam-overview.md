---
description: 說明如何使用Google Publisher標記(GPT)整合DFP。
seo-description: 說明如何使用Adobe Audience Manager(AAM)中的Google Publisher標記(GPT)整合DFP。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher標記(GPT)整合DFP
title: 使用Google Publisher標記(GPT)整合DFP
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# 使用Google Publisher標記(GPT)整合DFP

以下列出的文章概述如何使用Google Publisher標記(GPT)整合DFP。您可以使用伺服器端整合，也可以設定GPT作為目的地，將Audience Manager區段資料傳送至DFP。您也將瞭解收錄DFP記錄檔以便在Audience Manager中報告的必要步驟。

* [使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以透過用戶端或伺服器端整合，將合格區段傳送至DFP。以下列出兩種方法的需求和相關資訊。

* [建立GPT目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以透過用戶端(瀏覽器端)整合或伺服器端整合，將合格的區段傳送至DFP。如果您選擇用戶端整合，您必須在Audience Manager中建立Google Publisher標記的Cookie目的地。

* [修改GPT Settargeting API呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   新增if陳述式以檢查Audience Manager Cookie，然後呼叫Google Publisher Tag. setTargeting方法。

* [Google Publisher標記的Audience Manager代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt是一個JavaScript函數，可讀取Audience Manager Cookie資料，並將該資訊傳送至Google Publisher標記。
