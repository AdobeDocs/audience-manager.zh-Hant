---
description: 回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實作
title: 回填特徵實作
uuid: 8b0ef4e6-d16 a-4d1 d-94f1-b84 eepffa9 a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 回填特徵實作 {#backfill-trait-realizations}

回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。

[!UICONTROL Data Explorer Trait Backfill] 是高階功能，借由解鎖其他使用案例來增強Audience Manager體驗。回填需要額外的處理能力，而且所有Audience Manager客戶都能使用遞增成本。如需詳細資訊，請與您的Adobe銷售代表聯絡。

當您從未使用的訊號建立特徵時，可以選擇在特定時段回填特徵實作。[!DNL Audience Manager] 擷取符合新特徵的受眾的歷史資料，並將其儲存在對應的個人檔案上。您可以查看 **[!UICONTROL Backfill Options]**[!UICONTROL Trait Expression]**[「特徵產生器](../../features/traits/about-trait-builder.md)**」中的區段。

>[!NOTE]
>
>您可以回填規則型和已登錄特性的特徵實作。

以下是如何回填特徵實實實作的方法：

1. 前往 [!UICONTROL Audience Data > Signals > Search] amd執行訊號搜尋或使用 [訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md) 識別要用於新特徵的訊號。
1. 根據需要的訊號建立新特徵。
1. 使用 **[!UICONTROL Backfill Options]****[!UICONTROL Trait Expression]** 區段，選擇您要回填特徵實作的時間間隔。預先定義的回填間隔包括1、7、14和30天。您也可以選擇最多30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. (可選)按一 **[!UICONTROL Estimate Realizations]****[!UICONTROL Estimated Trait Realizations]** 下該區段，查看過去天內回填特徵的值 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 值。

   ![估計特徵真實性](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特徵回填和估計不適用於使用下列運算元運算式的特徵：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 建立特徵。

在建立特徵後，您將看到其實施統計資料中包含的回填實作。

## 特徵回填延遲 {#trait-backfilling-latency}

新建立的特徵會在建立後的兩到三小時開始擷取觀眾。不過，由於每天大量執行的資料 [!DNL Audience Manager] 大量執行，回填的人口並不會立即反映在 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] 和圖形中。

Audience [!UICONTROL Trait Graph] Manager會在來自特徵建立的48小時內更新回填人口。

## 特徵回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每個月回填高達50個特徵，並在每個月的天內重設回填計數器。

>[!NOTE]
>
>特徵回填配額不會從前幾個月延續。例如，如果您本月回填30個特徵，則下個月的特徵回填配額會重設為50個，而非70個。

## 對報告的影響 {#reporting-impact}

回填特徵實作會反映在和 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] 度量中，將 [!DNL Audience Manager] 歷史訊號轉變為特徵實作。

但是， [!UICONTROL Trait Graph]在 [!UICONTROL General Reports]特徵 [!UICONTROL Trend Reports] 建立日期之前填入歷史量度時，也會回溯更新。