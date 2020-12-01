---
description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者資料目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期及實現頻率。 對於每個區段，您可以檢視其SID、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID(UUID)的訪客描述檔。 訪客資料檢視器有助於疑難排解。
keywords: location;location parameter
seo-description: 使用「訪客資料檢視器」可顯示目前瀏覽器的使用者資料目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期及實現頻率。 對於每個區段，您可以檢視其SID、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID(UUID)的訪客描述檔。 訪客資料檢視器有助於疑難排解。
seo-title: 訪客設定檔檢視器
solution: Audience Manager
title: 訪客設定檔檢視器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%

---


# 訪客設定檔檢視器 {#visitor-profile-viewer}

使用[!UICONTROL Visitor Profile Viewer]可顯示目前瀏覽器的使用者描述檔目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其[!UICONTROL SID]、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期及實現頻率。 對於每個區段，您可以檢視其[!UICONTROL SID]、名稱和區段成員資格日期。 您也可以檢視其他Audience Manager描述檔ID([!UICONTROL UUID])的訪客描述檔。 [!UICONTROL Visitor Profile Viewer]有助於疑難排解。

>[!NOTE]
>
>* 存取需要[!UICONTROL Administrator]權限。
>* 在使用者介面中出現已實現區段和已登入特徵的相關資訊之前，會有24小時的延遲。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *（可選）按* 一下特徵名稱，以在中顯示該特徵 [!UICONTROL Trait Builder]。

   如需詳細資訊，請參閱[Traits](../features/traits/trait-details-page.md)。

1. *（可選）按* 一下區段名稱，以在中顯示該區段 [!UICONTROL Segment Builder]。

   如需詳細資訊，請參閱[區段](../features/segments/segments-purpose.md)。

1. *（條件性）* 在方 **[!UICONTROL UUID]** 塊中，指定另一個Audience Manager描述檔ID，然後按一下 **[!UICONTROL Refresh]** 以檢視該使用者的特徵和區段。