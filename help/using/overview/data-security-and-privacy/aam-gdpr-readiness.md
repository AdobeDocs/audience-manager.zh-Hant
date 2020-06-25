---
description: Audience Manager 客戶的 GDPR 整備指引
seo-description: Audience Manager 客戶的 GDPR 整備指引
seo-title: Audience Manager 客戶的 GDPR 整備指引
solution: Audience Manager
title: Audience Manager 客戶的 GDPR 整備指引
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Audience Manager 客戶 (資料控制者) 的 GDPR 整備指引 {#gdpr-readiness-guidance}

Audience Manager 建議在資料控管和組織整備方面主動採取措施。這可協助您確保妥善整體消費者資料以進行存取或刪除請求的相關程序，讓您的團隊能管理這些請求，而消費者 (資料主體) 將對您的品牌有正面且與眾不同的體驗。

Adobe 身為您的資料處理者，無法針對 GDPR 要求及取得資料主體同意的程序提供法律建議。請諮詢您的法律顧問，取得貴組織遵循 GDPR 的指引。

## 資料控管：開始思考如何在 Audience Manager 例項中管理您的消費者資料

* 檢閱行銷團隊用來識別 Audience Manager 中使用者的各種客戶 ID，以及是以何種資料來源儲存。這將能簡化請求 (例如刪除或存取) 的處理程序，因為您的團隊會先雜湊某些資料類型，再於 Audience Manager 中擷取這些資料。
* IDFA/GAID 行動裝置 ID 可用於 Audience Manager 中的多種使用案例。如果您使用 Adobe Mobile SDK，請務必提交 Experience Cloud ID (MID) 以及 IDFA/GAID，以確保 GDPR 回應完整。
* 隨著個人資料的定義越來越廣泛，IP 位址可能會被視為您所在地區的個人資料。主動與 Adobe Consulting 合作，將最後八位元模糊化。
* 決定資料主體提出 GDPR 請求時確認其身分的驗證原則和流程。
* 考慮使用[資料匯出控制](../../features/data-export-controls.md)來阻擋對存放個人資料的技術進行受眾啟用。例如，含有第三方資料的區段不應匯集至電子郵件服務提供者。設定 [!UICONTROL Data Export Control] 以確保組織中沒有人會意外啟用這些資料。
* 開始使用[以角色為基礎的存取控制](../../features/administration/administration-overview.md)，以確保適當的團隊能存取預期的資料。
* 請考慮適合資料的[保留期](../../faq/faq-privacy.md#data-retention-faq)。
* 審查身分連結、隱私權政策和法律要求，以瞭解何時何地適合將身分組繫結在一起；可透過 Audience Manager 的[設定檔合併規則](../../features/profile-merge-rules/merge-rules-overview.md)適當地使用。

## 組織整備：建立業務流程

* 識別接收/回應資料主體請求的流程。考慮建立自動化工具，用於將請求提交至 Audience Manager。
* 在您的 DMP 卓越中心內指定隱私權聯絡點。將貴組織的隱私權聯絡點與您的 Audience Manager 產品使用團隊連結，以瞭解如何管理輸入 ID 要求。
* 與資料主體共用資料之前先進行資料審查。記錄您所實作的步驟，協助您建立究責機制。
