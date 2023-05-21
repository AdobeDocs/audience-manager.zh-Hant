---
description: 批量建立允許您使用單個操作構建多個資料源、派生的信號、段、特徵和其他項。 按照以下說明進行批量建立請求。
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 大量建立
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# 大量建立{#bulk-create}

批量建立允許您使用單個操作構建多個資料源、派生的信號、段、特徵和其他項。 按照以下說明進行批量建立請求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>不要在批量建立請求中混合對象類型。 每個對象的標頭是唯一的，無法組合。 清除工作表，並對不同的項目單獨提出請求。

要批量建立對象，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 頁籤，並複製要添加的項的建立標題。
2. 按一下 **[!UICONTROL Create]** 頁籤。
3. 將建立標題貼上到更新工作表的第一行。
4. 根據標題標籤貼上或鍵入要更改為相應列的資料。
5. 在工作表工具欄中，按一下與要更新的項目匹配的建立按鈕。
此操作將開啟 [!UICONTROL Account Information] 對話框。
6. 提供所需 [登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 按一下 **[!UICONTROL Submit]**。

工作表將建立 [!UICONTROL Results] 的雙曲餘切值。 的 [!UICONTROL Results] 列返回成功操作的JSON響應。 查看 [REST API](../../api/rest-api-main/rest-api-main.md) 的上界。 在輸入資料之前，批量建立工作表應與以下示例類似。 注意，此處不顯示所有不同的建立選項。 其中包括此選項，以幫助您瞭解完成的工作表的外觀。

![](assets/cretetraits.png)

如果批量更新返回錯誤或失敗，請參見 [批量管理工具故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
