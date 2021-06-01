---
description: 說明使用「區段產生器」暫停或刪除作用中區段時，對區段使用者、資料和目的地的影響。
seo-description: 說明使用「區段產生器」暫停或刪除作用中區段時，對區段使用者、資料和目的地的影響。
seo-title: 暫停和刪除的區段
solution: Audience Manager
title: 暫停和刪除的區段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: 區段
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 6%

---

# 暫停和刪除的區段 {#paused-and-deleted-segments}

說明使用[!UICONTROL Segment Builder]暫停或刪除作用中區段時，對分段使用者、資料和目的地的影響。

## 存取暫停和刪除控制項

將滑鼠指標暫留在區段清單中的區段名稱上，以顯示&#x200B;**[!UICONTROL pause]**&#x200B;和&#x200B;**[!UICONTROL delete]**&#x200B;圖示（位於[!UICONTROL Actions]欄中）。 這些功能會影響區段，如下所述。

## 暫停的區段功能

暫停（停用）的區段：

* 停止劃分新的合格使用者。
* 保留使用者的區段狀態/成員資格（不會從區段中移除使用者）。
* 保留在區段清單中，即可重新啟動。
* 不會傳送資料至相關聯的目的地。
* 傳回可用報表中的資料（直到停用日期為止）。

## 已刪除的區段功能

已刪除的區段：

* 停止劃分新的合格使用者。
* 從區段成員資格中移除合格使用者。
* 會從區段清單中移除。
* 無法刪除。
* 不會傳送資料至相關聯的目的地。
* 不會傳回可用報表中的資料。

>[!NOTE]
>
>您也可以使用[!DNL API]方法來暫停和刪除區段。 如需詳細資訊，請參閱[REST API](../../api/rest-api-main/rest-api-main.md)。
