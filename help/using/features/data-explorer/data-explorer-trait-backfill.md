---
description: 回填特性實現，以捕獲歷史受眾並避免在特性建立日期之前丟失相關資料。
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: 回填特徵實現
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---

# 回填特徵實現 {#backfill-trait-realizations}

回填特性實現，以捕獲歷史受眾並避免在特性建立日期之前丟失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一種高級功能，通過釋放其他使用案例來增強Audience Manager體驗。 回填需要額外的處理能力，並且以遞增的成本提供給所有Audience Manager客戶。 請聯繫您的Adobe銷售代表，瞭解更多詳細資訊。

當您從未使用的信號中建立特徵時，您可以選擇在特定時間段內回填特徵實現。 [!DNL Audience Manager] 捕獲符合新特性的受眾的歷史資料並將其儲存在相應的檔案中。 您可以看到 **[!UICONTROL Backfill Options]** 的 [!UICONTROL Trait Expression] 的下界 **[特性生成器](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以為基於規則和已連接的特徵重新填充特徵實現。

下面是如何回填特性實現：

1. 轉到 [!UICONTROL Audience Data > Signals > Search] amd運行信號搜索或使用 [信號儀表板](../../features/data-explorer/data-explorer-signals-dashboard.md) 識別新特性中要使用的信號。
1. 根據所需信號建立新特性。
1. 使用 **[!UICONTROL Backfill Options]** 的 **[!UICONTROL Trait Expression]** 框中選擇要回填特性實現的時間間隔。 預定義的回填間隔包括1、7、14和30天。 您也可以選擇最多30天的自定義日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （可選）按一下 **[!UICONTROL Estimate Realizations]** 的 **[!UICONTROL Estimated Trait Realizations]** 部分以查看 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 過去7天內回填特徵的值。

   ![估計特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特徵回填和估計不適用於使用以下運算子的表達式的特徵：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 創造特質。

一旦你完成了特徵的建立，你將看到其回填的實現包含在實現統計資訊中。

請看下面的視頻，看如何回填特徵的視頻。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特性回填延遲 {#trait-backfilling-latency}

新創造的特質開始在2到3小時後吸引觀眾。 但是，由於資料量大， [!DNL Audience Manager] 每天執行，填補的人口不會立即反映在 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 圖形。

Audience Manager更新 [!UICONTROL Trait Graph] 在特徵創造後48小時內就有回填人。

## 特徵回填極限 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允許您每月回填最多50個traits，每月1天重置回填計數器。

>[!NOTE]
>
>特性回填配額不會從前幾個月結轉。 例如，如果你在本月回填30個特徵，下個月的特徵回填配額將重置為50而不是70。

## 對報告的影響 {#reporting-impact}

回填特性實現反映在 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 度量，如 [!DNL Audience Manager] 將歷史信號轉化為特質實現。

然而， [!UICONTROL Trait Graph]。 [!UICONTROL General Reports], [!UICONTROL Trend Reports] 在特徵建立日期之前，不會用回溯填寫的歷史度量追溯更新。
