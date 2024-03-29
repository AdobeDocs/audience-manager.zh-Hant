---
description: 透過與消費者隱私權和選擇退出程序相關的公認最佳實務，說明 Audience Manager 整合及法規遵循。
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: 資料隱私權概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 68%

---

# 資料隱私權概述 {#data-privacy}

## 概述

資料隱私文檔描述 [!DNL Audience Manager] 整合併遵守與消費者隱私和選擇退出程式相關的公認最佳做法。

[!DNL Audience Manager] 瞭解消費者以及與其互動的線上品牌之間關係的重要性。雙方都受益於匿名資料元素的透明交換：

* 消費者可獲得個人化內容、折扣產品優惠，以及簡化的使用者體驗。
* 品牌可獲得重要的收益流，以支援多種線上商業模型。

在我們繼續支援這個模式的同時， [!DNL Audience Manager] 繼續致力於為您提供工具，幫助您支援向消費者提供透明度和控制的能力，同時提供符合以下要求的個性化廣告 [線上行為廣告(OBA)自律原則](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)。

## [!DNL GDPR] {#gdpr}

[一般資料保護規範 (GDPR)](https://gdpr.eu/data-privacy/) 為歐盟成員國引進了許多新的資料隱私權，包括&#x200B;**存取權**&#x200B;和&#x200B;**被遺忘權**。這意味著 [!DNL EU] 其個人資料已被您的企業收集的公民可以請求隨時訪問或刪除其資料。 若未能遵照這些請求採取動作，貴組織可能需支付數百萬美元的罰款。

要遵守 [!DNL GDPR]。 [!DNL Audience Manager] 支援資料存取和刪除 [請求](data-privacy-requests.md)。

## [!DNL CCPA] {#ccpa}

2020 年 1 月 1 日生效的[加州消費者隱私法 (CCPA)](https://www.caprivacy.org/about)，為加州居民提供有關個人資訊的新權利，並對在加州經營事業的特定實體施加資料保護責任。

[!DNL CCPA] 為加州居民提供新的資料隱私權，包括存取和刪除其個人資料的權利，以及知悉其個人資料是否被出售或揭露 (以及向誰) 的權利。要遵守 [!DNL CCPA]。 [!DNL Audience Manager] 支援 [!DNL CCPA] 訪問和刪除 [請求](data-privacy-requests.md)。

如需詳細資訊，請參閱 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy/opt-out.html)。

## 法規遵循 {#compliance}

[!DNL Audience Manager] 可協助您透過 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) 等隱私工具處理資料存取和刪除請求，以遵循特定隱私權法規所規範的義務。

此服務提供一個 [!DNL RESTful API] 和使用者介面，可協助您管理消費者資料請求。您可以使用 [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)，根據個別消費者的請求，提交存取和刪除個人資料的請求，協助您自動執行這部分的法規遵循義務。

在通過Privacy Service處理資料存取和刪除請求時， [選擇退出請求](data-privacy-requests.md#opt-out-requests) 當前通過 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)。 如需詳細資訊，請參閱[資料隱私權請求](data-privacy-requests.md)。

## 相關概念 {#related-concepts}

* [資料隱私權請求](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [適用於 IAB TCF 的 Audience Manager 外掛程式](aam-iab-plugin.md)
* [Audience Manager 識別碼](data-privacy-ids.md)
* [CCPA 字彙表](aam-ccpa-glossary.md)
* [GDPR 字彙表](aam-gdpr-glossary.md)
* [針對目的地的 GDPR 考量事項](aam-gdpr-partners.md)
* [Audience Manager 客戶的 GDPR 整備指引](aam-gdpr-readiness.md)
* [資料控管](data-governance.md)
* [隱私權與資料保留常見問題集](../../faq/faq-privacy.md)
