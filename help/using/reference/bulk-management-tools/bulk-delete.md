---
description: 大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號和目的地。請依照下列指示進行大量刪除請求。
seo-description: 大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號和目的地。請依照下列指示進行大量刪除請求。
seo-title: 大量刪除
solution: Audience Manager
title: 大量刪除
uuid: 679cde46-09fb-45c6-b84 d-47e00 e0 e7 c0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號和目的地。請依照下列指示進行大量刪除請求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果您有對應至目的地的區段，目的地對應的大量刪除將會失敗。嘗試大量刪除目的地前，請先從使用者介面中移除您的區段。此外，特徵和區段資料夾必須是空白的，才能加以刪除。

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. 將刪除標題貼入更新工作表的第一列。
4. 在標題下方的欄中，貼上或輸入您要刪除之物件的ID。
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 欄會傳回一則訊息，指出該項目是否已刪除或錯誤訊息。
在輸入資料之前，您的大量更新工作表看起來應該類似下列：

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
