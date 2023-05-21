---
description: 批量估計基於段規則返回段大小資料。 按照這些說明進行批量評估請求。
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: 大量估計
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# 大量估計{#bulk-estimates}

批量估計基於段規則返回段大小資料。 按照這些說明進行批量評估請求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

要進行批量更新，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 頁籤並複製 [!UICONTROL Estimate Segment Size] 標題。
2. 按一下 **[!UICONTROL Estimate]** 頁籤。
3. 將估計題頭貼上到估計工作表的第一行中。
4. 根據標題標籤貼上或鍵入要更改為相應列的資料。
5. 在工作表工具欄中，按一下與要更新的項目匹配的建立按鈕。
此操作將開啟 [!UICONTROL Account Information] 對話框。
6. 提供所需 [登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 按一下 **[!UICONTROL Submit]**。

此操作將建立 [!UICONTROL Response] 列，其中包含估計段大小資料。 在輸入資料之前，您的批量估計工作表應與以下內容類似：

![](assets/estimate.png)
如果批量更新返回錯誤或失敗，請參見 [批量管理工具故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
