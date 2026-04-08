---
description: 大量估計會根據區段規則傳回區段大小資料。 依照這些指示進行大量估計要求。
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: 大量估計
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# 大量估計{#bulk-estimates}

大量估計會根據區段規則傳回區段大小資料。 依照這些指示進行大量估計要求。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>在[ UI中指派的](../../features/administration/administration-overview.md)RBAC群組許可權[!DNL Audience Manager]已在[!UICONTROL Bulk Management Tools]中接受。

若要進行大量更新，請開啟[!UICONTROL Bulk Management Tools]工作表並：

1. 按一下「**[!UICONTROL Headers]**」索引標籤並複製[!UICONTROL Estimate Segment Size]標題。
2. 按一下「**[!UICONTROL Estimate]**」標籤。
3. 將預估標題貼到預估工作表的第一個資料列。
4. 根據標題標籤，將您要變更的資料貼上或輸入至對應的欄。
5. 在工作表工具列中，按一下符合您要更新之料號的「建立」按鈕。
此動作會開啟[!UICONTROL Account Information]對話方塊。
6. 提供必要的[登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)並按一下&#x200B;**[!UICONTROL Submit]**。

此動作會在工作表中建立包含預估區段大小資料的[!UICONTROL Response]欄。 在輸入資料之前，大量估計工作表應該看起來類似下列：

![](assets/estimate.png)
如果大量更新傳回錯誤或失敗，請參閱[大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
