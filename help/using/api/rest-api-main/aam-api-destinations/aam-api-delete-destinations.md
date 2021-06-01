---
description: DELETE和POST方法，可讓您移除目的地和區段對應。
seo-description: DELETE和POST方法，可讓您移除目的地和區段對應。
seo-title: 刪除目的地
solution: Audience Manager
title: 刪除目的地
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 8%

---

# 刪除目的地 {#delete-destinations}

`DELETE` 和 `POST` 可讓您移除目的地和區段對應的方法。

<!-- r_delete_destinations_all.xml -->

## 刪除目的地

刪除目標的`DELETE`方法。

>[!NOTE]
>
>您必須先移除所有區段對應，才能刪除目的地。

* 請求: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 回應：如果成功，則傳回程式碼`204 No Content`。

## 大量刪除目的地

使用此`POST`方法刪除多個目標。 在要求內文中使用陣列傳遞目的地ID(`destinationId`)。

* 請求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 回應：如果成功，則傳回程式碼`204 No Content`。

## 依區段對應ID刪除目標對應

`POST`方法，會根據指定的區段ID移除目的地對應。

* 請求: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 回應：如果成功，則傳回程式碼`204 No Content`。
