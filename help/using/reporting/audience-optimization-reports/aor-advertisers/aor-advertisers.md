---
description: 「廣告商的受眾最佳化」可協助您在付費媒體宣傳中識別Audience manager細分的潛在效能機會。 這些報表結合記錄層級的促銷活動績效資料與Audience manager區段度量，以提供以區段為中心的最佳化以及有效的渠道組合。
seo-description: 「廣告商的受眾最佳化」可協助您在付費媒體宣傳中識別Audience manager細分的潛在效能機會。 這些報表結合記錄層級的促銷活動績效資料與Audience manager區段度量，以提供以區段為中心的最佳化以及有效的渠道組合。
seo-title: 廣告商的受眾最佳化
solution: Audience Manager
title: 廣告商的受眾最佳化
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

「廣告商的受眾最佳化」可協助您在付費媒體宣傳中識別Audience manager細分的潛在效能機會。 這些報表結合記錄層級的促銷活動績效資料與Audience manager區段度量，以提供以區段為中心的最佳化以及有效的渠道組合。

## 資料擷取方法 {#data-ingestion-methods}

您可以透過下列任 [!DNL Audience Manager] 一方法，將資料傳送至這些報表。 有時客戶會透過兩種方式傳送資料。 這有助於確保您的報表包含有關訪客的最完整和準確資訊。 若要使用 [!UICONTROL Audience Optimization] 報表，您的事件呼叫必須包含 ** 「概述」和「中繼資料檔案 [的對應」檔案中所列的所有參數](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 。 您可以透過下列方法傳送資料。

* 像素呼叫：若要傳遞必要的中繼資料參數，以 [!DNL Audience Manager] 查看透過像 [素呼叫擷取促銷活動點按資料](../../../integration/media-data-integration/click-data-pixels.md) , [以及透過像素呼叫擷取促銷活動印象資料](../../../integration/media-data-integration/impression-data-pixels.md)。

* 資料檔案：如果您想使用這些報表來分析來自未整合之來源的資料或資料 [!DNL Audience Manager]，則需要建立並上傳該資料的資料和中繼資料檔案。 如需詳細資訊，請參 [閱「對象最佳化報表的資料檔案」](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) ，以 [及「對象最佳化報表的資料和中繼資料檔案」](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## 基於角色的訪問控制(RBAC) {#rbac}

您可檢視的報表類型取決於 [!UICONTROL RBAC] 您指派給的群組。 如需詳 [細資訊](../../../features/administration/administration-overview.md) ，請 [參閱管理和建立群組](../../../features/administration/administration-overview.md#create-group) 。

[!UICONTROL RBAC] 群組必須設定一些資料來源，才能檢視報 [!UICONTROL Audience Optimization] 表。 您的 [!DNL Audience Manager] 顧問將為您設定這些資料來源。 每個使用者群組中的資 [!UICONTROL RBAC] 料來源愈多，這些群組成員可存取的資料就愈多。 至少，您的顧問將至少設定下列其中一個資料來源：

* 廣告商資料來源
* 品牌資料來源
* 平台資料來源

屬於多個使用者群組的 [!UICONTROL RBAC] 使用者可在每個群組的檢視之間切換。 顯示的資料會更新，以符合選取的群組。 如果您的公司未使用， [!UICONTROL RBAC]所有使用者都將擁有管理員權限並存取所有資料來源（轉換群組）。

## 轉換群組 {#conversion-groups}

在報表 [!UICONTROL Audience Optimization] 中， **[!UICONTROL Conversion Groups]** 與包含至少一個轉換特徵的資料來源同義。 至少不含一個轉換特徵的資料來源不會顯示在報表中 [!UICONTROL Audience Optimization] 。 您可以在「報告的轉換特徵」報表中檢視轉換群 [組的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 。
