---
description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實現
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 回填特徵實現 {#backfill-trait-realizations}

回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。

[!UICONTROL Data Explorer Trait Backfill] 是一種進階功能，可解除鎖定其他使用案例，以增強Audience Manager體驗。 回填需要額外的處理能力，而且所有Audience manager客戶都能以遞增成本使用。 如需詳細資訊，請連絡您的Adobe銷售代表。

當您從未使用的訊號建立特徵時，可以選擇回填特定時段的特徵實現。 [!DNL Audience Manager] 擷取符合新特徵的觀眾的歷史資料，並將其儲存在對應的描述檔中。 您可在「特徵產 **[!UICONTROL Backfill Options]** 生器」 [!UICONTROL Trait Expression] 的區段中 **[看到](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以回填規則型和已登入特徵的特徵實現。

以下是如何回填特徵實現：

1. 前往 [!UICONTROL Audience Data > Signals > Search] amd執行「訊號搜尋」，或使用「訊號儀表板 [](../../features/data-explorer/data-explorer-signals-dashboard.md) 」來識別要用於新特徵的信號。
1. 根據所需訊號建立新特徵。
1. 使用區 **[!UICONTROL Backfill Options]** 段中 **[!UICONTROL Trait Expression]** 的選取您要回填特徵實現的時間間隔。 預先定義的回填間隔包括1、7、14和30天。 您也可以選擇最多30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （可選）按一 **[!UICONTROL Estimate Realizations]** 下區段 **[!UICONTROL Estimated Trait Realizations]** 中的，以查看最近7 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] 天回填特徵的估計值和值。

   ![估計特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特徵回填和估計不適用於使用下列運算子的運算式：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Create the trait.

一旦您完成特徵的建立，您就會看到其回填的實現包含在實現統計資料中。

請觀看以下影片，以取得如何回填特徵的影片逐步說明。

>[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=chi_hant)

## 特徵回填延遲 {#trait-backfilling-latency}

新建立的特徵在建立後2到3小時開始擷取觀眾。 However, due to the large volume of data that  performs on a daily basis, the backfilled population is not immediately reflected in the  and  graphs.[!DNL Audience Manager][!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]

Audience manager會在特徵建 [!UICONTROL Trait Graph] 立後48小時內，以回填的人口更新。

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] allows you to backfill up to 50 traits per month, with the backfill counter being reset on the 1 day of each month.

>[!NOTE]
>
>Trait backfilling quota does not carry over from previous months. E.g., if you backfill 30 traits this month, the trait backfill quota for the next month is reset to 50, not 70.

## 對報告的影響 {#reporting-impact}

Backfilled trait realizations are reflected in the  and  metrics, as  turns historical signals into trait realizations.[!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population][!DNL Audience Manager]

不過，在特 [!UICONTROL Trait Graph]徵建 [!UICONTROL General Reports]立日 [!UICONTROL Trend Reports] 期之前回填歷史量度時，不會追溯更新、和。