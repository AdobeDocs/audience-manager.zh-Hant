---
description: 大量刪除可讓您透過單一操作來移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目的地。 請依照下列指示提出大量刪除請求。
seo-description: 大量刪除可讓您透過單一操作來移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目的地。 請依照下列指示提出大量刪除請求。
seo-title: 大量刪除
solution: Audience Manager
title: 大量刪除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 大量刪除{#bulk-delete}

大量刪除可讓您透過單一操作來移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目的地。 請依照下列指示提出大量刪除請求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果區段對應至目的地，目的地對應的大量刪除將會失敗。 在嘗試大量刪除目的地之前，請先在使用者介面中從該目的地移除您的區段。 此外，特徵和區段資料夾必須空白，您才能刪除它們。

要刪除多個項目，請開啟[!UICONTROL Bulk Management Tools]工作表，然後：

1. 按一下&#x200B;**[!UICONTROL Headers]**&#x200B;標籤，然後複製您要新增之項目的建立標題。
2. 按一下&#x200B;**[!UICONTROL Delete]**&#x200B;標籤。
3. 將刪除標題貼入更新工作表的第一列。
4. 在標題下方的欄中，貼上或輸入您要刪除之物件的ID。
5. 提供所需的[登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)，然後按一下&#x200B;**[!UICONTROL Submit]**。

   工作表會建立[!UICONTROL Results]欄。 [!UICONTROL Results]列返回一條消息，指明該項是否已被刪除或是一條錯誤消息。
在輸入資料之前，您的大量更新工作表看起來應類似下列：

![](assets/delete.png)

如果您的批量更新返回錯誤或失敗，請參閱[批量管理工具的故障排除](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
