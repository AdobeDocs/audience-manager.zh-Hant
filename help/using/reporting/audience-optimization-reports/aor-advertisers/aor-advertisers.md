---
description: Advertisers Optimize for Advertisers可幫助您識別付費媒體促銷活動中Audience Manager區段的潛在效能機會。這些報表將記錄層級促銷活動績效資料與Audience Manager區段量度結合，以通知區段導向最佳化以及有效的頻道混音。
seo-description: Advertisers Optimize for Advertisers可幫助您識別付費媒體促銷活動中Audience Manager區段的潛在效能機會。這些報表將記錄層級促銷活動績效資料與Audience Manager區段量度結合，以通知區段導向最佳化以及有效的頻道混音。
seo-title: 廣告商的受眾最佳化
solution: Audience Manager
title: 廣告商的受眾最佳化
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Advertisers Optimize for Advertisers可幫助您識別付費媒體促銷活動中Audience Manager區段的潛在效能機會。這些報表將記錄層級促銷活動績效資料與Audience Manager區段量度結合，以通知區段導向最佳化以及有效的頻道混音。

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. 有時候，客戶會依兩種方法傳送資料。這有助於確保您的報表包含有關訪客的最完整且準確的資訊。To use the [!UICONTROL Audience Optimization] reports, your event calls must include *all* of the parameters listed in the [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentation. 您可以透過下列方式傳送資料。

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Role-Based Access Controls (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you're assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] 群組必須設定一些資料來源，才能檢視 [!UICONTROL Audience Optimization] 報表。Your [!DNL Audience Manager] consultant will set up these data sources for you. [!UICONTROL RBAC] 每個使用者群組中的資料來源越多，這些群組成員可以存取的資料越多。至少您的顧問至少會設定其中一個資料來源：

* 廣告商資料來源
* 品牌資料來源
* 平台資料來源

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group's view. 顯示的資料將會更新，以尊重所選群組。If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#conversion-groups}

[!UICONTROL Audience Optimization] 在報表中， **[!UICONTROL Conversion Groups]** 是包含至少一個轉換特徵的資料來源同義詞。Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. You can view the conversion traits for conversion groups in the [Reported Conversion Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) report.
