---
description: 將「傳遞效能」報告日誌檔案中的資料放入僅包含ID的表中。 將非ID元資料放在單獨的查找表中，以幫助減少檔案大小和處理時間。
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: 使用查閱表格縮短記錄檔處理時間
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 18%

---

# 使用查閱表格縮短記錄檔處理時間{#improve-log-file-processing-times-with-lookup-tables}

將「傳遞效能」報告日誌檔案中的資料放入僅包含ID的表中。 將非ID元資料放在單獨的查找表中，以幫助減少檔案大小和處理時間。

<!-- 

c_lookup_tables.xml

 -->

## 日誌檔案元資料增加了檔案大小和處理時間

使用的典型日誌檔案 [!UICONTROL Delivery Performance] 報告通常包含數千行和幾十列。 它由數字ID和人類可讀資訊組成，如創意人士、廣告商、插入訂單等。

此非ID資訊稱為 *`metadata`* （即有關其他資訊的資訊），並寫入日誌檔案的每一行。

然而， [!UICONTROL Delivery Performance] 報告主要與日誌檔案中的ID一起工作。 元資料是有用的，但是重複性很強。 它增加了檔案大小和資料接收時間。

## 使用索引表減小檔案大小並縮短處理時間

為幫助提高效能，主資料檔案應僅包含ID。 將元資料放在單獨的查找（或索引）表中，並將這些記錄與主檔案連結，其中有一個鍵變數是兩者共同的。

## 查找表如何減小檔案大小

假設您有一個看起來與下面類似的資料檔案。

| 使用者 ID | 廣告 ID | 廣告名稱 | 訂購 ID | 訂單名稱 | 廣告主 ID | 廣告商名稱 |
|---|---|---|---|---|---|---|
| 1 | 111 | 鞋A | 456 | 運動鞋 | 27 | 公司A |
| 2 | 111 | 鞋A | 456 | 運動鞋 | 27 | 公司A |
| 3 | 111 | 鞋A | 456 | 運動鞋 | 27 | 公司A |
| 4 | 222 | 鞋B | 789 | 遠足 | 14 | 公司B |
| 5 | 222 | 鞋B | 789 | 遠足 | 14 | 公司B |

<br> 

這是刪除了元資料的同一日誌檔案。 如果檔案僅包含ID，則檔案較小，處理起來也更容易。

| 使用者 ID | 廣告 ID | 訂購 ID | 廣告主 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

下面的查找檔案保存元資料，並可以用Ad ID連結回主檔案。 同時注意大小。 您不需要多次重複每個廣告商，而只需為每個廣告商提供一個參考。

| 廣告 ID | 廣告名稱 | 訂單名稱 | 廣告商名稱 |
|---|---|---|---|
| 111 | 鞋A | 運動鞋 | 公司A |
| 222 | 鞋B | 遠足 | 公司B |

## API可消除對查找表的需求

如果您的廣告服務系統具有API，則可能不需要在查找檔案中發送元資料。 我們可以通過API獲取這些資訊。 在這種情況下，日誌檔案應僅包含ID。 我們將與您合作，以確定是否可以通過API獲取元資料。
