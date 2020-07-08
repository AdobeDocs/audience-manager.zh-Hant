---
description: 設定Google群組，將您的Google Campaign Manager資料檔案匯入Audience Manager。 本節的內容會摘要整合程式，並提供您Google Campaign Manager資源的連結，以協助您開始使用。
seo-description: 設定Google群組，將您的Google Campaign Manager資料檔案匯入Audience Manager。 本節的內容會摘要整合程式，並提供您Google Campaign Manager資源的連結，以協助您開始使用。
seo-title: 將Google Campaign Manager資料檔案匯入Audience Manager
solution: Audience Manager
title: 將Google Campaign Manager資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# 將Google Campaign Manager資料檔案匯入Audience Manager {#import-dcm-data-files-into-audience-manager}

設定群組 [!DNL Google] ，將您的資料 [!DNL Google Campaign Manager] 檔案匯入Audience Manager。 本節內容摘要了整合程式，並提供您資源的連結， [!DNL Google Campaign Manager] 以協助您開始使用。

## 整合摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 取代 [!DNL DoubleClick for Advertisers] (DFA) 的替代方案。Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. 但無 [!DNL Audience Manager] 法直接存取和匯入您 [!UICONTROL Data Transfer] 的和 [!UICONTROL Match Table] 檔案。 若要匯入這些檔案，須由客戶自行為之。

不過，DoubleClick促銷活動管理員說明中已詳 [細說明設定程式](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)。 此外，您也可以檢視下列步驟以開始使用。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 資料檔案包含所有廣告商或客戶的資料。 如果您需要省略特定用戶端，則必須先編輯檔案，才能將檔案提供給 [!DNL Audience Manager]。

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每天檢查並傳輸資料一次。 資料通常在24小時 [!DNL Audience Manager] 後才可用。

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   群組可控制您資料的存 [!DNL Google Campaign Manager] 取權。 最終，您會邀請並加入 [!DNL Audience Manager] 此群組。

1. [驗證您的Google雲端儲存空間狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google雲端儲存區包含包含您和的資料儲 [!UICONTROL Data Transfer] 存貯體 [!UICONTROL Match Tables]。 您需要設定儲存貯體，或確保您的新群組擁有現有資料儲存貯體的存取權。

1. [取得資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   與您的客戶經 [!DNL Google Campaign Manager] 理或平台解決方案顧問合作。 他們會提供您資料檔案的URL。 [!DNL Google] 可能會在未來版本中變更儲存貯體和檔案名稱的格式。 同樣地，請與您的 [!DNL Google Campaign Manager] 客戶經理合作，確定您使用的格式正確。

1. [設定儲存貯體權限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   可讓您 [!DNL Cloud Storage Manager] 控制資料共用和儲存貯體存取。 為您的群組提供儲存貯體的讀取存取權，儲存貯體中包含您 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 檔案。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共用 [!DNL Google Campaign Manager] 使用者ID會加密以保護隱私。 Encryption將2欄新增至資料傳輸檔案的結尾， `PartnerId1` 而 `PartnerId2`且 這些欄包含接收這些檔案的每家公司專屬的編碼使用者ID。

   身為授權的第三方，可 [!DNL Audience Manager] 以接收 [!DNL Google Campaign Manager] 資料，但無法解碼ID。 但是，我們 [!DNL Audience Manager] 知道編碼ID與我們的ID如何相符。 這表示我們可以自信且精確地比對及同步使用者。

   >[!NOTE]
   >如果您已 [!DNL Google Campaign Manager] 與其他 [!DNL Audience Manager] 兩個第三方合作夥伴共用資料，則無法將檔案匯入。

1. 邀 [!DNL Audience Manager] 請加入群組。

   建立群組並賦予其存取資料貯體的權限後，請邀 [!DNL Audience Manager] 請加入群組。 傳送邀請電子郵件至DFA-AAM@adobe.com。 請務必包含步驟3的資料檔案URL。 我們的內部團隊會與您合作，在接受邀請後確認存取權。 1. 在使用者介面中設定兩 [!DNL Google Campaign Manager] 個資料 [!DNL Audience Manager] 來源。

   命名資料來源 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`。 在「建 [立資料來源](../../../features/manage-datasources.md#create-data-source) 」工作流程中，將ID類型設為 `Cookie`。 與內部團隊共用兩個新資料來源的ID。

1. 您可以輕鬆從匯入的檔 [!DNL Google Campaign Manager] 案建立特徵 [!DNL Audience Manager]。 請參 [閱可操作的記錄檔](../../../integration/media-data-integration/actionable-log-files.md) ，並要求您 [!DNL Audience Manager] 的顧問或客戶服務為您啟用此功能。
