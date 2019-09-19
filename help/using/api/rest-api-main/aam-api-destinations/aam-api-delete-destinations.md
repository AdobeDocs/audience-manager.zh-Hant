---
description: 可讓您移除目標和區段對應的DELETE和POST方法。
seo-description: 可讓您移除目標和區段對應的DELETE和POST方法。
seo-title: 刪除目標
solution: Audience Manager
title: 刪除目標
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# 刪除目標 {#delete-destinations}

`DELETE` 和可 `POST` 讓您移除目標和區段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 刪除目標

移除 `DELETE` 目標的方法。

>[!NOTE]
>
>您必須先移除所有區段對應，才能刪除目標。

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 回應：如果成功， `204 No Content` 則傳回程式碼。

## 批量刪除目標

使用此方法刪除多個 `POST` 目標。 將目標ID( `destinationId`)與請求主體中的陣列一起傳遞。

* 請求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 回應：如果成功， `204 No Content` 則傳回程式碼。

## 依區段對應ID刪除目標映射

根據 `POST` 指定的區段ID移除目標映射的方法。

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 回應：如果成功， `204 No Content` 則傳回程式碼。