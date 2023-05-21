---
description: 廣告商Audience Optimization可幫助您為付費媒體活動中的Audience Manager段確定潛在的表現機會。 這些報告將日誌級市場活動績效資料與Audience Manager段指標相結合，以支援以段為中心的優化和有效的渠道組合。
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: 廣告商適用的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---

# [!UICONTROL Audience Optimization] 廣告商{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 對於廣告商，您可以幫助您為付費媒體活動中的Audience Manager段確定潛在的表現機會。 這些報告將日誌級市場活動績效資料與Audience Manager [!UICONTROL segment] 以資料段為中心的優化和有效的通道組合。

## 資料接收方法 {#data-ingestion-methods}

您可以將資料發送到 [!DNL Audience Manager] 以便在這些報告中使用。 有時，客戶會通過兩種方法發送資料。 這有助於確保您的報告包含有關訪問者的最全面和準確的資訊。 使用 [!UICONTROL Audience Optimization] 報告，您的事件呼叫必須包括 *全部* 列出的參數 [元資料檔案的概述和映射](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 文檔。 您可以通過下面列出的以下方法發送資料。

* 像素調用：將所需的元資料參數傳遞給 [!DNL Audience Manager] 見 [通過像素呼叫捕獲市場活動按一下資料](../../../integration/media-data-integration/click-data-pixels.md) 和 [通過像素呼叫捕獲市場活動印象資料](../../../integration/media-data-integration/impression-data-pixels.md)。

* 資料檔案：如果要使用這些報告來分析未與整合的源中的資料 [!DNL Audience Manager]，您需要為該資料建立和上載資料和元資料檔案。 有關詳細資訊，請參見 [用於Audience Optimization報告的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 和 [用於Audience Optimization報告的資料和元資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)。

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以查看的報告類型取決於 [!UICONTROL RBAC] 組。 請參閱 [管理](../../../features/administration/administration-overview.md) 和 [建立組](../../../features/administration/administration-overview.md#create-group) 的子菜單。

[!UICONTROL RBAC] 組必須設定一些資料源才能查看 [!UICONTROL Audience Optimization] 報告。 您 [!DNL Audience Manager] 顧問將設定 [!UICONTROL data sources] 為你。 越多 [!UICONTROL data sources] 每 [!UICONTROL RBAC] 用戶組，這些組成員將有權訪問的資料越多。 至少，您的顧問將至少設定其中一個 [!UICONTROL data sources]:

* 廣告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

屬於多個用戶的用戶 [!UICONTROL RBAC] 用戶組可以在每個組的視圖之間切換。 顯示的資料將更新以與所選組相關。 如果你的公司不使用 [!UICONTROL RBAC]，所有用戶都具有管理員權限和對所有 [!UICONTROL data sources] （轉換組）。

## 轉換組 {#conversion-groups}

在 [!UICONTROL Audience Optimization] 報告， **[!UICONTROL Conversion Groups]** 是同義詞 [!UICONTROL data sources] 至少包含一個轉化特性。 [!UICONTROL Data sources] 至少不包含一個轉換特性的 [!UICONTROL Audience Optimization] 報告。 您可以在 [報告的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 報告。
