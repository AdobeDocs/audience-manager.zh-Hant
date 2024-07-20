---
description: 說明當您使用區段產生器暫停或刪除作用中的區段時，對分段使用者、資料和目的地的影響。
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: 暫停和刪除的區段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# 暫停和刪除的區段 {#paused-and-deleted-segments}

說明當您使用[!UICONTROL Segment Builder]暫停或刪除作用中的區段時，對分段的使用者、資料和目的地的影響。

## 存取「暫停」和「刪除」控制項

將游標停留在區段清單中的區段名稱上，以顯示&#x200B;**[!UICONTROL pause]**&#x200B;和&#x200B;**[!UICONTROL delete]**&#x200B;圖示（在[!UICONTROL Actions]欄中）。 這些功能會影響區段，如下所述。

## 暫停的區段功能

已暫停（已停用）的區段：

* 停止分段新的合格使用者。
* 保留使用者的分段狀態/會籍（不會從區段移除使用者）。
* 保留在區段清單中，並可重新啟用。
* 不會傳送資料至關聯的目的地。
* 傳回可用報表中的資料（截至停用日期）。

## 已刪除區段功能

已刪除的區段：

* 停止分段新的合格使用者。
* 從區段成員資格中移除合格使用者。
* 會從區段清單中移除。
* 無法取消刪除。
* 不會傳送資料至關聯的目的地。
* 不會傳回可用報表中的資料。

>[!NOTE]
>
>您也可以使用[!DNL API]方法暫停和刪除區段。 如需詳細資訊，請參閱[REST API](../../api/rest-api-main/rest-api-main.md)。
