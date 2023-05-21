---
description: 批量刪除允許您通過單個操作刪除多個段、特徵、資料夾、派生信號、資料源、模型和目標。 按照以下說明進行批量刪除請求。
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: 大量刪除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# 大量刪除{#bulk-delete}

批量刪除允許您通過單個操作刪除多個段、特徵、資料夾、派生信號、資料源、模型和目標。 按照以下說明進行批量刪除請求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果將段映射到目標，則目標映射的批量刪除將失敗。 在嘗試批量刪除目標之前，請在用戶介面中從該目標中刪除段。 此外，特徵和段資料夾必須為空，然後才能刪除它們。

要刪除多個項目，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 頁籤，並複製要添加的項的建立標題。
2. 按一下 **[!UICONTROL Delete]** 頁籤。
3. 將刪除標題貼上到更新工作表的第一行。
4. 貼上或鍵入要刪除的對象的ID（在標題下的列中）。
5. 提供所需 [登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 按一下 **[!UICONTROL Submit]**。

   工作表將建立 [!UICONTROL Results] 的雙曲餘切值。 的 [!UICONTROL Results] 列返回一條消息，指明該項是否已被刪除或出現錯誤消息。
在輸入資料之前，批量更新工作表應類似於以下內容：

![](assets/delete.png)

如果批量更新返回錯誤或失敗，請參見 [批量管理工具故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
