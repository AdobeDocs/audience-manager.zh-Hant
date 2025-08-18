---
description: 設定Google群組，將您的Google Campaign Manager資料檔案匯入Audience Manager。 本節中的內容概述整合程式，並提供Google Campaign Manager資源的連結，以協助您開始使用。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google Campaign Manager資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# 將Google Campaign Manager資料檔案匯入Audience Manager {#import-dcm-data-files-into-audience-manager}

設定[!DNL Google]群組，將您的[!DNL Google Campaign Manager]資料檔案匯入Audience Manager。 本節中的內容摘要說明整合程式，並提供您連結[!DNL Google Campaign Manager]資源，協助您開始使用。

## 整合摘要

[!DNL Google Campaign Manager]是[!DNL Google]的[!DNL DoubleClick for Advertisers] (DFA)替代專案。 與DFA類似，[!DNL Google Campaign Manager]客戶可以在[!DNL Audience Manager]中匯入、檢視和處理其資料。 但[!DNL Audience Manager]無法直接存取及匯入您的[!UICONTROL Data Transfer]與[!UICONTROL Match Table]檔案。 若要匯入這些檔案，須由客戶自行為之。

不過，[DoubleClick Campaign Manager說明](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)已完整記錄此設定程式。 您也可以檢閱下列步驟以開始。

>[!CAUTION]
>
>[!DNL Google Campaign Manager]個資料檔案包含您所有廣告商或使用者端的資料。 如果您需要省略特定使用者端，則必須先編輯檔案，才能讓[!DNL Audience Manager]使用。

## 資料傳輸頻率和可用性

[!DNL Audience Manager]每天檢查並傳輸資料一次。 資料通常可在24小時後的[!DNL Audience Manager]內使用。

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456)。

   群組可控制您[!DNL Google Campaign Manager]資料的存取權。 最終，您將邀請並新增[!DNL Audience Manager]到此群組。

1. [驗證您的Google雲端儲存空間狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)。

   Google雲端儲存空間包含儲存您[!UICONTROL Data Transfer]和[!UICONTROL Match Tables]的資料貯體。 您需要設定貯體，或確認您的新群組有權存取現有的資料儲存貯體。

1. [取得資料檔URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)。

   請與您的[!DNL Google Campaign Manager]客戶經理或平台解決方案顧問合作。 它們會提供您資料檔案的URL。 [!DNL Google]可能會變更未來版本中儲存貯體和檔案名稱的格式。 再次強調，請與您的[!DNL Google Campaign Manager]帳戶管理員合作，確定您使用正確的格式。

1. [設定儲存貯體許可權](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   [!DNL Cloud Storage Manager]可讓您控制資料共用和儲存貯體存取。 授予群組對包含您的[!UICONTROL Data Transfer]和[!UICONTROL Match Table]檔案之儲存貯體的讀取存取權。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   已加密共用的[!DNL Google Campaign Manager]使用者識別碼以保護隱私權。 加密在資料傳輸檔案的結尾新增2個資料行，`PartnerId1`和`PartnerId2`。 這些欄包含每個接收這些檔案的公司專屬的編碼使用者ID。

   作為授權第三方，[!DNL Audience Manager]可以接收[!DNL Google Campaign Manager]資料，但無法將ID解碼。 不過，在[!DNL Audience Manager]端，我們知道編碼ID和我們的ID如何相符。 這表示我們可以信賴度並準確地比對及同步使用者。

   >[!NOTE]
   >如果您已與2個其他協力廠商合作夥伴共用資料，則無法將[!DNL Google Campaign Manager]檔案匯入[!DNL Audience Manager]。

1. 邀請[!DNL Audience Manager]加入群組。

   在您建立群組並授予其資料儲存貯體的存取權後，請邀請[!DNL Audience Manager]加入群組。 傳送邀請電子郵件至dfaaam@adobe.com。 請務必加入步驟3中的資料檔案URL。 我們的內部團隊會在接受邀請後，與您合作以驗證存取權。 1.在[!DNL Google Campaign Manager]使用者介面中為[!DNL Audience Manager]資料設定兩個資料來源。

   為資料來源命名`Advertiser Analytics: DCM Platform`和`Advertiser Analytics: AAM+DCM Platform`。 在[建立資料來源](../../../features/manage-datasources.md#create-data-source)工作流程中，將ID型別設定為`Cookie`。 與我們的內部團隊共用兩個新資料來源的ID。

1. 您可以從匯入[!DNL Google Campaign Manager]的[!DNL Audience Manager]檔案中輕鬆建立特徵。 檢視[可操作的記錄檔](../../../integration/media-data-integration/actionable-log-files.md)，並要求您的[!DNL Audience Manager]顧問或客戶服務為您啟用此功能。
