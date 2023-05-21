---
description: 描述使用段生成器暫停或刪除活動段時對分段用戶、資料和目標的影響。
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
ht-degree: 4%

---

# 暫停和刪除的區段 {#paused-and-deleted-segments}

描述在使用以下方式暫停或刪除活動段時對分段用戶、資料和目標的影響 [!UICONTROL Segment Builder]。

## 訪問暫停和刪除控制項

將滑鼠懸停在段清單中的段名稱上，以公開 **[!UICONTROL pause]** 和 **[!UICONTROL delete]** 表徵圖(在 [!UICONTROL Actions] 列)。 這些特徵會影響以下所述的段。

## 暫停的段功能

暫停（已停用）段：

* 停止對新的合格用戶進行分段。
* 保留用戶的分段狀態/成員資格（不會從段中刪除用戶）。
* 保留在段清單中，可重新激活。
* 不將資料發送到關聯的目標。
* 返回可用報表中的資料（截止到停用日期）。

## 已刪除的段功能

已刪除段：

* 停止對新的合格用戶進行分段。
* 從段成員身份中刪除限定用戶。
* 從段清單中刪除。
* 無法取消刪除。
* 不將資料發送到關聯的目標。
* 不返回可用報告中的資料。

>[!NOTE]
>
>也可以使用 [!DNL API] 的雙曲餘切值。 有關詳細資訊，請參見 [REST API](../../api/rest-api-main/rest-api-main.md)。
