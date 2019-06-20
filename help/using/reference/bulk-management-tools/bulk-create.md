---
description: 大量建立可讓您使用單一作業建構多個資料來源、衍生的訊號、區段、特徵和其他項目。請依照下列指示進行大量建立請求。
seo-description: 大量建立可讓您使用單一作業建構多個資料來源、衍生的訊號、區段、特徵和其他項目。請依照下列指示進行大量建立請求。
seo-title: 大量建立
solution: Audience Manager
title: 大量建立
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

大量建立可讓您使用單一作業建構多個資料來源、衍生的訊號、區段、特徵和其他項目。請依照下列指示進行大量建立請求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>請勿在大量建立請求中混合物件類型。每個物件的標題都是唯一的，無法結合。清除工作表並對不同項目進行個別請求。

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. 將建立標題貼入更新工作表的第一列。
1. 根據標題標籤，貼上或輸入您要變更為對應欄的資料。
1. 在工作表工具列中，按一下符合您正在更新之項目的建立按鈕。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 欄會傳回JSON回應以獲得成功操作。See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 在輸入資料之前，您的大量建立工作表看起來應該類似下列範例。請注意，此處不會顯示所有不同的建立選項。此項目可協助您瞭解已完成的工作表看起來是甚麼樣子。

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
