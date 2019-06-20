---
description: 批量估計會根據區段規則傳回區段大小資料。請依照下列指示進行大量預估請求。
seo-description: 批量估計會根據區段規則傳回區段大小資料。請依照下列指示進行大量預估請求。
seo-title: 大量估計
solution: Audience Manager
title: 大量估計
uuid: 63b2f06a-8ba0-47a2-bd0 b-8039b2 d4 c95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

批量估計會根據區段規則傳回區段大小資料。請依照下列指示進行大量預估請求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. 將預估標題貼入估計工作表的第一列。
1. 根據標題標籤，貼上或輸入您要變更為對應欄的資料。
1. 在工作表工具列中，按一下符合您正在更新之項目的建立按鈕。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. 輸入資料之前，您的大量估計工作表看起來類似下列：

![](assets/estimate.png)如果批量更新傳回錯誤或失敗，請參閱 [「大量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)」。

