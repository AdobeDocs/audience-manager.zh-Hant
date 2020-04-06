---
description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實現
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 回填特徵實現 {#backfill-trait-realizations}

回填特徵實現，以擷取歷史受眾，並避免在特徵建立日期之前遺失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一種進階功能，可解除鎖定其他使用案例，以增強Audience Manager體驗。 回填需要額外的處理能力，而且所有Audience Manager客戶都能以遞增成本使用。 如需詳細資訊，請連絡您的Adobe銷售代表。

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

1. 建立特徵。

一旦您完成特徵的建立，您就會看到其回填的實現包含在實現統計資料中。

請觀看以下影片，以取得如何回填特徵的影片逐步說明。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特徵回填延遲 {#trait-backfilling-latency}

新建立的特徵在建立後2到3小時開始擷取觀眾。 但是，由於每日執行的資 [!DNL Audience Manager] 料量龐大，回填的人口不會立即反映在和 [!UICONTROL Unique Trait Realizations] 圖 [!UICONTROL Total Trait Population] 表中。

Audience Manager會在特徵建 [!UICONTROL Trait Graph] 立後48小時內，以回填的人口更新。

## 特徵回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每月回填最多50個特徵，而回填計數器會在每月的1天重設。

>[!NOTE]
>
>特徵回填配額不會延續前幾個月。 例如，如果您在本月回填30個特徵，下個月的特徵回填配額會重設為50，而非70。

## 對報告的影響 {#reporting-impact}

回填的特徵實現會反映在和 [!UICONTROL Unique Trait Realizations] 量度中 [!UICONTROL Total Trait Population] ，因為歷史 [!DNL Audience Manager] 訊號會變成特徵實現。

不過，在特 [!UICONTROL Trait Graph]徵建 [!UICONTROL General Reports]立日 [!UICONTROL Trend Reports] 期之前，歷史量度會回填，不會追溯更新、和。