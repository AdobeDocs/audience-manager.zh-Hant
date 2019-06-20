---
description: 可讓您移除目的地和區段映射的刪除和POST方法。
seo-description: 可讓您移除目的地和區段映射的刪除和POST方法。
seo-title: 刪除目的地
solution: Audience Manager
title: 刪除目的地
uuid: 38fb2228-e564-49a3-9930-3139f8799 a8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` 以及 `POST` 可讓您移除目的地和區段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 刪除目的地

A `DELETE` method that removes a destination.

>[!NOTE]
>
>您必須先移除所有區段映射，才能刪除目的地。

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## 大量刪除目的地

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* 請求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## 依區段對應ID刪除目的地映射

A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.