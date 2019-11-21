---
description: Audience manager客戶的GDPR準備指引
seo-description: Audience manager客戶的GDPR準備指引
seo-title: Audience manager客戶的GDPR準備指引
solution: Audience Manager
title: Audience manager客戶的GDPR準備指引
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Audience manager客戶（資料掌控者）的GDPR準備指引 {#gdpr-readiness-guidance}

Audience manager建議在資料治理和組織準備方面採取主動行動。 這可協助您確保將消費者資料組織用於存取或刪除要求的相關程式，讓您的團隊能夠管理這些要求，而您的消費者（資料主體）對您的品牌將擁有正面、與眾不同的體驗。

身為您的資料處理者，Adobe無法就GDPR要求及取得資料主體同意的程式提供法律建議。 請洽詢您的法律顧問，以取得貴組織遵守GDPR的指引。

## 資料治理：開始思考如何在Audience manager例項中管理您的消費者資料

* 檢閱行銷團隊用來識別Audience manager中使用者的各種客戶ID，以及其儲存資料來源。 這將簡化請求的處理（例如刪除或存取），因為您的團隊在Audience manager中擷取某些資料類型之前，會先雜湊某些資料類型。
* IDFA/GAID行動裝置ID用於Audience manager的多個使用案例。 如果您使用Adobe Mobile SDK，請務必提交Experience Cloud ID(MID)以及IDFA/GAID，以確保GDPR回應完整。
* 隨著個人資料的定義越來越廣泛，IP位址可能會被視為您所在地區的個人資料。 主動與Adobe Consulting合作，模糊最後八位元。
* 確定在資料主體提出GDPR請求時確認其身分的驗證／驗證策略和流程。
* 請考慮使 [用「資料匯出控制](../../features/data-export-controls.md) 」來封鎖對儲存個人資料之技術的受眾啟動。 例如，具有第三方資料的區段不應匯集至電子郵件服務供應商。 設定以 [!UICONTROL Data Export Control] 確保組織中沒有人會意外啟用此資料。
* 開始使用 [基於角色的訪問控制](../../features/administration/administration-overview.md) ，以確保適當的團隊能夠訪問預定的資料。
* 請考慮適 [合資料的](../../faq/faq-privacy.md#data-retention-faq) 「保留期」。
* 審查身分連結、隱私權政策和法律要求，以瞭解何時何地將身分組系結在一起；透過Audience Manager的設定檔合併規 [則適當使用](../../features/profile-merge-rules/merge-rules-overview.md)。

## 組織就緒性：建立業務流程

* 識別接收／回應資料主體要求的程式。 考慮建立自動化工具，將請求提交至Audience Manager。
* 在您的DMP卓越中心指定隱私權聯絡點。 將貴組織的隱私權聯絡點與您的Audience manager產品使用團隊連絡，以瞭解如何管理輸入ID需求。
* 在與資料主體共用之前先進行資料審查。 記錄您所採取的步驟，協助您建立責任。
