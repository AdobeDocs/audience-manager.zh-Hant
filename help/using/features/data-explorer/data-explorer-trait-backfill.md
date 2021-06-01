---
description: 回填特徵實現項目，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實現項目，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實現
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# 回填特徵實現 {#backfill-trait-realizations}

回填特徵實現項目，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是進階功能，可借由解鎖其他使用案例來增強Audience Manager體驗。回填需要額外的處理能力，並且以遞增成本提供給所有Audience Manager客戶。 如需詳細資訊，請連絡您的Adobe銷售代表。

當您從未使用的訊號建立特徵時，可以選擇在特定時段內回填特徵實現。 [!DNL Audience Manager] 擷取符合新特徵資格的受眾的歷史資料，並將其儲存在對應的設定檔中。您可以在&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**&#x200B;的[!UICONTROL Trait Expression]區段中看到&#x200B;**[!UICONTROL Backfill Options]**。

>[!NOTE]
>
>您可以回填規則型和已上線特徵的特徵實現。

以下是如何回填特徵實現：

1. 前往[!UICONTROL Audience Data > Signals > Search]並執行「訊號搜尋」，或使用[訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md)來識別要用於新特徵的訊號。
1. 根據所需訊號建立新特徵。
1. 使用&#x200B;**[!UICONTROL Trait Expression]**&#x200B;區段中的&#x200B;**[!UICONTROL Backfill Options]**&#x200B;來選取您要回填特徵實現的時間間隔。 預先定義的回填間隔包括1、7、14和30天。 您也可以選擇最多30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （選用）按一下&#x200B;**[!UICONTROL Estimated Trait Realizations]**&#x200B;區段中的&#x200B;**[!UICONTROL Estimate Realizations]**，查看過去7天內回填特徵的預估[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]值。

   ![預估 — 特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特徵回填和估計無法供具有下列運算子之運算式的特徵使用：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 建立特徵。

建立完特徵後，您會看到其回填的實現包含在實現統計資料中。

請觀看以下影片，以了解如何回填特徵的影片逐步說明。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特徵回填延遲{#trait-backfilling-latency}

新建立的特徵會在建立後兩到三小時開始擷取對象。 但是，由於[!DNL Audience Manager]每天執行的資料量很大，所以回填的母體不會立即反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]圖表中。

Audience Manager會在特徵建立後48小時內，以回填的母體更新[!UICONTROL Trait Graph]。

## 特徵回填限制{#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每月回填最多50個特徵，並在每月的1天重設回填計數器。

>[!NOTE]
>
>特徵回填配額不會延續前幾個月。 例如，如果您在本月回填30個特徵，則下個月的特徵回填配額會重設為50而非70。

## 對報告的影響{#reporting-impact}

回填的特徵實現會反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]量度中，因為[!DNL Audience Manager]會將歷史訊號轉換為特徵實現。

不過，系統不會以在特徵建立日期之前回填的歷史量度，來回溯更新[!UICONTROL Trait Graph]、[!UICONTROL General Reports]和[!UICONTROL Trend Reports]。
