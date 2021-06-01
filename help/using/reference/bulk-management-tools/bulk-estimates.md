---
description: 大量預估會根據區段規則傳回區段大小資料。 請依照下列指示進行大量預估請求。
seo-description: 大量預估會根據區段規則傳回區段大小資料。 請依照下列指示進行大量預估請求。
seo-title: 大量估計
solution: Audience Manager
title: 大量估計
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 大量估計{#bulk-estimates}

大量預估會根據區段規則傳回區段大小資料。 請依照下列指示進行大量預估請求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

若要進行大量更新，請開啟[!UICONTROL Bulk Management Tools]工作表，然後：

1. 按一下&#x200B;**[!UICONTROL Headers]**&#x200B;標籤並複製[!UICONTROL Estimate Segment Size]標題。
2. 按一下&#x200B;**[!UICONTROL Estimate]**&#x200B;標籤。
3. 將預估標題貼入預估工作表的第一列。
4. 貼上或輸入您要根據標題標籤，變更為對應欄的資料。
5. 在工作表工具列中，按一下符合您要更新之項目的建立按鈕。
此操作將開啟[!UICONTROL Account Information]對話框。
6. 提供所需的[登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)，然後按一下&#x200B;**[!UICONTROL Submit]**。

此動作會在工作表中建立[!UICONTROL Response]欄，其中包含預計的區段大小資料。 在輸入資料之前，您的大量預估工作表看起來應類似下列：

![](assets/estimate.png)
如果您的大量更新傳回錯誤或失敗，請參閱 [大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
