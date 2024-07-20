---
description: 可讓您移除目的地和區段對應的DELETE和POST方法。
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
ht-degree: 0%

---

# 刪除目的地 {#delete-destinations}

允許您移除目的地和區段對應的`DELETE`和`POST`方法。

<!-- r_delete_destinations_all.xml -->

## 刪除目的地

移除目的地的`DELETE`方法。

>[!NOTE]
>
>您必須先移除所有區段對應，才能刪除目的地。

* 要求： `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 回應：如果成功，則傳回代碼`204 No Content`。

## 大量刪除目的地

使用此`POST`方法移除多個目的地。 傳入目的地ID ( `destinationId`)，要求內文中包含陣列。

* 要求： `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 回應：如果成功，則傳回代碼`204 No Content`。

## 依區段對應ID刪除目的地對應

根據指定的區段ID移除目的地對應的`POST`方法。

* 要求： `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 回應：如果成功，則傳回代碼`204 No Content`。
