---
description: 設定一個Google組，將您的Google市場活動經理資料檔案放入Audience Manager。 本節的內容概括了整合過程，並為您提供了指向Google市場活動經理資源的連結，以幫助您開始活動。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google市場活動經理資料檔案導入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 將Google市場活動經理資料檔案導入Audience Manager {#import-dcm-data-files-into-audience-manager}

設定 [!DNL Google] 組 [!DNL Google Campaign Manager] 資料檔案到Audience Manager。 本節的內容概括了整合過程，並提供了指向 [!DNL Google Campaign Manager] 資源，幫助您開始。

## 整合摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 取代 [!DNL DoubleClick for Advertisers] (DFA) 的替代方案。與外交部類似， [!DNL Google Campaign Manager] 客戶可以在 [!DNL Audience Manager]。 但 [!DNL Audience Manager] 無法直接訪問和導入 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 的子菜單。 若要匯入這些檔案，須由客戶自行為之。

但是，設定過程在 [DoubleClick Campaign Manager幫助](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)。 此外，您還可以查看下面列出的步驟以開始操作。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 資料檔案包含所有廣告商或客戶的資料。 如果需要忽略特定客戶端，則必須先編輯這些檔案，然後才能使這些檔案可用 [!DNL Audience Manager]。

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每天檢查並傳輸一次資料。 資料通常在 [!DNL Audience Manager] 24小時後。

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   組控制對您的 [!DNL Google Campaign Manager] 資料。 最終，您會邀請並添加 [!DNL Audience Manager] 到此組。

1. [驗證您的Google雲儲存狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google雲儲存包含保存您 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Tables]。 您需要設定儲存桶，或確保新組可以訪問現有資料儲存儲存桶。

1. [獲取資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   與 [!DNL Google Campaign Manager] 客戶經理或平台解決方案顧問。 它們將提供資料檔案的URL。 [!DNL Google] 可能會更改未來版本中儲存段和檔案名的格式。 同樣，與 [!DNL Google Campaign Manager] Account Manager確保您使用的格式正確。

1. [設定儲存段權限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   的 [!DNL Cloud Storage Manager] 允許您控制資料共用和儲存桶訪問。 授予您的組對包含您的 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 的子菜單。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共用 [!DNL Google Campaign Manager] 用戶ID被加密以保護隱私。 加密在資料傳輸檔案的末尾添加2列， `PartnerId1` 和 `PartnerId2`。 這些列包含特定於每個接收這些檔案的公司的編碼用戶ID。

   作為經授權的第三方， [!DNL Audience Manager] 可以 [!DNL Google Campaign Manager] 資料，但無法解碼ID。 但是，在 [!DNL Audience Manager] 另外，我們知道編碼的ID與我們的ID的匹配。 這意味著我們可以自信和準確地匹配和同步用戶。

   >[!NOTE]
   >無法導入 [!DNL Google Campaign Manager] 檔案 [!DNL Audience Manager] 如果您已與另外兩個第三方合作夥伴共用資料。

1. 邀請 [!DNL Audience Manager] 加入組。

   建立組並授予其對資料儲存段的訪問權限後，請邀請 [!DNL Audience Manager] 加入組。 向dfaaam@adobe.com發送邀請電子郵件。 確保包括步驟3中的資料檔案URL。 我們的內部團隊將在接受邀請後與您合作驗證訪問權限。 1。設定兩個資料源 [!DNL Google Campaign Manager] 資料 [!DNL Audience Manager] 用戶介面。

   命名資料源 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`。 在 [建立資料源](../../../features/manage-datasources.md#create-data-source) 工作流，將ID類型設定為 `Cookie`。 與我們的內部團隊共用兩個新資料源的ID。

1. 您可以輕鬆地從 [!DNL Google Campaign Manager] 導入的檔案 [!DNL Audience Manager]。 請參閱 [可操作的日誌檔案](../../../integration/media-data-integration/actionable-log-files.md) 問問 [!DNL Audience Manager] 咨詢顧問或客戶服務，為您啟用該功能。
