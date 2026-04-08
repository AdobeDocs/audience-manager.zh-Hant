---
description: 廣告商適用的Audience Optimization可協助您在付費媒體行銷活動中，識別Audience Manager區段的潛在效用機會。 這些報表結合記錄層級行銷活動績效資料與Audience Manager區段量度，以提供以區段為中心的最佳化和有效的管道組合資訊。
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: 廣告商適用的Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
TQID: https://experienceleague.adobe.com/U9Rg-4rwjGdqYsjGDlctn0PBuxAlDjwIBtorAnGtqHU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 0%

---

# 廣告商的[!UICONTROL Audience Optimization]{#audience-optimization-for-advertisers}

廣告商的[!UICONTROL Audience Optimization]可協助您在付費媒體行銷活動中識別Audience Manager區段的潛在效用機會。 這些報表結合記錄層級行銷活動績效資料與Audience Manager [!UICONTROL segment]量度，以提供以區段為中心的最佳化和有效管道組合資訊。

## 資料擷取方法 {#data-ingestion-methods}

您可以透過下列任一方法將資料傳送至[!DNL Audience Manager]以用於這些報表。 有時候，客戶會透過兩種方法傳送資料。 這可協助確保您的報表包含最全面且準確的訪客相關資訊。 若要使用[!UICONTROL Audience Optimization]報表，您的事件呼叫必須包含&#x200B;*中繼資料檔案概述與對應*&#x200B;檔案中列出的[所有](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)引數。 您可以透過下列方法傳送資料。

* 畫素呼叫：若要將必要的中繼資料引數傳遞至[!DNL Audience Manager]，請參閱[透過畫素呼叫擷取行銷活動的點按資料](../../../integration/media-data-integration/click-data-pixels.md)和[透過畫素呼叫擷取行銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)。

* 資料檔案：如果您想要使用這些報表來分析您自己的資料或來自未與[!DNL Audience Manager]整合之來源的資料，您需要為該資料建立和上傳資料和中繼資料檔案。 如需詳細資訊，請參閱[Audience Optimization報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[Audience Optimization報表的資料和中繼資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以檢視的報告型別取決於指派給您的[!UICONTROL RBAC]群組。 如需詳細資訊，請參閱[管理](../../../features/administration/administration-overview.md)和[建立群組](../../../features/administration/administration-overview.md#create-group)。

[!UICONTROL RBAC]群組必須設定一些資料來源，才能檢視[!UICONTROL Audience Optimization]報告。 您的[!DNL Audience Manager]顧問將為您設定這些[!UICONTROL data sources]。 每個[!UICONTROL data sources]使用者群組中的[!UICONTROL RBAC]越多，這些群組成員有權存取的資料就越多。 您的顧問至少會設定下列[!UICONTROL data sources]中的一個：

* 廣告商[!UICONTROL data source]
* 品牌[!UICONTROL data source]
* 平台[!UICONTROL data source]

屬於多個[!UICONTROL RBAC]使用者群組的使用者可以在每個群組的檢視之間切換。 顯示的資料將會更新，以符合選取的群組。 如果您的公司未使用[!UICONTROL RBAC]，則所有使用者都將擁有管理員許可權，以及所有[!UICONTROL data sources] （轉換群組）的存取權。

## 轉換群組 {#conversion-groups}

在[!UICONTROL Audience Optimization]報表中，**[!UICONTROL Conversion Groups]**&#x200B;與至少包含一個轉換特徵的[!UICONTROL data sources]同義。 不包含至少一個轉換特徵的[!UICONTROL Data sources]不會出現在[!UICONTROL Audience Optimization]報表中。 您可以在[回報的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)報表中檢視轉換群組的轉換特徵。
