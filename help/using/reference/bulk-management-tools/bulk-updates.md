---
description: 大量更新可讓您在單一作業中編輯多個區段、特徵和區段或特徵資料夾元素。請依照下列指示進行大量更新。
keywords: Baaam
seo-description: 大量更新可讓您在單一作業中編輯多個區段、特徵和區段或特徵資料夾元素。請依照下列指示進行大量更新。
seo-title: 大量更新
solution: Audience Manager
title: 大量更新
uuid: 22f1badd-a274-4d3 e-9957-a24 bf8 c1 d0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

大量更新可讓您在單一作業中編輯多個區段、特徵和區段或特徵資料夾元素。請依照下列指示進行大量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. 將更新標題貼入更新工作表的第一列。請注意下列事項：

   * 更新資料夾時，所有標題都是必要的。
   * 更新區段或特徵時，您只需要區段ID(SID)和需要變更的標題元素。刪除未使用的標題。

1. 根據標題標籤，貼上或輸入您要變更為對應欄的資料。
1. 在工作表工具列中，按一下符合您正在更新之項目的更新按鈕。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 欄會傳回JSON回應以獲得成功操作。See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 在輸入資料之前，您的大量更新工作表看起來應該類似下列：

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
