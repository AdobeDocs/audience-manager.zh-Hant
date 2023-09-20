---
description: 大量更新可讓您在單一操作中編輯多個區段、特徵、模型、資料來源，以及區段或特徵資料夾元素。 請依照這些指示進行大量更新。
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: 大量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 大量更新{#bulk-updates}

大量更新可讓您在單一操作中編輯多個區段、特徵、模型、資料來源，以及區段或特徵資料夾元素。 請依照這些指示進行大量更新。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] UI遵循於 [!UICONTROL Bulk Management Tools].

若要進行大量更新，請開啟 [!UICONTROL Bulk Management Tools] 工作表及：

1. 按一下 **[!UICONTROL Headers]** 定位並複製您要編輯之專案的更新標題。
2. 按一下 **[!UICONTROL Update]** 標籤。
3. 將更新標題貼到更新工作表的第一列。 請注意下列事項：

   * 更新資料夾時，需要所有標頭。
   * 更新區段或特徵時，您只需要區段ID (SID)和需要變更的標題元素。 刪除未使用的標頭。

4. 根據標題標籤，將您要變更的資料貼上或輸入至對應的欄。
5. 在工作表工具列中，按一下符合您要更新之料號的更新按鈕。
此動作會開啟 [!UICONTROL Account Information] 對話方塊。

6. 提供必要的 [登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 並按一下 **[!UICONTROL Submit]**.

   工作表會建立 [!UICONTROL Results] 欄。 此 [!UICONTROL Results] 欄會傳回成功作業的JSON回應。 請參閱 [REST API](../../api/rest-api-main/rest-api-main.md) 例如。 在輸入資料之前，大量更新工作表應該看起來類似下列：

![](assets/update.png)

如果大量更新傳回錯誤或失敗，請參閱 [大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md).
