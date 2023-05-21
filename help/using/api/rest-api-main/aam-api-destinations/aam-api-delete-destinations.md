---
description: DELETE和POST方法，用於刪除目標和段映射。
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: 刪除目的地
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 6%

---

# 刪除目的地 {#delete-destinations}

`DELETE` 和 `POST` 用於刪除目標和段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 刪除目標

A `DELETE` 刪除目標的方法。

>[!NOTE]
>
>必須先刪除所有段映射，然後才能刪除目標。

* 請求: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 響應：返回代碼 `204 No Content` 成功。

## 批量刪除目標

使用此項刪除多個目標 `POST` 的雙曲餘切值。 傳入目標ID( `destinationId`)。

* 請求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 響應：返回代碼 `204 No Content` 成功。

## 按段映射ID刪除目標映射

A `POST` 根據指定的段ID刪除目標映射的方法。

* 請求: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 響應：返回代碼 `204 No Content` 成功。
