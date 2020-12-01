---
description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實現
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# 回填特徵實現 {#backfill-trait-realizations}

回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一種進階功能，可解除鎖定其他使用案例，以增強Audience Manager體驗。回填需要額外的處理能力，而且所有Audience Manager客戶都能以遞增成本使用。 如需詳細資訊，請連絡您的Adobe銷售代表。

當您從未使用的訊號建立特徵時，可以選擇回填特定時段的特徵實現。 [!DNL Audience Manager] 擷取符合新特徵的觀眾的歷史資料，並將其儲存在對應的描述檔中。您可在&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**&#x200B;的[!UICONTROL Trait Expression]區段中看到&#x200B;**[!UICONTROL Backfill Options]**。

>[!NOTE]
>
>您可以回填規則型和已登入特徵的特徵實現。

以下是如何回填特徵實現：

1. 前往[!UICONTROL Audience Data > Signals > Search]並執行「訊號搜尋」，或使用[Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md)來識別要用於新特徵的訊號。
1. 根據所需訊號建立新特徵。
1. 使用&#x200B;**[!UICONTROL Trait Expression]**&#x200B;區段中的&#x200B;**[!UICONTROL Backfill Options]**&#x200B;來選取您要回填特徵實現的時間間隔。 預先定義的回填間隔包括1、7、14和30天。 您也可以選擇最多30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （可選）按一下&#x200B;**[!UICONTROL Estimated Trait Realizations]**&#x200B;區段中的&#x200B;**[!UICONTROL Estimate Realizations]**，查看過去7天內回填特徵的預估[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]值。

   ![估計特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特徵回填和估計不適用於使用下列運算子的運算式：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 建立特徵。

一旦您完成特徵的建立，您就會看到其回填的實現包含在實現統計資料中。

請觀看以下影片，以取得如何回填特徵的影片逐步說明。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特徵回填延遲{#trait-backfilling-latency}

新建立的特徵在建立後2到3小時開始擷取觀眾。 但是，由於[!DNL Audience Manager]每天執行的資料量很大，所以回填的人口不會立即反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]圖中。

Audience Manager會在特徵建立後48小時內，以回填的人數更新[!UICONTROL Trait Graph]。

## 特徵回填限制{#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每月回填最多50個特徵，而回填計數器會在每月的1天重設。

>[!NOTE]
>
>特徵回填配額不會延續前幾個月。 例如，如果您在本月回填30個特徵，下個月的特徵回填配額會重設為50，而非70。

## 對報告的影響{#reporting-impact}

回填的特徵實現會反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]量度中，因為[!DNL Audience Manager]會將歷史訊號轉換為特徵實現。

不過，在特徵建立日期之前回填歷史量度時，不會追溯更新[!UICONTROL Trait Graph]、[!UICONTROL General Reports]和[!UICONTROL Trend Reports]。