---
description: 說明當您使用「區段產生器」暫停或刪除作用中的區段時，區段使用者、資料和目的地所受的影響。
seo-description: 說明當您使用「區段產生器」暫停或刪除作用中的區段時，區段使用者、資料和目的地所受的影響。
seo-title: 暫停和刪除的區段
solution: Audience Manager
title: 暫停和刪除的區段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 暫停和刪除的區段 {#paused-and-deleted-segments}

說明當您使用暫停或刪除作用中區段時，區段使用者、資料和目的地的影響 [!UICONTROL Segment Builder]。

## 存取暫停和刪除控制項

將滑鼠指標暫留在區段清單中的區段名稱上， **[!UICONTROL pause]** 以顯示 **[!UICONTROL delete]** 和圖示(在欄 [!UICONTROL Actions] 中)。 這些功能會影響區段，如下所述。

## 暫停的區段功能

暫停（停用）的區段：

* 停止劃分新的合格使用者。
* 保留使用者的區段狀態／會籍（不會從區段中移除使用者）。
* 保留在區段清單中，並可重新啟動。
* 不傳送資料至相關的目的地。
* 傳回可用報表中的資料（截至停用日期）。

## 已刪除的區段功能

已刪除的區段：

* 停止劃分新的合格使用者。
* 從區段會籍中移除合格使用者。
* 已從區段清單中移除。
* 無法刪除。
* 不傳送資料至相關的目的地。
* 不會傳回可用報表中的資料。

>[!NOTE]
>
>您也可以使用方法暫停和刪除 [!DNL API] 區段。 如需詳細資訊，請參 [閱REST API](../../api/rest-api-main/rest-api-main.md)。