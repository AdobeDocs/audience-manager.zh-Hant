---
description: 回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。
seo-description: 回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。
seo-title: 回填特徵實作
title: 回填特徵實作
uuid: 8b0ef4e6-d16 a-4d1 d-94f1-b84 eepffa9 a5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

回填特徵實作以擷取歷史觀眾，並避免在特徵建立日期之前遺失相關資料。

[!UICONTROL Data Explorer Trait Backfill] 是高階功能，借由解鎖其他使用案例來增強Audience Manager體驗。回填需要額外的處理能力，而且所有Audience Manager客戶都能使用遞增成本。如需詳細資訊，請與您的Adobe銷售代表聯絡。

當您從未使用的訊號建立特徵時，可以選擇在特定時段回填特徵實作。[!DNL Audience Manager] 擷取符合新特徵的受眾的歷史資料，並將其儲存在對應的個人檔案上。You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>您可以回填規則型和已登錄特性的特徵實作。

以下是如何回填特徵實實實作的方法：

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. 根據需要的訊號建立新特徵。
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. 預先定義的回填間隔包括1、7、14和30天。您也可以選擇最多30天的自訂日期範圍。
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >特徵回填和估計不適用於使用下列運算元運算式的特徵：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 建立特徵。

在建立特徵後，您將看到其實施統計資料中包含的回填實作。

## Trait Backfilling Latency {#trait-backfilling-latency}

新建立的特徵會在建立後的兩到三小時開始擷取觀眾。However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每個月回填高達50個特徵，並在每個月的天內重設回填計數器。

>[!NOTE]
>
>特徵回填配額不會從前幾個月延續。例如，如果您本月回填30個特徵，則下個月的特徵回填配額會重設為50個，而非70個。

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.