---
description: 使用訪問者配置檔案查看器可顯示當前瀏覽器的用戶配置檔案的當前狀態，包括其特徵和段。 對於每個特徵，您可以查看其SID、名稱、訪問者特徵如何實現的詳細資訊（第一方或第三方）、實現日期和實現頻率。 對於每個段，可以查看其SID、名稱和段成員身份日期。 您還可以查看其他Audience Manager配置檔案ID(UUID)的訪問者配置檔案。 訪問者配置檔案查看器有助於進行故障排除。
keywords: 位置；位置參數
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 訪客設定檔檢視器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# 訪客設定檔檢視器 {#visitor-profile-viewer}

使用 [!UICONTROL Visitor Profile Viewer] 顯示當前瀏覽器的用戶配置檔案的當前狀態，包括其特性和段。 對於每個特徵，你可以查看 [!UICONTROL SID]、名稱、訪問者特徵實現方式（第一方或第三方）的詳細資訊、實現日期和實現頻率。 對於每個段，可以查看 [!UICONTROL SID]、名稱和段成員資格日期。 您還可以查看其他Audience Manager配置檔案ID([!UICONTROL UUID])。 的 [!UICONTROL Visitor Profile Viewer] 有助於排除故障。

>[!NOTE]
>
>* 需要訪問 [!UICONTROL Administrator] 權限。
>* 在用戶介面中出現關於已實現的段和已連接的特徵的資訊之前，有24小時的延遲。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 按一下 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *（可選）* 按一下特徵名稱以在 [!UICONTROL Trait Builder]。

   有關詳細資訊，請參見 [性狀](../features/traits/trait-details-page.md)。

1. *（可選）* 按一下段名稱以在 [!UICONTROL Segment Builder]。

   有關詳細資訊，請參見 [段](../features/segments/segments-purpose.md)。

1. *（條件）* 在 **[!UICONTROL UUID]** 框中，指定另一個Audience Manager配置檔案ID，然後按一下 **[!UICONTROL Refresh]** 查看該用戶的特徵和段。
