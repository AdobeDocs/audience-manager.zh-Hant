---
description: 資料收集元件包括資料收集伺服器、DIL API、傳入伺服器對伺服器資料傳輸，以及記錄檔。
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: 資料收集元件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 3%

---

# 資料收集元件{#data-collection-components}

資料收集元件包括資料收集伺服器、DIL API、傳入伺服器對伺服器資料傳輸，以及記錄檔。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含下列資料收集元件：

* [資料收集伺服器(DCS)和設定檔快取伺服器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [資料整合程式庫 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [傳入伺服器對伺服器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [記錄檔](../../reference/system-components/components-data-collection.md#log-files)

## 資料收集伺服器(DCS)和設定檔快取伺服器(PCS) {#dcs-pcs}

DCS和PCS可共同作業，並分別提供與特徵實現、受眾細分和資料儲存相關的服務。

**[!UICONTROL Data Collection Servers (DCS)]函式**

在[!DNL Audience Manager]中，DCS：

* 從事件呼叫接收及評估特徵資料。 這包括即時分段所使用的資訊，以及伺服器對伺服器傳輸排程間隔傳入的資料。
* 根據使用者已實現的特徵以及您使用[區段產生器](../../features/segments/segment-builder.md)建立的資格規則來劃分使用者。
* 建立及管理裝置ID和已驗證的設定檔ID。 這包括資料提供者ID、使用者ID、宣告ID、整合代碼等識別碼。
* 檢查PC是否有使用者在即時事件呼叫前已實現的其他特徵。 這可讓DCS根據即時資料和歷史資料來判斷使用者的資格。
* 寫入記錄檔並傳送至分析系統以進行儲存和處理。

**[!DNL DCS]透過[!UICONTROL Global Server Load Balancing (GSLB)]**&#x200B;管理需求

[!DNL DCS]是地理上分散且負載平衡的系統。 這表示[!DNL Audience Manager]可以根據網站訪客的地理位置，將要求導向或導向區域資料中心。 此策略有助於改善回應時間，因為[!DNL DCS]回應會直接傳送到包含該訪客相關資訊的資料中心。 [!UICONTROL GSLB]可讓我們的系統更有效率，因為相關資料會快取至最接近使用者的伺服器。

>[!IMPORTANT]
>
>[!DNL DCS]只會偵測來自使用IPv4之裝置的網頁流量。

在事件呼叫中，地理位置是擷取自較大JSON資料內文傳回的索引鍵/值組。 這個機碼值組是`"dcs_region": region ID`引數。

![](assets/dcs-map.png)

身為客戶，您會透過我們的資料收集程式碼間接與[!DNL DCS]互動。 您也可以透過一組API直接使用[!DNL DCS]。 請參閱[資料收集伺服器(DCS) API方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS]是大型資料庫（基本上是大型伺服器端Cookie）。 它會儲存從伺服器對伺服器的傳輸和 [!DNL DCS] 中接收到的作用中使用者資料。[!UICONTROL PCS]資料包含裝置ID、已驗證的設定檔ID及其相關特徵。 當[!DNL DCS]收到即時呼叫時，它會檢查[!UICONTROL PCS]中是否有使用者可能屬於或符合資格的其他特徵。 而且，如果之後將特徵新增至區段，這些特徵ID會新增至[!UICONTROL PCS]，使用者就能自動符合該區段的資格，而無需造訪特定網站或應用程式。 [!UICONTROL PCS]可協助深化[!DNL Audience Manager]對您使用者的瞭解，因為它可以使用新的和歷史特徵資料即時比對及劃分使用者，或在幕後比對及劃分使用者。 相較於僅憑即時資格，此行為可讓您更完整且準確地掌握使用者的情況。

沒有可讓我們的客戶直接使用[!UICONTROL PCS]的UI控制項。 客戶對[!UICONTROL PCS]的存取是間接的，透過其作為資料存放區和資料傳輸的角色。 [!UICONTROL PCS]在Apache Cassandra上執行。

**正在從[!UICONTROL PCS]**&#x200B;中清除非作用中的ID

如前所述，[!UICONTROL PCS]會儲存作用中使用者的特徵ID。 作用中使用者是過去14天內[邊緣資料伺服器](../../reference/system-components/components-edge.md)從任何網域看到的任何使用者。 這些對[!UICONTROL PCS]的呼叫會將使用者保持在作用中狀態：

* [!DNL /event]個呼叫
* [!DNL /ibs]個呼叫（識別碼同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果[!UICONTROL PCS]有17天未使用，則會排清特徵。 不過，這些特徵不會遺失。 儲存在Hadoop中。 如果在其他時間再次看到使用者，則Hadoop會將其所有特徵推送回[!UICONTROL PCS]，通常在24小時內完成。

**其他[!UICONTROL DCS/PCS]個處理程式：隱私權選擇退出**

這些伺服器系統處理隱私權和使用者選擇退出的請求。 如果使用者已選擇退出資料收集，則不會收集記錄檔中的使用者Cookie資訊。 如需隱私權政策的詳細資訊，請參閱[Adobe隱私權中心](https://www.adobe.com/tw/privacy/experience-cloud.html)。

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL]是您放置在資料收集頁面上的程式碼。 請參閱[DIL API](../../dil/dil-overview.md)，以取得可用服務與方法的詳細資訊。

## 傳入伺服器對伺服器 {#inbound-outbound-server}

這些系統可接收由各種伺服器對伺服器整合所傳送的資料與我們使用者端整合。 如需詳細資訊，請參閱有關[傳送對象資料](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md)的檔案。

## 記錄檔 {#log-files}

[!UICONTROL PCS]會建立資料並將資料寫入記錄檔。 這些資料會傳送至其他資料庫系統以進行處理、報告和儲存。

>[!MORELIKETHIS]
>
>* [Adobe 隱私中心](https://www.adobe.com/tw/privacy.html)
