---
description: 資料收集元件包括資料收集伺服器、DIL API、傳入的伺服器資料傳輸和記錄檔。
seo-description: 資料收集元件包括資料收集伺服器、DIL API、傳入的伺服器資料傳輸和記錄檔。
seo-title: 資料收集元件
solution: Audience Manager
title: 資料收集元件
uuid: 51bb1719-5ff2-4bc7-9eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

資料收集元件包括資料收集伺服器、DIL API、傳入的伺服器資料傳輸和記錄檔。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含下列資料收集元件：

* [資料收集伺服器(DCS)和描述檔快取伺服器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [資料整合程式庫 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [傳入伺服器至伺服器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [記錄檔](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

DCS和PCS合作並個別提供特徵實現、受眾細分和資料儲存等服務。

**[!UICONTROL Data Collection Servers (DCS)]函數**

In [!DNL Audience Manager], the DCS:

* 接收並評估事件呼叫中的特徵資料。這包括用於即時分段和依伺服器對伺服器傳輸在排程間隔傳入的資料的資訊。
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* 建立並管理裝置ID和已驗證的描述檔ID。這包括識別碼，例如資料提供者ID、使用者ID、宣告的ID、整合代碼等。
* 針對使用者在即時事件呼叫之前已實現的其他特性檢查PCS。這可讓DCS根據即時資料和歷史資料來符合使用者資格。
* 寫入記錄檔，並將這些檔案傳送至分析系統以進行儲存和處理。

**[!UICONTROL DCS]透過管理需求[!UICONTROL Global Server Load Balancing (GSLB)]**

[!UICONTROL DCS] 這是分布各地且負載平衡的系統。This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] 讓我們的系統更有效率，因為相關資料會快取在與使用者最近的伺服器中。

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

在事件呼叫中，地理位置是擷取在大量JSON資料內文中傳回的索引鍵值配對中。This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] 資料包含裝置ID、已驗證的描述檔ID及其相關特徵。[!UICONTROL DCS] 收到即時呼叫時，會檢查使用者 [!UICONTROL PCS] 屬於或符合資格的其他特性。And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]&#39;s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. 這項行為可為您提供比單獨使用即時條件更完整精確的使用者圖片。

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**清除來自[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] 呼叫
* [!DNL /ibs] 呼叫(ID同步)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

[!UICONTROL PCS] 如果他們處於非活動狀態17天，則會發生對開本特徵。但這些特性並未遺失。它們儲存在Hadoop中。If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**其他[!UICONTROL DCS/PCS]程序：隱私權選擇退出**

這些伺服器系統可處理隱私權和使用者選擇退出要求。如果使用者已選擇退出資料收集，則不會在記錄檔中收集使用者Cookie資訊。For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## 資料整合程式庫 (DIL) {#dil}

[!UICONTROL DIL] 是您放置在頁面上的程式碼，用於收集資料。See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

這些系統可接收透過不同伺服器與伺服器整合所傳送的資料。See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. 這些系統會傳送至其他資料庫系統，以進行處理、報告和儲存。

>[!MORE_贊_ this]
>
>* [Adobe 隱私中心](https://www.adobe.com/privacy.html)

