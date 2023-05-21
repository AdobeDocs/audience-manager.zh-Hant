---
description: 本過程將指導您完成在「觀眾實驗」中建立、編輯或刪除test組所需的步驟
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: 管理測試群組
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---

# 管理測試群組 {#manage-test-groups}

此過程將引導您完成建立、編輯或刪除test組所需的步驟 [!UICONTROL Audience Lab]。

## 建立段Test組 {#create-test-groups}

### 必要條件

<!-- create-test-group.xml -->

* 你至少要有一個 **轉化性** 設定。 可以在 [特性生成器](../../features/traits/create-onboarded-rule-based-traits.md)按 **轉換** 類型。 有關轉換特性以及如何設定這些特性的詳細資訊，我們準備了 [視頻](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 為你。

   >[!IMPORTANT]
   >
   >[資料夾特徵](../../features/traits/about-folder-traits.md) 是 **不支援** 按 [!UICONTROL Audience Lab]。 設定 [事件類型](../../features/traits/create-onboarded-rule-based-traits.md) 資料夾特徵 **轉換** 不會在 [!UICONTROL Audience Lab] 特定資料夾特性。

* 對於使用 [基於角色的訪問控制](../../features/administration/administration-overview.md):分配 [!UICONTROL Audience Lab] [通配符權限](../../features/administration/administration-overview.md#wild-card-permissions) 至 **[!UICONTROL User Groups]** 提供訪問權限。 此權限允許用戶建立和查看test的結果。 用戶將只能使用他們擁有的資料源中的段 **讀** 和 **映射到目標** 權限。 用戶將只能使用來自他們具有的資料源的轉換特徵 **&quot;閱讀&quot;** 權限。 用戶也只能查看他們有權訪問的目標。 所以，在添加 [!DNL Audience Lab] 對組的通配符權限，確保組具有：
   * 讀取相關轉化特徵；
   * 讀取並映射相關分段以供test;
   * 訪問相關目標。

建立新 [!UICONTROL Segment Test Group]:

1. 選擇 **[!UICONTROL Create New Test Group]** 的 [!UICONTROL Audience Lab] 啟動嚮導的儀表板。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填寫 **[!UICONTROL Test Group Name]** 和 **[!UICONTROL Description]**。
   * 選擇 **[!UICONTROL Base Segment]** 在檔案瀏覽器中導航或在搜索欄中鍵入，通過按 **[!UICONTROL Choose Segment.]**
   * 可將test組另存為草稿，並稍後繼續處理。
   * 如果所選基本段已在其他test組中使用，則會顯示警報。 使用基段兩次可能會扭曲兩個test的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以建立 **最多15個test段** 並按您的意願劃分設備百分比。
   * 可通過按一下test段來編輯它們的名稱。
   * 分配新test段時，百分比會自動平均分到100%。 然後，您可以手動編輯百分比。 編輯百分比後，按一下複選框，確保百分比加起來達到100%，否則您將無法繼續下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要保留段的某一部分作為控制組，請選擇控制段。 控制組允許您查看您建立的test段與基準相比的影響。
   * 您可以在下拉清單中選擇一個test段作為控制段，也可以選擇 **[!UICONTROL None]** 無法控制。
   * 按一下 **[!UICONTROL Next]** 等你完事了。

1. **[!UICONTROL Select Conversion Traits]**

   * 通過在轉換特性窗口中鍵入來添加轉換特性。 這是 **強制** 步驟，除非您至少添加一個轉換特性，否則無法繼續執行下一步。
   * 如果您願意，最多可以添加5個轉換特性。
   * 如果您選擇已用於其他test組的轉換特性，則會顯示警報。
   * 注意，Audience Manager不支援使用 [資料夾特徵](/help/using/features/traits/about-folder-traits.md) 轉換特徵。 選擇資料夾特性作為轉換特性將導致在test中顯示0聚合和趨勢報告。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜索欄位中鍵入所需目標，或使用下拉箭頭。 [!UICONTROL Audience Lab] test段可以發送到URL、cookie或伺服器到伺服器目標。
   * 將段拖放到目標。
   * 在目標中刪除段後，填寫 **[!UICONTROL Destination Mapping Value]** 盲區。
   * 您可以將同一test段發送到多個目標，並且可以將多個test段添加到單個目標。
   * 如果目標不可用於某個test段，則根據 [資料導出控制項](../../features/data-export-controls.md)。
   * 用戶將僅根據 [RBAC用戶組](../../features/administration/administration-overview.md) 他們屬於。
   * 最後，您需要為test組選擇開始日期。 此日期標籤將test組發佈到目標的期間的開始。 選擇 **無結束日期** 段之不確定比較。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 只有在即時目標中支援已驗證的配置檔案。 如果具有該配置的配置檔案合併規則的test段被發送到基於檔案的伺服器到伺服器目標，則可能不會填充受眾。

   按一下 **[!UICONTROL Next]** 以審閱並完成test組。

1. **[!UICONTROL Summary & Finalize]**

   * 查看在前面的步驟中添加的資訊，然後選擇 **[!UICONTROL Finalize Group]**。
   * 請記住，完成test組後，它可以被複製或刪除，但不能編輯。

   >[!NOTE]
   >* 您可以在建立過程中的任意點保存test組，並稍後返回嚮導。 test組狀態將為 **[!UICONTROL Draft]** 在您完成段test組之前，test組不會向目標發送任何資料。
   >* 對於拔模test，可以通過按一下返回並編輯test組 **[!UICONTROL Edit]** 在主test組卡中 [!UICONTROL Audience Lab] 的子菜單。


## 編輯段Test組 {#edit-test-groups}

在 [!UICONTROL Audience Lab]，您只能編輯繪製test組。 在 [!UICONTROL Create Segment Test Group] 嚮導中，您可以將test組另存為草稿，並稍後繼續處理。

1. 導航到 [!UICONTROL Audience Lab] 的子菜單。
1. 搜索草稿test組，然後選擇 **[!UICONTROL Edit]** 控制項。
1. 恢復 [建立段Test組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 嚮導，選擇 **[!UICONTROL Finalize Group]** 等你完事了。

## 刪除段Test組 {#delete-test-groups}

1. 導航到 [!UICONTROL Audience Lab] 的子菜單。
1. 查找要刪除的test組。 您可以:

   * 按 **[!UICONTROL Delete]** 控制項在test組卡中，或
   * 按test組卡中的test組標題以轉到 [Test組資訊](../../features/audience-lab/audience-lab-information-view.md) 按 **[!UICONTROL Delete]** 的子菜單。

1. 對於 [已完成test段](../../features/audience-lab/audience-lab.md#status)，如果您願意，警報將提示您下載CSV檔案以保存報告。
