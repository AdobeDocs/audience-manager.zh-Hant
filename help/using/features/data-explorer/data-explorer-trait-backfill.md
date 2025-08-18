---
description: 回填特徵實現以擷取歷史對象，並避免在特徵建立日期之前遺失相關資料。
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# 回填特徵實現 {#backfill-trait-realizations}

回填特徵實現以擷取歷史對象，並避免在特徵建立日期之前遺失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill]是進階功能，可藉由解鎖其他使用案例來增強Audience Manager體驗。 回填需要額外的處理能力，而且所有Audience Manager客戶都可以透過累加成本取得回填。 如需詳細資訊，請聯絡您的Adobe銷售代表。

從未使用的訊號建立特徵時，您可以選擇在特定時段內回填特徵實現。 [!DNL Audience Manager]會擷取符合新特徵資格受眾的歷史資料，並將其儲存在對應的設定檔中。 您可以在&#x200B;**[!UICONTROL Backfill Options]**&#x200B;特徵產生器[!UICONTROL Trait Expression]的&#x200B;**[區段中看到](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以回填規則型特徵和已上線特徵的特徵實現。

以下說明如何回填特徵實現：

1. 移至[!UICONTROL Audience Data > Signals > Search]並執行訊號搜尋，或使用[訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md)識別要用於新特徵的訊號。
1. 根據所需的訊號建立新特徵。
1. 使用&#x200B;**[!UICONTROL Backfill Options]**&#x200B;區段中的&#x200B;**[!UICONTROL Trait Expression]**&#x200B;來選取您要回填特徵實現的時間間隔。 預先定義的回填間隔為1、7、14和30天。 您也可以選擇最長30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （選用）按一下「**[!UICONTROL Estimate Realizations]**」區段中的「**[!UICONTROL Estimated Trait Realizations]**」，以檢視過去7天回填特徵的預估[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]值。

   ![預估 — 特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >使用下列運運算元的運算式特徵，無法進行特徵回填和預估：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`
1. 建立特徵。

完成特徵建立後，您會看到其回填的實現專案包含在實現統計資料中。

觀看以下影片，瞭解如何回填特徵的影片逐步解說。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特徵回填延遲 {#trait-backfilling-latency}

新建立的特徵會在建立兩到三個小時後開始擷取對象。 不過，由於[!DNL Audience Manager]每天執行的大量資料，回填的母體不會立即反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]圖表中。

Audience Manager會在特徵建立後48小時內以回填母體更新[!UICONTROL Trait Graph]。

## 特徵回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer]可讓您每月回填最多50個特徵，回填計數器會在每個月的1日重設。

>[!NOTE]
>
>特徵回填配額不會延續到前幾個月。 例如，如果您本月回填30個特徵，下個月的特徵回填配額會重設為50，而不是70。

## 對報表的影響 {#reporting-impact}

回填的特徵實現會反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]量度中，因為[!DNL Audience Manager]會將歷史訊號轉換為特徵實現。

但是，[!UICONTROL Trait Graph]、[!UICONTROL General Reports]和[!UICONTROL Trend Reports]未以回填在特徵建立日期之前的歷史量度進行回溯更新。
