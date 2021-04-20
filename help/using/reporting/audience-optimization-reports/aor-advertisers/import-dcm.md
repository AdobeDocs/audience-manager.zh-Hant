---
description: 設定Google群組，將您的Google Campaign Manager資料檔案帶入Audience Manager。 本節的內容會摘要整合程式，並提供您Google Campaign Manager資源的連結，以協助您開始使用。
seo-description: 設定Google群組，將您的Google Campaign Manager資料檔案帶入Audience Manager。 本節的內容會摘要整合程式，並提供您Google Campaign Manager資源的連結，以協助您開始使用。
seo-title: 將Google促銷活動管理員資料檔案匯入Audience Manager
solution: Audience Manager
title: 將Google促銷活動管理員資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# 將Google促銷活動管理員資料檔案匯入Audience Manager{#import-dcm-data-files-into-audience-manager}

設定[!DNL Google]群組，將[!DNL Google Campaign Manager]資料檔案匯入Audience Manager。 本節內容摘要了整合程式，並提供您[!DNL Google Campaign Manager]資源的連結，以協助您開始使用。

## 整合摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 取代 [!DNL DoubleClick for Advertisers] (DFA) 的替代方案。與DFA類似，[!DNL Google Campaign Manager]客戶可以在[!DNL Audience Manager]中匯入、檢視及使用其資料。 但[!DNL Audience Manager]無法直接存取並匯入您的[!UICONTROL Data Transfer]和[!UICONTROL Match Table]檔案。 若要匯入這些檔案，須由客戶自行為之。

不過，[DoubleClick促銷活動管理員說明](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)中已詳細說明設定程式。 此外，您也可以檢視下列步驟以開始使用。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 資料檔案包含所有廣告商或客戶的資料。如果需要忽略特定客戶端，則必須先編輯檔案，然後才能將其提供給[!DNL Audience Manager]。

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每天檢查並傳輸資料一次。資料通常在[!DNL Audience Manager] 24小時後可用。

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   群組可控制對[!DNL Google Campaign Manager]資料的存取。 最後，您會邀請並新增[!DNL Audience Manager]至此群組。

1. [驗證您的Google雲端儲存空間狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google雲端儲存區包含包含您[!UICONTROL Data Transfer]和[!UICONTROL Match Tables]的資料儲存貯體。 您需要設定儲存貯體，或確保您的新群組擁有現有資料儲存貯體的存取權。

1. [取得資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   與您的[!DNL Google Campaign Manager]客戶經理或平台解決方案顧問合作。 他們會提供您資料檔案的URL。 [!DNL Google] 可能會在未來版本中變更儲存貯體和檔案名稱的格式。同樣地，請與您的[!DNL Google Campaign Manager]客戶經理合作，確定您使用的格式正確。

1. [設定儲存貯體權限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   [!DNL Cloud Storage Manager]可讓您控制資料共用和儲存貯體存取。 為您的群組提供對包含[!UICONTROL Data Transfer]和[!UICONTROL Match Table]檔案的儲存貯體的讀取存取權。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共用的[!DNL Google Campaign Manager]使用者ID會加密以保護隱私。 Encryption將2列添加到資料傳輸檔案`PartnerId1`和`PartnerId2`的末尾。 這些欄包含接收這些檔案的每家公司專屬的編碼使用者ID。

   作為授權的第三方，[!DNL Audience Manager]可接收[!DNL Google Campaign Manager]資料，但無法解碼ID。 不過，在[!DNL Audience Manager]一側，我們知道編碼ID與我們的ID如何相符。 這表示我們可以自信且精確地比對及同步使用者。

   >[!NOTE]
   >如果您已與其他2個第三方合作夥伴共用資料，則無法將[!DNL Google Campaign Manager]檔案匯入[!DNL Audience Manager]。

1. 邀請[!DNL Audience Manager]加入群組。

   建立群組並賦予其資料貯體存取權後，請邀請[!DNL Audience Manager]加入群組。 傳送邀請電子郵件至DFA-AAM@adobe.com。 請務必包含步驟3的資料檔案URL。 我們的內部團隊會與您合作，在接受邀請後確認存取權。 1.在[!DNL Audience Manager]使用者介面中為[!DNL Google Campaign Manager]資料設定兩個資料來源。

   將資料來源命名為`Advertiser Analytics: DCM Platform`和`Advertiser Analytics: AAM+DCM Platform`。 在[建立資料來源](../../../features/manage-datasources.md#create-data-source)工作流程中，將ID類型設為`Cookie`。 與內部團隊共用兩個新資料來源的ID。

1. 您可以輕鬆從匯入至[!DNL Audience Manager]的[!DNL Google Campaign Manager]檔案建立特徵。 請參閱[可操作的日誌檔案](../../../integration/media-data-integration/actionable-log-files.md)並要求您的[!DNL Audience Manager]顧問或客戶服務為您啟用該功能。
