---
description: 設定Google群組，將您的Google Campaign Manager資料檔案帶入Audience Manager。 本節中的內容會摘要整合程式，並提供您Google Campaign Manager資源的連結，以協助您快速上手。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google Campaign Manager資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 將Google Campaign Manager資料檔案匯入Audience Manager {#import-dcm-data-files-into-audience-manager}

設定 [!DNL Google] 群組 [!DNL Google Campaign Manager] 資料檔案放入Audience Manager。 本節中的內容會摘要整合程式，並提供您的連結 [!DNL Google Campaign Manager] 協助您快速入門的資源。

## 整合摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 取代 [!DNL DoubleClick for Advertisers] (DFA) 的替代方案。與DFA類似， [!DNL Google Campaign Manager] 客戶可在 [!DNL Audience Manager]. 但 [!DNL Audience Manager] 無法直接存取和匯入 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 檔案。 若要匯入這些檔案，須由客戶自行為之。

不過，在 [DoubleClick促銷活動管理員說明](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). 此外，您也可以檢閱下列步驟以開始使用。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 資料檔案包含所有廣告商或用戶端的資料。 如果您需要忽略特定用戶端，則必須先編輯檔案，才能讓這些檔案可供使用 [!DNL Audience Manager].

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每天檢查資料並傳輸一次。 資料通常可在 [!DNL Audience Manager] 24小時後。

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   群組可控制您的 [!DNL Google Campaign Manager] 資料。 最終，您會邀請並新增 [!DNL Audience Manager] 加入此群組。

1. [驗證您的Google雲端儲存狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google雲端儲存包含保存您 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Tables]. 您需要設定貯體，或確認新群組擁有現有資料儲存貯體的存取權。

1. [取得資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   與您的 [!DNL Google Campaign Manager] 客戶經理或平台解決方案顧問。 它們會提供您資料檔案的URL。 [!DNL Google] 可能會在未來版本中變更貯體和檔案名稱的格式。 同樣地，與您的 [!DNL Google Campaign Manager] 客戶經理，確認您使用的格式正確。

1. [設定貯體權限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   此 [!DNL Cloud Storage Manager] 可讓您控制資料共用和貯體存取。 授予群組對包含您 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 檔案。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   共用 [!DNL Google Campaign Manager] 使用者ID會經過加密以保護隱私。 加密會在資料傳輸檔案的結尾添加2列， `PartnerId1` 和 `PartnerId2`. 這些欄包含每個接收這些檔案的公司專屬的編碼使用者ID。

   作為授權的第三方， [!DNL Audience Manager] 可接收 [!DNL Google Campaign Manager] 資料，但無法將ID解碼。 不過，在 [!DNL Audience Manager] 另外，我們也知道編碼ID與ID的相符程度。 這表示我們可以信賴且正確地比對及同步使用者。

   >[!NOTE]
   >您無法匯入 [!DNL Google Campaign Manager] 檔案 [!DNL Audience Manager] 如果您已與其他2個協力廠商合作夥伴共用資料。

1. 邀請 [!DNL Audience Manager] 加入群組。

   建立群組並授予其資料貯體的存取權後，請邀請 [!DNL Audience Manager] 加入群組。 請傳送邀請電子郵件至dfaaam@adobe.com。 請務必加入步驟3的資料檔案URL。 我們的內部團隊會在您接受邀請後與您合作，驗證存取權。 1.為 [!DNL Google Campaign Manager] 資料 [!DNL Audience Manager] 使用者介面。

   為資料來源命名 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`. 在 [建立資料來源](../../../features/manage-datasources.md#create-data-source) 工作流程，請將ID類型設為 `Cookie`. 與我們的內部團隊共用兩個新資料來源的ID。

1. 您可以輕鬆從 [!DNL Google Campaign Manager] 您導入的檔案 [!DNL Audience Manager]. 請參閱 [可操作的記錄檔](../../../integration/media-data-integration/actionable-log-files.md) 問 [!DNL Audience Manager] 顧問或客戶服務，為您啟用此功能。
