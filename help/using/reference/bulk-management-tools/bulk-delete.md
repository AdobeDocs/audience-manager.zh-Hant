---
description: 大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目標。 請依照下列指示進行大量刪除請求。
seo-description: 大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目標。 請依照下列指示進行大量刪除請求。
seo-title: 大量刪除
solution: Audience Manager
title: 大量刪除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 30d4cec4502a2cf8b217816ea4ae62eb1b22f641

---


# 大量刪除{#bulk-delete}

大量刪除可讓您透過單一作業移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目標。 請依照下列指示進行大量刪除請求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支 *援* 。 [!DNL Audience Manager]這種工具僅為方便和禮貌而提供。 若是大量變更，我們建議您改 [用Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果區段已映射至目標，則目標映射的大量刪除將失敗。 在嘗試大量刪除目標之前，先從使用者介面中的該目標移除區段。 此外，特徵和區段資料夾必須空白，您才能刪除它們。

要刪除多個物料，請開啟工作 [!UICONTROL Bulk Management Tools] 表並：

1. 按一下 **[!UICONTROL Headers]** 標籤，並複製您要新增項目的建立標題。
2. Click the **[!UICONTROL Delete]** tab.
3. 將刪除標題貼入更新工作表的第一列。
4. 在標題下方的欄中，貼上或輸入您要刪除的物件的ID。
5. 提供必要 [的登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然後按一 **[!UICONTROL Submit]**&#x200B;下。

   工作表會建立 [!UICONTROL Results] 欄。 該 [!UICONTROL Results] 列返回一條消息，指明該項是否已刪除或是一條錯誤消息。
在輸入資料之前，您的大量更新工作表看起來應類似下列：

![](assets/delete.png)

如果您的大量更新傳回錯誤或失敗，請參 [閱批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
