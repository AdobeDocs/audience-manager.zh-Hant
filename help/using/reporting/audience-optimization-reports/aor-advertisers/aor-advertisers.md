---
description: 「廣告商的受眾最佳化」可協助您在付費媒體宣傳中識別Audience Manager細分的潛在效能機會。 這些報表結合記錄層級的促銷活動績效資料與Audience Manager區段度量，以提供以區段為中心的最佳化以及有效的渠道組合。
seo-description: 「廣告商的受眾最佳化」可協助您在付費媒體宣傳中識別Audience Manager細分的潛在效能機會。 這些報表結合記錄層級的促銷活動績效資料與Audience Manager區段度量，以提供以區段為中心的最佳化以及有效的渠道組合。
seo-title: 廣告商適用的 Audience Optimization
solution: Audience Manager
title: 廣告商適用的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] 針對廣告商{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] for Advertisers可協助您在付費媒體促銷活動中識別Audience Manager區段的潛在效能機會。這些報表結合記錄層級的促銷活動績效資料與Audience Manager [!UICONTROL segment]量度，以通知以區段為中心的最佳化和有效的渠道組合。

## 資料擷取方法{#data-ingestion-methods}

您可以將資料傳送至[!DNL Audience Manager]，以便透過其中一種方法用於這些報表。 有時客戶會透過兩種方式傳送資料。 這有助於確保您的報表包含有關訪客的最完整和準確資訊。 若要使用[!UICONTROL Audience Optimization]報表，您的事件呼叫必須包含[概述與中繼資料檔案對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)檔案中所列參數的&#x200B;*all*。 您可以透過下列方法傳送資料。

* 像素呼叫：若要將必要的中繼資料參數傳遞至[!DNL Audience Manager]，請參閱[透過像素呼叫擷取促銷活動點按資料](../../../integration/media-data-integration/click-data-pixels.md)及[透過像素呼叫擷取促銷活動印象資料](../../../integration/media-data-integration/impression-data-pixels.md)。

* 資料檔案：如果您想使用這些報表來分析未與[!DNL Audience Manager]整合之來源的您自己的資料或資料，則需要建立並上傳該資料的資料和中繼資料檔案。 如需詳細資訊，請參閱[對象最佳化報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)和[對象最佳化報表的資料和中繼資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

您可檢視的報表類型取決於您指派給的[!UICONTROL RBAC]群組。 如需詳細資訊，請參閱[管理](../../../features/administration/administration-overview.md)和[建立群組](../../../features/administration/administration-overview.md#create-group)。

[!UICONTROL RBAC] 群組必須設定一些資料來源，才能檢視 [!UICONTROL Audience Optimization] 報表。您的[!DNL Audience Manager]顧問將為您設定這些[!UICONTROL data sources]。 每個[!UICONTROL RBAC]使用者群組的[!UICONTROL data sources]愈多，這些群組成員可存取的資料愈多。 至少，您的顧問將至少設定以下其中一個[!UICONTROL data sources]:

* 廣告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

屬於多個[!UICONTROL RBAC]使用者群組的使用者可在每個群組的檢視之間切換。 顯示的資料會更新，以符合選取的群組。 如果您的公司未使用[!UICONTROL RBAC]，所有使用者都將擁有管理員權限並可存取所有[!UICONTROL data sources]（轉換群組）。

## 轉換群組{#conversion-groups}

在[!UICONTROL Audience Optimization]報表中，**[!UICONTROL Conversion Groups]**&#x200B;是包含至少一個轉換特徵的[!UICONTROL data sources]同義詞。 [!UICONTROL Data sources] 至少不包含一個轉換特徵的轉換特徵不會出現在報 [!UICONTROL Audience Optimization] 表中。您可以在[報告的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md)報表中檢視轉換群組的轉換特徵。
