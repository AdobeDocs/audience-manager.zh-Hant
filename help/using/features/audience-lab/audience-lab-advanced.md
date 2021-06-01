---
description: 本文說明為「Audience Lab重複配置範本」和「區段鑒效組」提供進階功能的兩項功能。
seo-description: 本文說明為「Audience Lab重複配置範本」和「區段鑒效組」提供進階功能的兩項功能。
seo-title: Audience Lab 進階功能
solution: Audience Manager
title: Audience Lab 進階功能
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# [!DNL Audience Lab] 進階功能  {#audience-lab-advanced-functionality}

本文介紹為[!DNL Audience Lab]提供高級功能的兩項功能：[!DNL Duplicate Allocation Template]和[!DNL Segment Holdout]。

## 重複分配模板{#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

在[!DNL Audience Lab]中， [!DNL Allocation Template]表示建立測試組時所做的各種選擇：

* 測試區段之間的裝置分佈；
* 測試區段對應至目的地；
* 您用於測試群組的轉換特徵；
* 測試群組發佈至所選目的地的日期範圍。

複製配置範本後，您就可以在新測試群組中，對不同的基本區段重複使用相同的測試區段和目的地分配。 配置範本的範例如下所示。 影像是從&#x200B;**建立測試群組**&#x200B;工作流程的[!UICONTROL Summary & Finalize]步驟中拍攝。

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 使用重複分配模板

建立初始測試組，然後選擇&#x200B;**[!UICONTROL Duplicate Allocation Template]**&#x200B;以跨多個測試組重複使用相同的設定。 例如，如果您執行測試，想要判斷多個目的地對多個區段的功效，則可使用此功能。

1. 在Audience Lab主檢視中，搜尋您要在新測試群組中重現其配置範本的測試群組。 在下拉框中，選擇&#x200B;**[!UICONTROL Duplicate Allocation Template]**。

   ![](assets/duplicate-allocation-template.png)

2. 在[!UICONTROL Create Test Group]精靈中，您可以指定基本區段，並視需要重新命名測試區段。
3. *不能*&#x200B;修改：

   * 測試區段之間的裝置分佈；
   * 轉換特徵；
   * 測試區段與目的地的對應。 您只能針對需要填入對應金鑰的目的地填入。
   * 您的測試群組將發佈至所選目的地的日期範圍。

4. 查看在前面的步驟中添加的資訊，並選擇&#x200B;**[!UICONTROL Finalize Group]**。

## 測試段鑒效{#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 是進階功能，可應客戶要求啟動。請聯繫[!DNL Customer Care]或[!DNL Adobe Consulting]以激活此功能。

使用此功能來預留部分對象不包含在測試中。 您選取的百分比不會列入測試。 如此一來，您可以測量並比較來自已鎖定目標（在目的地上啟動）和未鎖定目標（鑒效組）對象的轉換次數。

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 使用測試區段鑒效組

1. 使用[!UICONTROL Create Test Group]精靈建立新測試群組。
1. 在&#x200B;**[!UICONTROL Allocate Test Segment]**&#x200B;步驟中，您可以選取要預扣測試的對象部分。

   ![清單項目](assets/test-segment-holdout.png)

1. 使用滑桿調整要保留多少個設備以阻止測試。 請注意，測試區段1和測試區段2現在如何只佔總裝置的70%。

   ![](assets/test-segment-holdout-selected.png)

1. 完成&#x200B;**[!UICONTROL Create Test Group]**&#x200B;工作流程中的其餘步驟，並在您對您的選擇感到滿意時選擇&#x200B;**[!UICONTROL Finalize Group]**。 您現在有一個測試群組，其中一部分受眾未接受測試。
