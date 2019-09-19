---
description: 本文說明為Audience Lab重複配置範本和區段抑制提供進階功能的兩項功能。
seo-description: 本文說明為Audience Lab重複配置範本和區段抑制提供進階功能的兩項功能。
seo-title: Audience lab進階功能
solution: Audience Manager
title: Audience lab進階功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] 進階功能 {#audience-lab-advanced-functionality}

本文說明提供進階功能的兩項功能 [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] 和 [!DNL Segment Holdout]。

## 重複分配模板 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在中 [!DNL Audience Lab]，表示 [!DNL Allocation Template] 建立測試組時所做的各種選擇：

* 測試區段間的裝置分佈；
* 將測試區段對應至目標；
* 您用於測試群組的轉換特徵；
* 測試群組發佈至所選目的地的日期範圍。

透過複製配置範本，您可以在新的測試群組中，將相同的測試區段與目標分佈重複用於不同的基本區段。 配置範本的範例如下所示。 影像是從「建立測試群 [!UICONTROL Summary & Finalize] 組」工作流程 **的步驟中擷取** 。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重複的分配模板

建立初始測試群組，然後選取以 **[!UICONTROL Duplicate Allocation Template]** 在多個測試群組間重複使用相同的設定。 例如，如果您要執行測試，以決定多個區段的多個目的地的效能，則可使用此功能。

1. 在Audience lab主檢視中，搜尋您要在新測試群組中重制其配置範本的測試群組。 在下拉式方塊中，選取 **[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在精靈 [!UICONTROL Create Test Group] 中，您可以指定基本區段，並視需要重新命名測試區段。
3. 您無 *法修* 改：

   * 測試區段間的裝置分佈；
   * 轉換特徵；
   * 測試區段與目標的對應。 您只能為需要對應金鑰的目的地填寫對應金鑰。
   * 測試群組將發佈至所選目的地的日期範圍。

4. 檢閱您在先前步驟中新增的資訊，並選取 **[!UICONTROL Finalize Group]**。

## 測試區段抑制 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是進階功能，會在客戶要求時啟動。 請聯絡 [!DNL Customer Care] 或啟 [!DNL Adobe Consulting] 用此功能。

使用此功能可避免部分觀眾被納入測試。 您選取的百分比會排除在測試之外。 如此一來，您就可以測量並比較來自目標（在目標上啟動）和非目標（抑制群組）對象的轉換數。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用測試段抑制

1. 使用精靈建立新的測試 [!UICONTROL Create Test Group] 群組。
1. 在此步 **[!UICONTROL Allocate Test Segment]** 驟中，您可以選取要拒絕測試的部分對象。

   ![清單項目](assets/test-segment-holdout.png)

1. 使用滑桿來調整您要在測試中保留多少個裝置。 請注意，測試區段1和測試區段2現在僅佔總裝置的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 執行工作流程中的其餘步驟， **[!UICONTROL Create Test Group]** 並在您對 **[!UICONTROL Finalize Group]** 選取範圍感到滿意時選取。 您現在有測試群組，部分受眾拒絕測試。
