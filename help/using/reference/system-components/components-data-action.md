---
description: 資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP出版業者、IRIS和描述檔快取伺服器。
seo-description: 資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP出版業者、IRIS和描述檔快取伺服器。
seo-title: 資料動作元件
solution: Audience Manager
title: 資料動作元件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP出版業者、IRIS和描述檔快取伺服器。

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] 是每小時傳送給客戶的檔案。這些包含使用者ID以及關聯的區段ID、特徵ID和其他資料。For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] 發佈商會收到來自該網站的同步化ID資料 [!UICONTROL Outbound Feed Converter]。When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* 裝置ID/資料供應商ID(DPUUID)
* 合格的區段ID
* 特徵ID

[!DNL Audience Manager] 客戶無法存取直接控制的功能 [!UICONTROL SFPT/S3 publishers]。客戶在建立和傳送資料至目的地時間接使用此服務。The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] 此系統是一個namesake，反映出此圖中這個人物的特性。In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] 與 [!UICONTROL SFTP/S3] 系統的類型相同。However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

[!UICONTROL IRIS] 服務和功能的範例包括：

* 快速(在30秒內)同步Cookie和區段。It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* 即時資料傳輸。[!UICONTROL IRIS] 負責將即時區段資格事件傳送給合作夥伴或其他目的地。This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* 適用於大規模且容錯的可靠基礎架構。Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**區段對應規則**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **新的細分資格**：當裝置符合新區段的資格時， [!UICONTROL IRIS] 請將所有與該裝置相關聯的區段傳送至對應至這些區段的所有目標。

1. **新細分優惠**&#x200B;資格：當裝置不再符合區段資格時， [!UICONTROL IRIS] 將所有與該裝置相關的資格和資格傳送給對應至這些區段的所有目的地。

1. **目的地對應更新**：當目標對應更新時， [!UICONTROL IRIS] 將所有與裝置相關的區段傳送至對應至這些區段的所有目標，下次Audience Manager看到裝置時。

1. **裝置圖表更新**：當任何裝置ID從用於評估區段的裝置圖表新增或移除時， [!UICONTROL IRIS] 請將與該裝置相關的所有區段傳送至對應至這些區段的所有目標，下次Audience Manager看到裝置時。

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**資料檔案範例**

The following example contains real-time segment data from [!UICONTROL IRIS]. 請記住，這僅是範例資料。每位客戶可能有不同的格式需求，因此內容可能會有所不同。

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
