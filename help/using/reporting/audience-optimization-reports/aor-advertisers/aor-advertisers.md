---
description: 廣告商Audience Optimization可協助您針對付費媒體促銷活動中的Audience Manager區段，找出潛在的績效機會。 這些報告將記錄層級的促銷活動績效資料與Audience Manager區段量度結合，以提供以區段為中心的最佳化及有效的管道組合。
seo-description: 廣告商Audience Optimization可協助您針對付費媒體促銷活動中的Audience Manager區段，找出潛在的績效機會。 這些報告將記錄層級的促銷活動績效資料與Audience Manager區段量度結合，以提供以區段為中心的最佳化及有效的管道組合。
seo-title: 廣告商適用的 Audience Optimization
solution: Audience Manager
title: 廣告商適用的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: 受眾最佳化報表
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] 廣告商適用{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 廣告商可協助您針對付費媒體行銷活動中的Audience Manager區段，找出潛在的績效機會。這些報告將記錄層級促銷活動績效資料與Audience Manager[!UICONTROL segment]量度結合，以提供以區段為中心的最佳化及有效的管道組合。

## 資料擷取方法{#data-ingestion-methods}

您可以透過下列任一方法，將資料傳送至[!DNL Audience Manager]以用於這些報表。 有時客戶會透過這兩種方法傳送資料。 這有助於確保您的報表包含有關訪客的最完整和準確資訊。 若要使用[!UICONTROL Audience Optimization]報表，您的事件呼叫必須包含[中繼資料檔案的概述和對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)檔案中所列參數的&#x200B;*all*。 您可以透過下列方法傳送資料。

* 像素呼叫：若要將必要的中繼資料參數傳遞至[!DNL Audience Manager]，請參閱透過像素呼叫擷取促銷活動點按資料](../../../integration/media-data-integration/click-data-pixels.md)及[透過像素呼叫擷取促銷活動曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)。[

* 資料檔案：如果您想使用這些報告來分析來自未與[!DNL Audience Manager]整合的源的您自己的資料或資料，則需要為該資料建立和上傳資料和元資料檔案。 如需詳細資訊，請參閱[Audience Optimization報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[Audience Optimization報表的資料和中繼資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可檢視的報表類型取決於您指派給的[!UICONTROL RBAC]群組。 如需詳細資訊，請參閱[管理](../../../features/administration/administration-overview.md)和[建立群組](../../../features/administration/administration-overview.md#create-group) 。

[!UICONTROL RBAC] 群組必須設定一些資料來源，才能檢視 [!UICONTROL Audience Optimization] 報表。您的[!DNL Audience Manager]顧問會為您設定這些[!UICONTROL data sources]。 每個[!UICONTROL RBAC]使用者群組中[!UICONTROL data sources]越多，群組成員將能存取的資料就越多。 您的顧問至少會設定以下其中一個[!UICONTROL data sources]:

* 廣告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

屬於多個[!UICONTROL RBAC]使用者群組的使用者可在每個群組的檢視之間切換。 顯示的資料將更新為與所選群組相關。 如果您的公司未使用[!UICONTROL RBAC]，則所有使用者都擁有管理員權限和所有[!UICONTROL data sources]（轉換群組）的存取權。

## 轉換群組{#conversion-groups}

在[!UICONTROL Audience Optimization]報表中，**[!UICONTROL Conversion Groups]**&#x200B;是包含至少一個轉換特徵的[!UICONTROL data sources]同義詞。 [!UICONTROL Data sources] 其中不包含至少一個轉換特徵的區段不會出現在報 [!UICONTROL Audience Optimization] 表中。您可以在[報告的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)報表中檢視轉換群組的轉換特徵。
