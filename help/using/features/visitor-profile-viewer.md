---
description: 使用訪客設定檔檢視器來顯示目前瀏覽器之使用者設定檔的目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、訪客特徵實現方式（第一方或第三方）的詳細資訊、實現日期和實現頻率。 您可以檢視每個區段的SID、名稱和區段會籍日期。 您也可以檢視其他Audience Manager設定檔ID (UUID)的訪客設定檔。 訪客資料檢視器可用於疑難排解。
keywords: 位置；位置引數
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 訪客資料檢視器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# 訪客資料檢視器 {#visitor-profile-viewer}

使用[!UICONTROL Visitor Profile Viewer]顯示目前瀏覽器之使用者設定檔的目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其[!UICONTROL SID]、名稱、訪客特徵實現方式的詳細資訊（第一方或第三方）、實現日期和實現頻率。 對於每個區段，您可以檢視其[!UICONTROL SID]、名稱和區段會籍日期。 您也可以檢視其他Audience Manager設定檔識別碼([!UICONTROL UUID])的訪客設定檔。 [!UICONTROL Visitor Profile Viewer]有助於疑難排解。

>[!NOTE]
>
>* 存取需要[!UICONTROL Administrator]許可權。
>* 使用者介面中會延遲24小時才顯示已實現區段和已上線特徵的資訊。

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 按一下&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**。

1. *（選擇性）*&#x200B;按一下特徵名稱，即可在[!UICONTROL Trait Builder]中顯示該特徵。

   如需詳細資訊，請參閱[特徵](../features/traits/trait-details-page.md)。

1. *（選擇性）*&#x200B;按一下區段名稱，即可在[!UICONTROL Segment Builder]中顯示該區段。

   如需詳細資訊，請參閱[區段](../features/segments/segments-purpose.md)。

1. *（條件式）*&#x200B;在&#x200B;**[!UICONTROL UUID]**&#x200B;方塊中，指定其他Audience Manager設定檔ID，然後按一下&#x200B;**[!UICONTROL Refresh]**&#x200B;以檢視該使用者的特徵和區段。
