---
description: 如何使用Google發佈者標籤(GPT)整合Google廣告管理器的概述。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 使用Google發佈者標籤(GPT)整合Google廣告經理
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 整合 [!DNL Google Ad Manager] （前稱DFP），使用Google發佈者標籤(GPT)

下面列出的文章概述了如何整合 [!DNL Google Ad Manager] 使用Google發佈者標籤(GPT)。 您可以使用伺服器端整合，也可以將GPT設定為目標，將Audience Manager段資料發送到 [!DNL Google Ad Manager]。 您還將瞭解攝取所需的步驟 [!DNL Google Ad Manager] 日誌檔案以在Audience Manager中報告。

* [使用Google發佈器標籤(GPT)向Google廣告管理器發送段的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   可將限定段發送到 [!DNL Google Ad Manager] 通過客戶端或通過伺服器端整合。 下面列出了有關這兩種方法的要求和相關資訊。

* [建立 GPT 目的地](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   可將限定段發送到 [!DNL Google Ad Manager] 通過客戶端（瀏覽器端）整合或伺服器端整合。 如果選擇客戶端整合，則必須為Audience Manager中的Google發佈者標籤建立基於cookie的目標。

* [修改 GPT setTargeting API 呼叫](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在調用Google發佈器標籤.setTargeting方法之前，添加if語句以檢查Audience ManagerCookie。

* [適用於 Google 發佈商廣告代碼的 Audience Manager 代碼](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是一個JavaScript函式，它讀取Audience Managercookie資料，並將該資訊發送到Google發佈器標籤。
