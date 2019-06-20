---
description: 將「傳送效能」報表記錄檔中的資料放入包含ID的表格中。將非ID中繼資料放入個別查閱表格中，有助於減少檔案大小和處理時間。
seo-description: 將「傳送效能」報表記錄檔中的資料放入包含ID的表格中。將非ID中繼資料放入個別查閱表格中，有助於減少檔案大小和處理時間。
seo-title: 使用查閱表格改善記錄檔處理時間
solution: Audience Manager
title: 使用查閱表格改善記錄檔處理時間
uuid: ffc77618-474b-455e-9c91-15b32fc152a5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

將「傳送效能」報表記錄檔中的資料放入包含ID的表格中。將非ID中繼資料放入個別查閱表格中，有助於減少檔案大小和處理時間。

<!-- 

c_lookup_tables.xml

 -->

## 記錄檔中繼資料增加檔案大小和處理時間

[!UICONTROL Delivery Performance] 報表使用的典型記錄檔通常包含數千列和數十欄。其中包含數值ID和人類可讀資訊，例如創意人員、廣告商、插入訂單等。

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. 中繼資料很有用，但重復重復。它可提高檔案大小和擷取資料的時間。

## 使用索引表格減少檔案大小並縮短處理時間

為協助改善效能，您的主要資料檔案只應包含ID。將中繼資料放入另一個查閱(或索引)表格中，並將這些記錄連結至主要檔案，並使用兩者共同的關鍵變數。

## 查閱表格如何減少檔案大小

假設您的資料檔案看起來類似下方的資料檔案。

| 使用者 ID | 廣告 ID | 廣告名稱 | 訂購 ID | 訂單名稱 | 廣告主 ID | 廣告商名稱 |
|---|---|---|---|---|---|---|
| 1 | 111 | 鞋類A | 456 | Sneakers | 27 | A公司 |
| 2 | 111 | 鞋類A | 456 | Sneakers | 27 | A公司 |
| 3 | 111 | 鞋類A | 456 | Sneakers | 27 | A公司 |
| 4 | 222 | 鞋類B | 789 | Hiking | 14 | B公司 |
| 5 | 222 | 鞋類B | 789 | Hiking | 14 | B公司 |

<br> 

以下是移除中繼資料時的相同記錄檔。當檔案包含ID時，檔案較小且易於處理。

| 使用者 ID | 廣告 ID | 訂購 ID | 廣告主 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

以下查閱檔案保留中繼資料，並可使用廣告ID連結回主要檔案。請注意尺寸。您只需要對每個廣告商重復一個參照，而不需要多次重復廣告商。

| 廣告 ID | 廣告名稱 | 訂單名稱 | 廣告商名稱 |
|---|---|---|---|
| 111 | 鞋類A | Sneakers | A公司 |
| 222 | 鞋類B | Hiking | B公司 |

## API可免除查閱表格的需求

如果廣告服務系統有API，您可能不需要在查閱檔案中傳送中繼資料。我們可以透過API取得該資訊。此時，您的記錄檔應僅包含ID。我們將與您合作判斷中繼資料是否可透過API取得。

>[!MORE_贊_ this]
>
>* [傳送與效能報告](../../reporting/dynamic-reports/delivery-performance-report.md)

