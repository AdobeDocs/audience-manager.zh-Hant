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
source-wordcount: '448'
ht-degree: 6%

---

# 全域資料來源 {#global-data-sources}

## 概述

所有Audience Manager客戶都可存取全域資料來源，並包含裝置製造商產生的裝置廣告ID，例如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]裝置製造商。 這些 ID 由製造商提供，用於廣告目的。Audience Manager客戶可使用全域資料來源來同步裝置ID，並匯入或匯出這些對應所中斷的資料。

下表說明了Audience Manager支援的全域資料來源。

| 資料來源ID | 說明 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - ID **[!DNL GAID]** 代表執行作業系統的 [!DNL Android] 裝置。 |
| 20915 | **[!DNL Apple ID For Advertising]** - ID **[!DNL IDFA]** 代表執行作業系統的 [!DNL iOS] 裝置。 |
| 121963 | **[!DNL Roku ID for Advertising]** - ID **[!DNL RIDA]** 代表串 [!DNL Roku] 流裝置。 |
| 389146 | **[!DNL Microsoft Advertising ID]** - ID **[!DNL MAID]** 代表執行作業系統的 [!DNL Windows 10] 裝置。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** ID代表 [!DNL Samsung] 智慧型電視。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** 代表裝置執行中  [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]**  — 表 **[!DNL LGUDID]** 示運行作業系統 [!DNL LG webOS] 的設備。 |
| 1171489 | **[!DNL Vizio ID for Advertising]**  — 代 **[!DNL IFA]** 表運行Vizio智慧電視作業系統的設備。 |

## 從全域資料來源匯入資料

您可以透過[即時資料傳輸](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批次資料傳輸](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)，從全域資料來源匯入裝置ID。

>[!IMPORTANT]
>
>使用全域裝置ID傳送資料至Audience Manager時，請務必為相關裝置ID使用對應的資料來源。 範例：若要匯入[!DNL Apple IDFA]的資料，請使用資料來源ID 20915。

## 限制

在運行[!DNL iOS]和[!DNL Android]作業系統的設備上，只有本機應用程式可以檢索和使用設備廣告ID([!UICONTROL DAID]s)。 在行動瀏覽器中執行的網頁應用程式無法存取裝置廣告ID。

## 全域裝置ID驗證

Audience Manager會根據格式，驗證客戶匯入的裝置廣告ID([!UICONTROL DAID])，以確保符合裝置製造商列出的標準格式。 請參閱[Audience Manager中的ID索引](../reference/ids-in-aam.md) ，以取得裝置廣告ID與全域資料來源的詳細對應，以及每個ID的適當格式。 請務必根據裝置類型，以正確格式匯入裝置ID。 Audience Manager拒絕不符合正確格式的裝置ID，並傳回錯誤訊息，指出ID遭拒。

* 批次資料傳輸的錯誤訊息概述如下：[入門狀態報表詞語和定義](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 即時資料傳輸的錯誤訊息概述如下：[DCS錯誤碼、訊息和範例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 設備ID過期策略

Audience Manager在120天未使用後自動捨棄裝置廣告ID，類似於[AAM UUID](../faq/faq-privacy.md)s。

## 請求新的全域資料來源

若要要求將新的全域資料來源新增至Audience Manager，請聯絡Adobe諮詢或Adobe客戶服務，並提供所需資料來源的詳細資訊：

* 請求的平台的名稱（例如[!UICONTROL Apple IDFA]）;
* 管理平台的公司/組織名稱（例如[!UICONTROL Apple Inc.]）;
* 裝置廣告ID命名空間技術規格的連結（例如[AdSupport檔案](https://developer.apple.com/documentation/adsupport)）。
