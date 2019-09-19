---
description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者資料目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期及實現頻率。 對於每個區段，您可以檢視其SID、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID(UUID)的訪客描述檔。 訪客資料檢視器有助於疑難排解。
keywords: 位置；位置參數
seo-description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者資料目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期及實現頻率。 對於每個區段，您可以檢視其SID、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID(UUID)的訪客描述檔。 訪客資料檢視器有助於疑難排解。
seo-title: 訪客資料檢視器
solution: Audience Manager
title: 訪客資料檢視器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


#  訪客資料檢視器 {#visitor-profile-viewer}

使用 [!UICONTROL Visitor Profile Viewer] 以顯示目前瀏覽器的使用者描述檔目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其 [!UICONTROL SID]、名稱、訪客特徵如何實現的詳細資訊（第一方或第三方）、實現日期，以及實現的頻率。 您可以檢視每個區段的 [!UICONTROL SID]名稱、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID([!UICONTROL UUID])的訪客描述檔。 這 [!UICONTROL Visitor Profile Viewer] 有助於疑難排解。

>[!NOTE]
>
>* 存取需要 [!UICONTROL Administrator] 權限。
>* 在使用者介面中出現已實現區段和已登入特徵的相關資訊之前，會有24小時的延遲。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Visitor Profile Viewer]**.

1. *（選擇性）* ，按一下特徵名稱，在中顯示該特徵 [!UICONTROL Trait Builder]。

   For more information, see [Traits](../features/traits/trait-details-page.md).

1. *（可選）* ，按一下區段名稱，在中顯示該區段 [!UICONTROL Segment Builder]。

   For more information, see [Segments](../features/segments/segments-purpose.md).

1. *（條件性）* ，在方塊中指定 **[!UICONTROL UUID]** 另一個Audience manager描述檔ID，然後按一下 **[!UICONTROL Refresh]** ，以檢視該使用者的特徵和區段。