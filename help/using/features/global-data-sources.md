---
description: 使用全局資料源導入設備廣告ID。
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

全球資料源可由所有Audience Manager客戶訪問，並包含由設備製造商(如 [!DNL Apple]。 [!DNL Samsung]。 [!DNL Microsoft]。 [!DNL Roku], [!DNL Android] 設備製造商。 這些 ID 由製造商提供，用於廣告目的。Audience Manager客戶可以使用全局資料源來同步設備ID並導入或導出與這些映射鎖定的資料。

下表介紹了Audience Manager支援的全局資料源。

| 資料源ID | 說明 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID表示運行 [!DNL Android] 作業系統。 |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID表示運行 [!DNL iOS] 作業系統。 |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID表示 [!DNL Roku] 流式傳輸設備。 |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID表示運行 [!DNL Windows 10] 作業系統。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID表示 [!DNL Samsung] 智慧電視。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** 代表運行的設備 [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** 表示運行的設備 [!DNL LG webOS] 作業系統。 |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** 代表運行Vizio智慧電視作業系統的設備。 |

## 從全局資料源導入資料

您可以通過全局資料源導入設備ID [即時資料傳輸](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) 和 [批資料傳輸](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)。

>[!IMPORTANT]
>
>使用全局設備ID向Audience Manager發送資料時，請確保使用相關設備ID的相應資料源。 示例：要導入資料 [!DNL Apple IDFA]，使用資料源ID 20915。

## 限制

在運行的設備上 [!DNL iOS] 和 [!DNL Android] 作業系統，只有本機應用程式才能檢索和使用設備廣告ID([!UICONTROL DAID]s)。 在移動瀏覽器中運行的Web應用程式無權訪問廣告ID的設備。

## 全局設備ID驗證

Audience Manager驗證設備通告ID([!UICONTROL DAID])，以確保其與設備製造商概述的標準格式相匹配。 請參閱 [Audience Manager中ID的索引](../reference/ids-in-aam.md) 用於將設備通告ID到全局資料源的詳細映射以及每個ID的正確格式。 確保根據設備類型以正確的格式導入設備ID。 Audience Manager拒絕不符合正確格式的設備ID，並返回一條錯誤消息以指示ID被拒絕。

* 此處概述了批資料傳輸的錯誤消息傳遞： [入門狀態報表術語和定義](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 此處概述了即時資料傳輸的錯誤消息傳遞： [DCS錯誤代碼、消息和示例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 設備ID過期策略

Audience Manager在120天不活動後自動丟棄通告ID的設備，類似於 [UUIDAAM](../faq/faq-privacy.md)s

## 請求新的全局資料源

要請求將新的全局資料源添加到Audience Manager中，請與Adobe咨詢或Adobe客戶服務部門聯繫，並提供有關所需資料源的詳細資訊：

* 請求的平台的名稱(例如， [!UICONTROL Apple IDFA]);
* 管理平台的公司/組織的名稱(如 [!UICONTROL Apple Inc.]);
* 指向設備通告ID命名空間的技術規範的連結(例如， [AdSupport文檔](https://developer.apple.com/documentation/adsupport))。
