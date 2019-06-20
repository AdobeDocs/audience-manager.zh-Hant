---
description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者描述檔狀態，包括其特徵和區段。對於每個特徵，您可以檢視其SID、名稱、關於訪客特徵的實作方式(第一方或第三方)、實作日期和實作頻率。您可以針對每個區段檢視其SID、名稱和區段成員資格日期。您也可以檢視另一個Audience Manager設定檔ID(UUID)的訪客描述檔。「訪客資料檢視器」有助於疑難排解。
keywords: 地點；位置參數
seo-description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者描述檔狀態，包括其特徵和區段。對於每個特徵，您可以檢視其SID、名稱、關於訪客特徵的實作方式(第一方或第三方)、實作日期和實作頻率。您可以針對每個區段檢視其SID、名稱和區段成員資格日期。您也可以檢視另一個Audience Manager設定檔ID(UUID)的訪客描述檔。「訪客資料檢視器」有助於疑難排解。
seo-title: 訪客資料檢視器
solution: Audience Manager
title: 訪客資料檢視器
uuid: 77ffe134-e08 f-41de-8fc4-15494847b1 d0
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Visitor Profile Viewer {#visitor-profile-viewer}

Use the [!UICONTROL Visitor Profile Viewer] to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its [!UICONTROL SID], name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its [!UICONTROL SID], name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID ([!UICONTROL UUID]). The [!UICONTROL Visitor Profile Viewer] is helpful for troubleshooting purposes.

>[!NOTE]
>
>* Access requires [!UICONTROL Administrator] permissions.
>* 在使用者介面中，有關實現區段和已登錄特性的資訊會延遲24小時。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Visitor Profile Viewer]**.

1. *(可選)* 按一下特徵名稱，以顯示 [!UICONTROL Trait Builder]該特徵。

   For more information, see [Traits](../features/traits/trait-details-page.md).

1. *(可選)* 按一下區段名稱，在其中顯示該區段 [!UICONTROL Segment Builder]。

   For more information, see [Segments](../features/segments/segments-purpose.md).

1. *(條件性)* 在 **[!UICONTROL UUID]** 方塊中指定另一個Audience Manager描述檔ID，然後按一下 **[!UICONTROL Refresh]** 以檢視該使用者的特徵和區段。