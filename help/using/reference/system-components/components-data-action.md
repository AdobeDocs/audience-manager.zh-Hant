---
description: 資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP發佈器、IRIS和描述檔快取伺服器。
seo-description: 資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP發佈器、IRIS和描述檔快取伺服器。
seo-title: 資料動作元件
solution: Audience Manager
title: 資料動作元件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# 資料動作元件{#data-action-components}

資料動作元件包括客戶資料饋送、資料收集伺服器、SFTP/S3/HTTP發佈器、IRIS和描述檔快取伺服器。

<!-- 

c_compact.xml

 -->

動作元件是可讓您將資料移入和移出[!DNL Audience Manager]的系統和程式，而且（因為沒有更好的片語）可以利用它。 這些[!DNL Audience Manager]元件包括：

## 客戶資料摘要 (CDF) {#cdf}

[!UICONTROL CDF] 是每小時傳送給客戶的檔案。這些ID包含使用者ID，以及關聯的區段ID、特徵ID和其他資料。 如需詳細資訊，請參閱[客戶資料饋送概觀](../../features/cdf-files.md)。

## 資料收集伺服器(DCS){#dcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3]發行者會從[!UICONTROL Outbound Feed Converter]接收同步的ID資料。 當這些檔案準備就緒時，[!UICONTROL SFTP/S3 publishers]會將此資料發送到客戶端指定的目標。 這些檔案包含同步化的ID資料，且[!DNL Audience Manager]使用者ID(UUID)的一對多對應：

* 裝置ID/資料提供者ID(DPUUID)
* 限定的區段ID
* 特徵ID

[!DNL Audience Manager] 客戶無法存取直接控制的功能 [!UICONTROL SFPT/S3 publishers]。客戶在建立資料並傳送資料至目的地時，會間接使用此服務。 [!UICONTROL SFTP/S3]系統本質上是以計畫間隔運行的自動作業進程。

## IRIS {#iris}

在希臘神話中，[!UICONTROL Iris]是一個快速傳遞訊息的人物。 [!UICONTROL IRIS]系統是反映古代人物特徵的名稱。 在現代語言中，[!UICONTROL IRIS]是低延遲、高頻Cookie同步與資料傳輸服務。

[!UICONTROL IRIS] 與系統使用的資料類型相 [!UICONTROL SFTP/S3] 同。但是，[!UICONTROL IRIS]不同，因為它會即時傳送資料至目的地，而非以設定的間隔傳送。 這是個單獨的系統，因為[!UICONTROL SFTP/S3]發佈者無法傳送資料至HTTP目的地，而且它們不適用於即時資料傳輸。

沒有UI控制項可讓客戶直接與[!UICONTROL IRIS]搭配運作。 當客戶建立資料並傳送至目的地，以及其他需要快速資料傳輸的程式時，會間接與[!UICONTROL IRIS]合作。

[!UICONTROL IRIS]服務和功能的範例包括：

* 為Cookie和區段提供快速（30秒內）同步。 它可同步[!DNL Audience Manager] Cookie、合作夥伴Cookie或兩者。
* 即時資料傳輸。 [!UICONTROL IRIS] 負責傳送即時區段資格事件給合作夥伴或其他目的地。此資料是JSON格式，並透過HTTP `POST`請求傳送。

* 大量伺服器對伺服器資料傳輸：如果您與[!DNL Audience Manager]交換大量資料，則[!UICONTROL IRIS]是您的伺服器用於傳輸資料的系統。

* 可靠、規模化、容錯的基礎架構。 支援[!UICONTROL IRIS]的系統包括Amazon SQS、Amazon EC2和Cassandra。

**區段對應規則**

為了最佳化[!UICONTROL IRIS]和區段目標之間的流量，[!UICONTROL IRIS]會根據一組規則傳送區段至目標。

1. **新細分資格**:當裝置符合新區段的資格時，會 [!UICONTROL IRIS] 將與該裝置相關的所有區段傳送至所有對應至這些區段的目的地。

1. **新區段取消資格**:當裝置不再符合區段資格時，會將與該 [!UICONTROL IRIS] 裝置相關聯的所有區段資格和取消資格傳送至所有對應至這些區段的目標。

1. **目標映射更新**:當目標對應更新時，會 [!UICONTROL IRIS] 將與裝置相關聯的所有區段傳送至所有對應至這些區段的目標，此時Audience Manager會在下次看到裝置時顯示。

1. **裝置圖表更新**:當任何裝置ID從用於評估區段的裝置圖形中新增或移除時，會將與該裝置關聯的所有區段傳送至所有對應至這些區段的目標，此時Audience Manager會在下次看到裝置時顯示。 [!UICONTROL IRIS] 

>[!IMPORTANT]
>
>如果Audience Manager連續3天未偵測到上述任何更新，[!UICONTROL IRIS]會將與裝置相關的所有區段傳送至所有對應至這些區段的目的地，則下次Audience Manager看到裝置時。

**範例資料檔案**

下列範例包含來自[!UICONTROL IRIS]的即時區段資料。 請記住，這僅是範例資料。 每位客戶可能有不同的格式要求，因此內容可能會有所不同。

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

## 配置式快取伺服器(PCS){#pcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。
