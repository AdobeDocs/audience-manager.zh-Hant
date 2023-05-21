---
description: 本文介紹兩種功能，它們為「受眾實驗室重複分配模板」和「段抑制」提供了高級功能。
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: Audience Lab 進階功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# [!DNL Audience Lab] 高級功能 {#audience-lab-advanced-functionality}

本文介紹兩個功能，它們為 [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] 和 [!DNL Segment Holdout]。

## 重複分配模板 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在 [!DNL Audience Lab]，也請參見Wiki頁。 [!DNL Allocation Template] 表示建立test組時所做的各種選擇：

* 設備在test段之間的分佈；
* 將test段映射到目標；
* 用於test組的轉換特性；
* test組發佈到選定目標的日期範圍。

通過複製分配模板，您可以在新test組中為不同的基本段重複使用相同的test段和目標分佈。 分配模板的示例如下所示。 影像是從 [!UICONTROL Summary & Finalize] 的 **建立Test組** 工作流。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重複分配模板

建立初始test組，然後選擇 **[!UICONTROL Duplicate Allocation Template]** 在多個test組中重用相同設定。 例如，如果要在運行test時確定多個目標對多個段的有效性，則可以使用此功能。

1. 在「觀眾實驗室」主視圖中，搜索要在新test組中重現其分配模板的test組。 在下拉框中，選擇 **[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在 [!UICONTROL Create Test Group] 嚮導中，可以指定基段並更名test段。
3. 你 *不能* 修改：

   * 設備在test段之間的分佈；
   * 轉化特性；
   * test段到目標的映射。 您只能為需要映射鍵的目標填寫映射鍵。
   * test組將發佈到所選目標的日期範圍。

4. 查看在前面的步驟中添加的資訊，然後選擇 **[!UICONTROL Finalize Group]**。

## Test段抑制 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是高級功能，在客戶請求時激活。 請聯繫 [!DNL Customer Care] 或 [!DNL Adobe Consulting] 來激活此功能。

使用此功能可阻止部分觀眾被包括在test中。 您選擇的百分比不在test中。 這樣，您就可以測量和比較來自目標（在目標上激活）和非目標（抑制組）受眾的轉換數。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用Test段保持

1. 使用 [!UICONTROL Create Test Group] 的子菜單。
1. 在 **[!UICONTROL Allocate Test Segment]** 步驟，您可以選擇要拒絕測試的受眾的一部分。

   ![清單項](assets/test-segment-holdout.png)

1. 使用滑塊調整要阻止測試的設備數量。 請注意，Test段1和Test段2目前僅佔總設備的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 通過 **[!UICONTROL Create Test Group]** 工作流和選擇 **[!UICONTROL Finalize Group]** 當您對所選內容感到滿意時。 你現在有一個test小組，部分觀眾拒絕測試。
