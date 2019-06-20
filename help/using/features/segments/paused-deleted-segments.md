---
description: 說明當您使用「區段產生器」暫停或刪除作用中區段時，區段使用者、資料和目的地的效果。
seo-description: 說明當您使用「區段產生器」暫停或刪除作用中區段時，區段使用者、資料和目的地的效果。
seo-title: 已暫停和已刪除區段
solution: Audience Manager
title: 已暫停和已刪除區段
uuid: 88efe4af-f9 a4-4bce-920a-352bd4 d505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## 存取暫停和刪除控制項

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). 這些功能會影響區段，如下所述。

## 已暫停的區段功能

暫停(停用)區段：

* 停止劃分新的合格使用者。
* 保留使用者的分段狀態/會籍(不會將使用者從區段移除)。
* 保留在區段清單中，可重新啓動。
* 不會將資料傳送至相關聯的目的地。
* 傳回可用報表中的資料(直到停用日期)。

## 已刪除區段功能

已刪除的區段：

* 停止劃分新的合格使用者。
* 從區段會籍中移除符合資格的使用者。
* 從區段清單中移除。
* 無法解除刪除。
* 不會將資料傳送至相關聯的目的地。
* 無法在可用報表中傳回資料。

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).