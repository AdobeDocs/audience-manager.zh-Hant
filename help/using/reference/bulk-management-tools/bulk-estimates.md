---
description: 大量估計會根據區段規則傳回區段大小資料。 請依照這些指示進行大量估計請求。
seo-description: 大量估計會根據區段規則傳回區段大小資料。 請依照這些指示進行大量估計請求。
seo-title: 大量估計
solution: Audience Manager
title: 大量估計
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# 大量估計{#bulk-estimates}

大量估計會根據區段規則傳回區段大小資料。 請依照這些指示進行大量估計請求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[UI中指](../../features/administration/administration-overview.md) 派的RBAC群 [!DNL Audience Manager] 組權限在中接受 [!UICONTROL Bulk Management Tools]。

若要進行大量更新，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下&#x200B;**[!UICONTROL Headers]**&#x200B;頁籤並複製[!UICONTROL Estimate Segment Size]標題。
2. 按一下&#x200B;**[!UICONTROL Estimate]**&#x200B;頁籤。
3. 將估計題頭貼上到估計工作表的第一行。
4. 根據標題標籤，貼上或輸入要變更為對應欄的資料。
5. 在工作表工具列中，按一下符合您正在更新之項目的建立按鈕。
此操作將開啟[!UICONTROL Account Information]對話框。
6. 提供所需的[登錄資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然後按一下&#x200B;**[!UICONTROL Submit]**。

此動作會在工作表中建立[!UICONTROL Response]欄，其中包含估計的區段大小資料。 在輸入資料之前，您的大量估計工作表看起來應類似下列：

![](assets/estimate.png)
如果您的大量更新傳回錯誤或失敗，請參 [閱批量管理工具疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。

