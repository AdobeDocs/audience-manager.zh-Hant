---
description: 大量請求會傳回可用於「更新」、「建立」、「估計」和「刪除」工作表中不同標題的資料。
seo-description: 大量請求會傳回可用於「更新」、「建立」、「估計」和「刪除」工作表中不同標題的資料。
seo-title: 大量請求
solution: Audience Manager
title: 大量請求
uuid: 0192d26a-4ca-4e12-9fea-388b92b382f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

大量請求會傳回可用於「更新」、「建立」、「估計」和「刪除」工作表中不同標題的資料。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

[!UICONTROL Request] 工作表沒有自己的欄標題集，您不需要複製ID至任何欄。而是根據您在工具列中按一下的動作按鈕傳回資料。此外，選擇性報告功能會傳回像素引發的頻率計數，並針對數個固定時間間隔傳回獨特使用者計數。

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. 在工作表頂端的工具列中，按一下與您要處理之資料對應的請求按鈕。您可以要求：

   * 資料供應商ID
   * 衍生訊號
   * 目的地對應
   * 規則型和內嵌特性
   * 區段
   * 特徵和區段資料夾ID
   [!DNL Audience Manager] API會將大量資料寫入 [!UICONTROL Request] 工作表中。

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. 基礎日期/時間戳記會以UNIX UTC時間記錄。目前，工作表無法以可讀格式傳回日期/時間戳記。

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
