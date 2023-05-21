---
description: 批量更新允許您在單個操作中編輯多個段、特徵、模型、資料源以及段或特徵資料夾元素。 按照以下說明進行批量更新。
keywords: 巴
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: 大量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# 大量更新{#bulk-updates}

批量更新允許您在單個操作中編輯多個段、特徵、模型、資料源以及段或特徵資料夾元素。 按照以下說明進行批量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

要進行批量更新，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 頁籤，並複製要編輯的項的更新標題。
2. 按一下 **[!UICONTROL Update]** 頁籤。
3. 將更新標題貼上到更新工作表的第一行。 請注意：

   * 更新資料夾時，需要所有標頭。
   * 更新段或特徵時，您只需要段ID(SID)和需要更改的頭元素。 刪除未使用的標頭。

4. 根據標題標籤貼上或鍵入要更改為相應列的資料。
5. 在工作表工具欄中，按一下與要更新的項目匹配的更新按鈕。
此操作將開啟 [!UICONTROL Account Information] 對話框。

6. 提供所需 [登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 按一下 **[!UICONTROL Submit]**。

   工作表將建立 [!UICONTROL Results] 的雙曲餘切值。 的 [!UICONTROL Results] 列返回成功操作的JSON響應。 查看 [REST API](../../api/rest-api-main/rest-api-main.md) 的上界。 在輸入資料之前，批量更新工作表應類似於以下內容：

![](assets/update.png)

如果批量更新返回錯誤或失敗，請參見 [批量管理工具故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
