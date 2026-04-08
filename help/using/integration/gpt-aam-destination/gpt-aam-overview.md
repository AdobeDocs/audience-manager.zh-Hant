---
description: 概述如何使用Google發佈商代碼(GPT)整合Google廣告管理員。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 使用Google發佈商代碼(GPT)整合Google廣告管理員
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
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
