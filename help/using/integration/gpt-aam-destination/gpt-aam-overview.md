---
description: 概觀如何使用Google Publisher標籤(GPT)整合Google廣告管理器。
seo-description: 概觀如何在Adobe Audience Manager(AAM)中使用Google Publisher標籤(GPT)整合Google Ad Manager。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher標籤(GPT)整合Google Ad Manager
title: 使用Google Publisher標籤(GPT)整合Google Ad Manager
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

下列文章提供如何使用Google Publisher標籤(GPT) [!DNL Google Ad Manager] 進行整合的概觀。 您可以使用伺服器端整合，或將GPT設為傳送Audience Manager區段資料的目標 [!DNL Google Ad Manager]。 您也將學習在Audience Manager中擷取記錄檔 [!DNL Google Ad Manager] 以進行報告的必要步驟。

* [使用Google Publisher標籤(GPT)將區段傳送至Google廣告管理員的需求與方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以透過用戶端或 [!DNL Google Ad Manager] 伺服器端整合，將符合資格的區段傳送至。 以下列出兩種方法的需求和相關資訊。

* [建立 GPT 目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以透過用戶端(瀏 [!DNL Google Ad Manager] 覽器端)整合或伺服器端整合，將合格的區段傳送至。 如果您選擇用戶端整合，您必須在Audience Manager中為Google Publisher標籤建立Cookie型目標。

* [修改 GPT setTargeting API 呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在呼叫Google Publisher標籤。setTargeting方法前，新增if陳述式以檢查Audience Manager Cookie。

* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是JavaScript函式，可讀取Audience Manager Cookie資料並將該資訊傳送至Google Publisher標籤。
