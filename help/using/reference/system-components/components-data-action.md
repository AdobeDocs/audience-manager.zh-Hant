---
description: 資料操作元件包括客戶資料源、資料收集伺服器、SFTP/S3/HTTP發佈器、IRIS和配置式快取伺服器。
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: 資料動作元件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# 資料動作元件{#data-action-components}

資料操作元件包括客戶資料源、資料收集伺服器、SFTP/S3/HTTP發佈器、IRIS和配置式快取伺服器。

<!-- 

c_compact.xml

 -->

操作元件是允許資料進出的系統和流程 [!DNL Audience Manager] （因為沒有更好的辭彙）用它做事。 這些 [!DNL Audience Manager] 元件包括：

## 客戶資料摘要 (CDF) {#cdf}

[!UICONTROL CDF] 是每小時向客戶發送的檔案。 這些包含用戶ID以及關聯的段ID、特徵ID和其他資料。 有關詳細資訊，請參見 [客戶資料饋送概述](../../features/cdf-files.md)。

## 資料收集伺服器(DCS) {#dcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

的 [!UICONTROL SFTP/S3] 發佈者從 [!UICONTROL Outbound Feed Converter]。 當這些檔案準備就緒時， [!UICONTROL SFTP/S3 publishers] 將此資料發送到客戶端指定的目標。 這些檔案包含具有一對多映射的同步ID資料 [!DNL Audience Manager] 用戶ID(UUID):

* 設備ID/資料提供程式ID(DPUUID)
* 限定段ID
* 特性ID

[!DNL Audience Manager] 客戶無權訪問直接控制 [!UICONTROL SFPT/S3 publishers]。 客戶在建立資料並將資料發送到目標時間接使用此服務。 的 [!UICONTROL SFTP/S3] 系統本質上是以預定時間間隔運行的自動作業進程。

## 虹膜 {#iris}

在希臘神話中， [!UICONTROL Iris] 是一個快速傳遞資訊的人物。 的 [!UICONTROL IRIS] 這個系統是反映這個古代人物特徵的同名稱。 就現代而言， [!UICONTROL IRIS] 是一種低延遲、高頻cookie同步和資料傳輸服務。

[!UICONTROL IRIS] 與 [!UICONTROL SFTP/S3] 系統。 但是， [!UICONTROL IRIS] 不同，因為它以即時方式而不是以設定的時間間隔向目的地發送資料。 這是一個單獨的系統，因為 [!UICONTROL SFTP/S3] 發佈者無法將資料發送到HTTP目標，並且它們不是為即時資料傳輸而設計的。

沒有UI控制項可讓客戶直接使用 [!UICONTROL IRIS]。 客戶與 [!UICONTROL IRIS] 在建立資料並將資料發送到目標以及需要快速資料傳輸的其他進程時間接執行。

示例 [!UICONTROL IRIS] 服務和功能包括：

* 為cookie和段提供快速（30秒內）同步。 它可以同步 [!DNL Audience Manager] 餅乾，夥伴餅乾，或兩者兼備。
* 即時資料傳輸。 [!UICONTROL IRIS] 負責將即時段資格事件發送到合作夥伴或其他目標。 此資料是JSON格式的，並通過HTTP發送 `POST` 請求。

* 批量伺服器到伺服器的資料傳輸：如果您與 [!DNL Audience Manager]。 [!UICONTROL IRIS] 是伺服器用於傳輸資料的系統。

* 可靠的基礎架構，可以規模化運行，並且具有容錯能力。 可供電的系統 [!UICONTROL IRIS] 包括AmazonSQS、AmazonEC2和卡桑德拉。

**段映射規則**

優化之間的通信 [!UICONTROL IRIS] 和分段目標， [!UICONTROL IRIS] 根據一組規則將段發送到目標。

1. **新段資格**:當設備符合新段的條件時， [!UICONTROL IRIS] 將與該設備關聯的所有段發送到映射到這些段的所有目標。

1. **新分部取消資格**:當設備不再符合段的條件時， [!UICONTROL IRIS] 將與該設備關聯的所有段資格和取消資格發送到映射到這些段的所有目標。

1. **目標映射更新**:更新目標映射時， [!UICONTROL IRIS] 將與設備關聯的所有段發送到映射到這些段的所有目標，以便下次Audience Manager看到設備時。

1. **設備圖形更新**:當從用於計算段的設備圖形中添加或刪除任何設備ID時， [!UICONTROL IRIS] 將與該設備關聯的所有段發送到映射到這些段的所有目標，以便下次Audience Manager看到該設備時。

>[!IMPORTANT]
>
>如果Audience Manager連續3天未檢測到以上任何更新， [!UICONTROL IRIS] 將與設備關聯的所有段發送到映射到這些段的所有目標，以便下次Audience Manager看到設備時。

**示例資料檔案**

以下示例包含來自 [!UICONTROL IRIS]。 請記住，這只是示例資料。 每個客戶可能有不同的格式要求，因此內容可能會有所不同。

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

## 配置檔案快取伺服器(PCS) {#pcs}

請參閱[資料收集元件](../../reference/system-components/components-data-collection.md)。
