---
description: 「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。
seo-description: 「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。
seo-title: 大量建立
solution: Audience Manager
title: 大量建立
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 大量建立{#bulk-create}

「大量建立」可讓您使用單一操作來建構多個資料來源、衍生訊號、區段、特徵和其他項目。 請依照下列指示進行大量建立請求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支 *援* 。 [!DNL Audience Manager]這種工具僅為方便和禮貌而提供。 若是大量變更，我們建議您改 [用Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>請勿在大量建立請求中混用物件類型。 每個物件的標題都是唯一的，無法組合。 清除工作表，並對不同的物料單獨請求。

要批量建立對象，請開啟工作 [!UICONTROL Bulk Management Tools] 表並：

1. 按一下 **[!UICONTROL Headers]** 標籤，並複製您要新增項目的建立標題。
1. Click the **[!UICONTROL Create]** tab.
1. 將建立標題貼入更新工作表的第一列。
1. 根據標題標籤，貼上或輸入要變更為對應欄的資料。
1. 在工作表工具列中，按一下符合您正在更新之項目的建立按鈕。
此動作會開啟對 [!UICONTROL Account Information] 話方塊。

1. 提供必要 [的登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然後按一 **[!UICONTROL Submit]**&#x200B;下。

工作表會建立 [!UICONTROL Results] 欄。 欄會 [!UICONTROL Results] 傳回成功作業的JSON回應。 如需范 [例，請參閱](../../api/rest-api-main/rest-api-main.md) REST API。 在輸入資料之前，您的大量建立工作表看起來應類似下列範例。 注意，此處不顯示所有不同的建立選項。 其中包含此功能，可協助您瞭解完成的工作表的外觀。

![](assets/cretetraits.png)

如果您的大量更新傳回錯誤或失敗，請參 [閱批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
