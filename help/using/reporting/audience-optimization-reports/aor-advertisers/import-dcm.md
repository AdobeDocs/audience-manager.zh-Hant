---
description: 設定Google群組，將您的DoubleClick Campaign Manager(DCM)資料檔案帶入Audience Manager。本節內容摘要說明整合程序，並提供DCM資源的連結以協助您開始使用。
seo-description: 設定Google群組，將您的DoubleClick Campaign Manager(DCM)資料檔案帶入Audience Manager。本節內容摘要說明整合程序，並提供DCM資源的連結以協助您開始使用。
seo-title: 將DCM資料檔案匯入Audience Manager
solution: Audience Manager
title: 將DCM資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272 bbcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

設定Google群組，將您的DoubleClick Campaign Manager(DCM)資料檔案帶入Audience Manager。本節內容摘要說明整合程序，並提供DCM資源的連結以協助您開始使用。

## 整合摘要

DCM 是 [!DNL Google] 取代 [!DNL DoubleClick for Advertisers] (DFA) 的替代方案。DCM 的客戶可以在 [!DNL Audience Manager] 中匯入、檢視和處理資料，功用與 DFA 類似。But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. 若要匯入這些檔案，須由客戶自行為之。

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). 此外，您也可以檢閱下列步驟以開始使用。

>[!CAUTION]
>
>DCM資料檔案包含所有廣告商或客戶的資料。If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每日檢查並傳輸資料一次。Data is usually available in [!DNL Audience Manager] after 24-hours.

## 步驟

1. [建立群組](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   群組可控制對您DCM資料的存取。Eventually, you&#39;ll invite and add [!DNL Audience Manager] to this group.

1. [驗證您的Google雲端儲存空間狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)。

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. 您將需要設定儲存貯體，或確定新群組擁有現有資料儲存貯體的存取權。

1. [取得資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)。

   與您的DCM帳戶管理員或平台解決方案顧問合作。他們會提供您的資料檔案URL給您。[!DNL Google] 可能會變更未來版本中儲存貯體和檔案名稱的格式。同樣地，請與您的DCM帳戶管理員合作，確定您使用的格式正確。

1. [設定貯體權限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共用DCM使用者ID會經過加密，以保護隱私權。Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. 這些欄包含每個接收這些檔案之公司專屬的編碼使用者ID。

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. 這表示我們可以放心地與使用者比對和同步化。

   >[!NOTE]
   >[!DNL Audience Manager] 如果您已與其他第三方合作夥伴共用資料，則無法將DCM檔案匯入。

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. 傳送邀請電子郵件至DFA-AAM@adobe.com。請務必包含步驟中的資料檔案URL。我們的內部團隊將會與您合作，在接受邀請後確認存取權。1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. 與內部團隊共用這兩個新資料來源的ID。

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
