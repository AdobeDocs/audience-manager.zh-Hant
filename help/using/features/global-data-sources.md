---
description: 使用全域資料來源匯入裝置廣告ID。
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: 全域資料來源
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# 全域資料來源 {#global-data-sources}

## 概述

所有Audience Manager客戶皆可存取全域資料來源，並包含裝置製造商產生的裝置廣告ID，例如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]裝置製造商。 這些 ID 由製造商提供，用於廣告目的。Audience Manager客戶可使用全域資料來源來同步裝置ID，並匯入或匯出這些對應所中斷的資料。

下表說明Audience Manager支援的全域資料來源。

| 資料Source ID | 說明 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]**&#x200B;識別碼代表執行[!DNL Android]作業系統的裝置。 |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]**&#x200B;識別碼代表執行[!DNL iOS]作業系統的裝置。 |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]**&#x200B;個ID代表[!DNL Roku]個串流裝置。 |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]**&#x200B;識別碼代表執行[!DNL Windows 10]作業系統的裝置。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID代表[!DNL Samsung]部智慧型電視。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]**&#x200B;代表執行[!DNL Amazon Fire OS]的裝置 |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]**&#x200B;代表執行[!DNL LG webOS]作業系統的裝置。 |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]**&#x200B;代表執行Vizio智慧型電視作業系統的裝置。 |

## 從全域資料來源匯入資料

您可以透過[即時資料傳輸](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批次資料傳輸](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)，從全域資料來源匯入裝置識別碼。

>[!IMPORTANT]
>
>使用全域裝置ID將資料傳送至Audience Manager時，請務必針對有問題的裝置ID使用對應的資料來源。 範例：若要為[!DNL Apple IDFA]匯入資料，請使用資料來源識別碼20915。

## 限制

在執行[!DNL iOS]和[!DNL Android]作業系統的裝置上，只有原生應用程式才能擷取和使用裝置廣告ID ([!UICONTROL DAID])。 在行動瀏覽器中執行的網頁應用程式無法存取裝置廣告ID。

## 全域裝置ID驗證

Audience Manager會根據格式，驗證客戶匯入的裝置廣告ID ([!UICONTROL DAID])，確保符合裝置製造商列出的標準格式。 請參閱[Audience Manager內的ID索引](../reference/ids-in-aam.md)，以取得裝置廣告ID與全域資料來源的詳細對應，以及每個ID的適當格式。 請務必根據裝置型別，以正確的格式匯入裝置ID。 Audience Manager會拒絕不符合適當格式的裝置ID，並傳回錯誤訊息以指出該ID遭到拒絕。

* 批次資料傳輸的錯誤訊息概述如下： [上線狀態報告條款與定義](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 即時資料傳輸的錯誤訊息概述如下： [DCS錯誤碼、訊息和範例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 裝置ID過期原則

Audience Manager會在閒置120天後自動捨棄裝置廣告ID，類似於[AAM UUID](../faq/faq-privacy.md)。

## 請求新的全域資料來源

若要請求將新的全域資料來源新增至Audience Manager，請聯絡Adobe Consulting或Adobe客戶服務，並提供必要資料來源的詳細資訊：

* 要求的平台名稱（例如，[!UICONTROL Apple IDFA]）；
* 管理平台的公司/組織的名稱（例如，[!UICONTROL Apple Inc.]）；
* 裝置廣告ID名稱空間技術規格的連結（例如，[AdSupport檔案](https://developer.apple.com/documentation/adsupport)）。
