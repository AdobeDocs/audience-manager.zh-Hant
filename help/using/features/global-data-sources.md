---
description: 使用全域資料來源匯入裝置廣告ID。
seo-description: 使用全域資料來源匯入裝置廣告ID。
seo-title: 全域資料來源
solution: Audience Manager
title: 全域資料來源
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# 全域資料來源 {#global-data-sources}

## 概述

所有Audience Manager客戶都可存取全域資料來源，並包含裝置製造商產生的裝置廣告ID，例如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]裝置製造商。 這些 ID 由製造商提供，用於廣告目的。Audience Manager客戶可以使用全域資料來源來同步裝置ID，並匯入或匯出這些對應的資料。

下表說明Audience Manager支援的全域資料來源。

| 資料來源ID | 說明 |
|---|---|
| 二零九一四年 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** ID代表執行作業系統 [!DNL Android] 的裝置。 |
| 二零九一五年 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** ID代表執行作業系統 [!DNL iOS] 的裝置。 |
| 郵編：121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** ID代表串 [!DNL Roku] 流裝置。 |
| 郵編：389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** ID代表執行作業系統 [!DNL Windows 10] 的裝置。 |
| 郵編：963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** ID代表智 [!DNL Samsung] 慧型電視。 |
| 郵編488258 | **[!DNL Amazon Fire TV Advertising IDs]** 代表執行中的裝置  [!DNL Amazon Fire OS] |

## 從全域資料來源匯入資料

您可以透過[即時資料傳輸](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批次資料傳輸](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)，從全域資料來源匯入裝置ID。

>[!IMPORTANT]
>
>使用全域裝置ID傳送資料至Audience Manager時，請務必針對相關裝置ID使用對應的資料來源。 範例：若要匯入[!DNL Apple IDFA]的資料，請使用資料來源ID 20915。

## 限制

在執行[!DNL iOS]和[!DNL Android]作業系統的裝置上，只有原生應用程式可擷取並使用裝置廣告ID([!UICONTROL DAID]s)。 在行動瀏覽器中執行的網頁應用程式無法存取裝置廣告ID。

## 全域裝置ID驗證

Audience Manager會根據客戶的格式來驗證客戶匯入的裝置廣告ID([!UICONTROL DAID])，以確保符合裝置製造商概述的標準格式。 如需裝置廣告ID與全域資料來源的詳細對應，以及每個ID的適當格式，請參閱Audience Manager](../reference/ids-in-aam.md)中的[ID索引。 請務必根據裝置類型，以正確的格式匯入裝置ID。 Audience Manager會拒絕不符合正確格式的裝置ID，並傳回錯誤訊息，指出ID遭拒。

* 批次資料傳輸的錯誤訊息概述如下：[入職狀態報告詞語與定義](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 以下列出即時資料傳輸的錯誤訊息：[DCS錯誤代碼、消息和示例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 裝置ID到期政策

Audience Manager會在閒置120天後自動放棄裝置廣告ID，類似於[AAM UUID](../faq/faq-privacy.md)。

## 請求新的全域資料來源

若要要求將新的全球資料來源新增至Audience Manager，請聯絡Adobe諮詢或Adobe客戶服務並提供所需資料來源的詳細資訊：

* 所請求平台的名稱（例如[!UICONTROL Apple IDFA]）;
* 管理平台的公司／組織名稱（例如[!UICONTROL Apple Inc.]）;
* 裝置廣告ID名稱空間技術規格的連結（例如[AdSupport Documentation](https://developer.apple.com/documentation/adsupport)）。