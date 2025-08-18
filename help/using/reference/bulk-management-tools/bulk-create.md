---
description: 大量建立可讓您透過單一操作建構多個資料來源、衍生訊號、區段、特徵和其他專案。 依照這些指示進行大量建立請求。
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 大量建立
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# 大量建立{#bulk-create}

大量建立可讓您透過單一操作建構多個資料來源、衍生訊號、區段、特徵和其他專案。 依照這些指示進行大量建立請求。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>在[ UI中指派的](../../features/administration/administration-overview.md)RBAC群組許可權[!DNL Audience Manager]已在[!UICONTROL Bulk Management Tools]中接受。

>[!CAUTION]
>
>請勿在大量建立請求中混合使用物件型別。 每個物件的標題都是唯一的，無法合併。 清除工作表，並針對不同料號提出個別請求。

若要大量建立物件，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下「**[!UICONTROL Headers]**」標籤，並複製您要新增之專案的建立標題。
2. 按一下「**[!UICONTROL Create]**」標籤。
3. 將建立標題貼到更新工作表的第一個資料列。
4. 根據標題標籤，將您要變更的資料貼上或輸入至對應的欄。
5. 在工作表工具列中，按一下符合您要更新之料號的「建立」按鈕。
此動作會開啟[!UICONTROL Account Information]對話方塊。
6. 提供必要的[登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)並按一下&#x200B;**[!UICONTROL Submit]**。

工作表會建立[!UICONTROL Results]欄。 [!UICONTROL Results]欄傳回成功作業的JSON回應。 如需範例，請參閱[REST API](../../api/rest-api-main/rest-api-main.md)。 在輸入資料之前，大量建立工作表看起來應該類似下列範例。 請注意，此處不顯示所有不同的建立選項。 其中包括此專案以協助您瞭解完整工作表的外觀。

![](assets/cretetraits.png)

如果大量更新傳回錯誤或失敗，請參閱[大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
