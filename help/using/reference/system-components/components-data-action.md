---
description: 資料動作元件包括客戶資料摘要、資料收集伺服器、SFTP/S3/HTTP發佈者、IRIS和設定檔快取伺服器。
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: 資料動作元件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# 資料動作元件{#data-action-components}

資料動作元件包括客戶資料摘要、資料收集伺服器、SFTP/S3/HTTP發佈者、IRIS和設定檔快取伺服器。

<!-- 

c_compact.xml

 -->

動作元件是系統和程式，可讓您在[!DNL Audience Manager]之內和之外行動資料，並（由於缺少更好的片語）處理這些動作。 這[!DNL Audience Manager]個元件包括：

## 客戶資料摘要 (CDF) {#cdf}

[!UICONTROL CDF]是每小時傳送給客戶的檔案。 這些檔案包含使用者ID以及關聯的區段ID、特徵ID和其他資料。 如需詳細資訊，請參閱[客戶資料摘要概觀](../../features/cdf-files.md)。

## 資料收集伺服器(DCS) {#dcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3]發行者會從[!UICONTROL Outbound Feed Converter]接收同步的ID資料。 當這些檔案準備就緒時，[!UICONTROL SFTP/S3 publishers]會將此資料傳送至使用者端指定的目的地。 這些檔案包含同步的ID資料，且將[!DNL Audience Manager]使用者ID (UUID)一對多對應至：

* 裝置ID/資料提供者ID (DPUUID)
* 合格的區段ID
* 特徵ID

[!DNL Audience Manager]客戶無法存取直接控制[!UICONTROL SFPT/S3 publishers]的功能。 客戶建立資料並將資料傳送到目的地時，會間接使用此服務。 [!UICONTROL SFTP/S3]系統基本上是排程間隔執行的自動化工作程式。

## IRIS {#iris}

在希臘神話中，[!UICONTROL Iris]是一個快速旅行和傳遞訊息的人物。 [!UICONTROL IRIS]系統是一個反映此人物古世界特徵的名稱空間。 用現代術語來說，[!UICONTROL IRIS]是低延遲、高頻率Cookie同步和資料傳輸服務。

[!UICONTROL IRIS]使用與[!UICONTROL SFTP/S3]系統相同的資料型別。 但是，[!UICONTROL IRIS]是不同的，因為它會即時傳送資料到目的地，而不是以設定的間隔。 這是獨立的系統，因為[!UICONTROL SFTP/S3]發佈者無法傳送資料至HTTP目的地，而且不是針對即時資料傳輸所設計。

沒有UI控制項可讓客戶直接使用[!UICONTROL IRIS]。 客戶在建立資料並將資料傳送到目的地時，以及針對需要快速資料傳輸的其他程式，間接使用[!UICONTROL IRIS]。

[!UICONTROL IRIS]服務和功能的範例包括：

* 為Cookie和區段提供快速（在30秒內）的同步處理。 它可以同步[!DNL Audience Manager] Cookie、合作夥伴Cookie，或兩者都同步。
* 即時資料傳輸。 [!UICONTROL IRIS]負責傳送即時區段資格事件給合作夥伴或其他目的地。 此資料為JSON格式，並透過HTTP `POST`要求傳送。

* 大量伺服器對伺服器資料傳輸：如果您與[!DNL Audience Manager]交換大量資料，[!UICONTROL IRIS]就是您的伺服器用來傳輸資料的系統。

* 可靠的基礎架構可大規模運作，且具備容錯功能。 支援[!UICONTROL IRIS]的系統包括Amazon SQS、Amazon EC2和Cassandra。

**區段對應規則**

為了最佳化[!UICONTROL IRIS]和區段目的地之間的流量，[!UICONTROL IRIS]會根據一組規則將區段傳送至目的地。

1. **新區段資格**：當裝置符合新區段的資格時，[!UICONTROL IRIS]會將與該裝置相關聯的所有區段傳送至對應至這些區段的所有目的地。

1. **新區段取消資格**：當裝置不再符合區段的資格時，[!UICONTROL IRIS]會將與該裝置相關聯的所有區段資格和取消資格，傳送至對應至這些區段的所有目的地。

1. **目的地對應更新**：當目的地對應更新時，[!UICONTROL IRIS]會將與裝置相關聯的所有區段傳送至對應至這些區段的所有目的地，下次在Audience Manager看到裝置時。

1. **裝置圖表更新**：當從用來評估區段的裝置圖表新增或移除任何裝置ID時，[!UICONTROL IRIS]會傳送與該裝置相關聯的所有區段到對應至這些區段的所有目的地，下次當Audience Manager看到該裝置時。

>[!IMPORTANT]
>
>如果Audience Manager連續3天未偵測到上述任何更新，[!UICONTROL IRIS]會將與裝置相關聯的所有區段，傳送至對應至這些區段的所有目的地，Audience Manager下次檢視裝置時。

**範例資料檔**

下列範例包含來自[!UICONTROL IRIS]的即時區段資料。 請記住，這僅是範例資料。 每個客戶可能有不同的格式需求，因此內容可能會有所不同。

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

## 設定檔快取伺服器(PCS) {#pcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。
