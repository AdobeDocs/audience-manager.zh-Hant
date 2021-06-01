---
description: 資料收集元件包括資料收集伺服器、DILAPI、傳入伺服器對伺服器資料傳輸，以及記錄檔。
seo-description: 資料收集元件包括資料收集伺服器、DILAPI、傳入伺服器對伺服器資料傳輸，以及記錄檔。
seo-title: 資料收集元件
solution: Audience Manager
title: 資料收集元件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: 系統元件
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---

# 資料收集元件{#data-collection-components}

資料收集元件包括資料收集伺服器、DILAPI、傳入伺服器對伺服器資料傳輸，以及記錄檔。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含下列資料收集元件：

* [資料收集伺服器(DCS)和設定檔快取伺服器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [資料整合程式庫 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [傳入伺服器對伺服器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [記錄檔](../../reference/system-components/components-data-collection.md#log-files)

## 資料收集伺服器(DCS)和設定檔快取伺服器(PCS){#dcs-pcs}

DCS和PCS可共同運作，分別提供與特徵實現、受眾細分和資料儲存相關的服務。

**[!UICONTROL Data Collection Servers (DCS)]函數**

在[!DNL Audience Manager]中，DCS:

* 從事件呼叫接收並評估特徵資料。 這包括用於即時分段的資訊，以及伺服器對伺服器傳輸以排程間隔傳入的資料。
* 根據使用者已實現的特徵，以及您透過[區段產生器](../../features/segments/segment-builder.md)建立的資格規則，將使用者分段。
* 建立並管理裝置ID與已驗證的設定檔ID。 這包括資料提供者ID、使用者ID、宣告ID、整合代碼等識別碼。
* 檢查PCS中是否有使用者在即時事件呼叫前已實現的其他特徵。 這可讓DCS根據即時資料和歷史資料來為使用者授與資格。
* 寫入記錄檔並將其傳送至分析系統，以便儲存及處理。

**[!DNL DCS]通過[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS]是地理分佈和負載平衡的系統。 這表示[!DNL Audience Manager]可根據網站訪客的地理位置，將請求導向至地區資料中心或從中傳送。 此策略有助於改善回應時間，因為[!DNL DCS]回應會直接傳至包含該訪客相關資訊的資料中心。 [!UICONTROL GSLB] 讓系統更有效率，因為相關資料是快取在最接近使用者的伺服器中。

>[!IMPORTANT]
>
>[!DNL DCS]僅檢測源自使用IPv4的設備的Web流量。

在事件呼叫中，地理位置是在較大的JSON資料內文中傳回的索引鍵值組中擷取。 此機碼值組是`"dcs_region": region ID`參數。

![](assets/dcs-map.png)

身為客戶，您需透過我們的資料收集程式碼，間接與[!DNL DCS]互動。 您也可以透過一組API直接與[!DNL DCS]搭配使用。 請參閱[資料收集伺服器(DCS)API方法與程式碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS]是大型資料庫（基本上是大型伺服器端Cookie）。 它會儲存從伺服器對伺服器的傳輸和 [!DNL DCS] 中接收到的作用中使用者資料。[!UICONTROL PCS] 資料包含裝置 ID、已驗證的設定檔 ID 及其相關特徵。當[!DNL DCS]收到即時呼叫時，會檢查[!UICONTROL PCS]中是否有使用者可能屬於或符合其資格的其他特徵。 此外，如果特徵稍後新增至區段，這些特徵ID會新增至[!UICONTROL PCS]，使用者可以自動符合該區段的資格，而不需造訪特定網站或應用程式。 [!UICONTROL PCS]有助於加深[!DNL Audience Manager]對使用者的了解，因為它可以即時或在背景使用新的和歷史特徵資料比對和劃分使用者。 相較於僅透過即時資格，此行為可讓您更完整、更精確地了解使用者。

沒有可讓客戶直接使用[!UICONTROL PCS]的UI控制項。 客戶對[!UICONTROL PCS]的存取是間接的，因為其作為資料儲存和資料傳輸的角色。 [!UICONTROL PCS]在Apache Cassandra上執行。

**從[!UICONTROL PCS]**

如前所述，[!UICONTROL PCS]會儲存作用中使用者的特徵ID。 作用中使用者是指過去14天內，從任何網域[邊緣資料伺服器](../../reference/system-components/components-edge.md)看到的任何使用者。 對[!UICONTROL PCS]的這些呼叫可讓使用者保持使用中狀態：

* [!DNL /event] 呼叫
* [!DNL /ibs] 呼叫（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果特徵在17天內處於非活動狀態，[!UICONTROL PCS]會刷新這些特徵。 但這些特徵並不會遺失。 它們儲存在Hadoop中。 如果使用者在另一次被看到，則Analytics會將其所有特徵推送回[!UICONTROL PCS]，通常是在24小時內。

**其他 [!UICONTROL DCS/PCS] 程式：隱私權選擇退出**

這些伺服器系統會處理隱私權和使用者選擇退出請求。 如果使用者已選擇退出資料收集，則不會在記錄檔中收集使用者Cookie資訊。 如需隱私權原則的詳細資訊，請參閱[Adobe隱私權中心](https://www.adobe.com/tw/privacy/experience-cloud.html)。

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] 是您放在頁面上以進行資料收集的程式碼。如需可用服務和方法的詳細資訊，請參閱[DILAPI](../../dil/dil-overview.md) 。

## 傳入伺服器對伺服器{#inbound-outbound-server}

這些系統會接收各種伺服器對伺服器整合所傳入的資料，並與我們的用戶端整合。 如需詳細資訊，請參閱[傳送對象資料](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md)的相關檔案。

## 日誌檔案{#log-files}

[!UICONTROL PCS]會建立資料並將其寫入日誌檔案。 這些資料會傳送至其他資料庫系統，以供處理、報告和儲存。

>[!MORELIKETHIS]
>
>* [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)

