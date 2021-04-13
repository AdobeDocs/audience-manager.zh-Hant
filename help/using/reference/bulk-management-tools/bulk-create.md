---
description: 「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。
seo-description: 「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。
seo-title: 大量建立
solution: Audience Manager
title: 大量建立
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 大量建立{#bulk-create}

「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[UI中指](../../features/administration/administration-overview.md) 派的RBAC群 [!DNL Audience Manager] 組權限在中接受 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>請勿在大量建立請求中混用物件類型。 每個物件的標題都是唯一的，無法組合。 清除工作表，並對不同的物料單獨請求。

要批量建立對象，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下&#x200B;**[!UICONTROL Headers]**&#x200B;標籤，並複製您要新增之項目的建立標題。
2. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;頁籤。
3. 將建立標題貼入更新工作表的第一列。
4. 根據標題標籤，貼上或輸入要變更為對應欄的資料。
5. 在工作表工具列中，按一下符合您正在更新之項目的建立按鈕。
此操作將開啟[!UICONTROL Account Information]對話框。
6. 提供所需的[登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然後按一下&#x200B;**[!UICONTROL Submit]**。

工作表會建立[!UICONTROL Results]欄。 [!UICONTROL Results]欄會傳回成功作業的JSON回應。 如需範例，請參閱[REST API](../../api/rest-api-main/rest-api-main.md)。 在輸入資料之前，您的大量建立工作表看起來應類似下列範例。 注意，此處不顯示所有不同的建立選項。 其中包含此功能，可協助您瞭解完成的工作表的外觀。

![](assets/cretetraits.png)

如果您的批量更新傳回錯誤或失敗，請參閱[批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
