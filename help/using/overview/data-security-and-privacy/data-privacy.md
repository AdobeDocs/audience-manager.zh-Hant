---
description: 透過與消費者隱私權和選擇退出程序相關的公認最佳實務，說明 Audience Manager 整合及法規遵循。
seo-description: 透過與消費者隱私權和選擇退出程序相關的公認最佳實務，說明 Audience Manager 整合及法規遵循。
seo-title: 資料隱私權概述
solution: Audience Manager
title: 資料隱私權概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 83%

---


# 資料隱私權概述 {#data-privacy}

## 概述

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] 瞭解消費者以及與其互動的線上品牌之間關係的重要性。雙方都受益於匿名資料元素的透明交換：

* 消費者可獲得個人化內容、折扣產品優惠，以及簡化的使用者體驗。
* 品牌可獲得重要的收益流，以支援多種線上商業模型。

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## GDPR {#gdpr}

[一般資料保護規範 (GDPR)](https://eugdpr.org/) 為歐盟成員國引進了許多新的資料隱私權，包括&#x200B;**存取權**&#x200B;和&#x200B;**被遺忘權**。這表示貴公司已收集其個人資料的任何歐盟公民，都有權隨時請求存取或刪除其資料。若未能遵照這些請求採取動作，貴組織可能需支付數百萬美元的罰款。

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## CCPA {#ccpa}

2020 年 1 月 1 日生效的[加州消費者隱私法 (CCPA)](https://www.caprivacy.org/about)，為加州居民提供有關個人資訊的新權利，並對在加州經營事業的特定實體施加資料保護責任。

[!DNL CCPA] 為加州居民提供新的資料隱私權，包括存取和刪除其個人資料的權利，以及知悉其個人資料是否被出售或揭露 (以及向誰) 的權利。為符合規定， [!DNL CCPA]支援 [!DNL Audience Manager] 存 [!DNL CCPA] 取和刪 [除請求](data-privacy-requests.md)。

如需詳細資訊，請參閱 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy/opt-out.html)。

## 法規遵循 {#compliance}

[!DNL Audience Manager] 可協助您透過 [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html) 等隱私工具處理資料存取和刪除請求，以遵循特定隱私權法規所規範的義務。

此服務提供一個 [!DNL RESTful API] 和使用者介面，可協助您管理消費者資料請求。您可以使用 [Privacy Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html)，根據個別消費者的請求，提交存取和刪除個人資料的請求，協助您自動執行這部分的法規遵循義務。

雖然資料存取和刪除請求是透過 [Privacy Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html) 處理，但目前是透過 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 支援[選擇退出](data-privacy-requests.md#opt-out-requests)請求。如需詳細資訊，請參閱[資料隱私權請求](data-privacy-requests.md)。

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