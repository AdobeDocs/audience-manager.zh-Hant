---
description: 資料收集元件包括資料收集伺服器、DIL API、傳入伺服器到伺服器的資料傳輸和記錄檔。
seo-description: 資料收集元件包括資料收集伺服器、DIL API、傳入伺服器到伺服器的資料傳輸和記錄檔。
seo-title: 資料收集元件
solution: Audience Manager
title: 資料收集元件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 6%

---


# 資料收集元件{#data-collection-components}

資料收集元件包括資料收集伺服器、DIL API、傳入伺服器到伺服器的資料傳輸和記錄檔。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含下列資料收集元件：

* [資料收集伺服器(DCS)和描述檔快取伺服器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [資料整合程式庫 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站伺服器到伺服器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日誌檔案](../../reference/system-components/components-data-collection.md#log-files)

## 資料收集伺服器(DCS)和描述檔快取伺服器(PCS) {#dcs-pcs}

DCS和PCS可搭配運作，並分別提供與特徵實現、受眾細分和資料儲存相關的服務。

**[!UICONTROL Data Collection Servers (DCS)]函數&#x200B;**

在 [!DNL Audience Manager]DCS中：

* 從事件呼叫接收並評估特徵資料。 這包括用於即時分段的資訊，以及伺服器間傳輸以預定間隔傳入的資料。
* 依據使用者已實現的特性，以及您使用「區段產生器」所建立的資格規則來區 [段使用者](../../features/segments/segment-builder.md)。
* 建立並管理裝置ID和已驗證的設定檔ID。 這包括諸如資料提供者ID、使用者ID、宣告的ID、整合碼等識別碼。
* 檢查PCS中是否有使用者在即時事件呼叫前已實現的其他特性。 這可讓DCS根據即時資料和歷史資料來篩選使用者。
* 寫入記錄檔並將其傳送至分析系統，以進行儲存和處理。

**[!DNL DCS]透過[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. 這表示 [!DNL Audience Manager] 可根據網站訪客的地理位置，將請求導向至地區資料中心或從區域資料中心傳送。 此策略有助於縮短回應時間，因 [!DNL DCS] 為回應會直接傳送到包含該訪客相關資訊的資料中心。 [!UICONTROL GSLB] 讓我們的系統更有效率，因為相關資料會快取在離使用者最近的伺服器上。

>[!IMPORTANT]
>
>只 [!DNL DCS] 會偵測來自使用IPv4之裝置的網路流量。

在事件呼叫中，地理位置會擷取到較大JSON資料內文傳回的索引鍵值對中。 此鍵值對是參 `"dcs_region": region ID` 數。

![](assets/dcs-map.png)

身為客戶，您可透過我們的資料收 [!DNL DCS] 集代碼間接與客戶互動。 您也可以透過一組API [!DNL DCS] 直接使用。 See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

它 [!UICONTROL PCS] 是大型資料庫（基本上是大型伺服器端Cookie）。 它會儲存從伺服器對伺服器的傳輸和 [!DNL DCS] 中接收到的作用中使用者資料。[!UICONTROL PCS] 資料包含裝置 ID、已驗證的設定檔 ID 及其相關特徵。當收 [!DNL DCS] 到即時呼叫時，會檢查使用者 [!UICONTROL PCS] 是否屬於或符合其他特徵。 而且，如果某個特徵稍後新增至區段，這些特徵ID會新增至區段，而使用者可以自動符合該區段的資格，而不需造訪特定網站或應用程式。 [!UICONTROL PCS] 它 [!UICONTROL PCS] 有助於深 [!DNL Audience Manager]入瞭解使用者，因為它可即時或在幕後使用新的歷史特徵資料來比對和劃分使用者。 與僅從即時資格證明相比，此行為可讓您更完整、更準確地瞭解使用者。

沒有UI控制項可讓客戶直接使用 [!UICONTROL PCS]。 客戶是間接存 [!UICONTROL PCS] 取的，透過其資料儲存與資料傳輸的角色。 運行 [!UICONTROL PCS] 於Apache Cassandra上。

**從[!UICONTROL PCS]**

如前所述，儲存作 [!UICONTROL PCS] 用中使用者的特徵ID。 作用中使用者是指過去14天內，任何網域的 [邊緣資料伺服器](../../reference/system-components/components-edge.md) ，都已看到的任何使用者。 這些呼叫可 [!UICONTROL PCS] 讓使用者保持作用中狀態：

* [!DNL /event] 呼叫
* [!DNL /ibs] 呼叫（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果 [!UICONTROL PCS] 特徵在17天內處於非活動狀態，則會刷新這些特徵。 但是，這些特徵並沒有消失。 它們儲存在Hadoop中。 如果使用者在另一時間再次出現，則Hadoop會將其所有特徵推回 [!UICONTROL PCS]，通常在24小時內。

**其他[!UICONTROL DCS/PCS]程式： 隱私權選擇退出**

這些伺服器系統可處理隱私權和使用者選擇退出要求。 如果使用者已選擇退出資料收集，則不會在記錄檔中收集使用者Cookie資訊。 如需我們隱私權政策的詳細資訊，請參 [閱Adobe隱私權中心](https://www.adobe.com/tw/privacy/experience-cloud.html)。

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] 是您放在頁面上進行資料收集的程式碼。 如需可用 [服務與方法的詳細資訊](../../dil/dil-overview.md) ，請參閱DIL API。

## 入站伺服器到伺服器 {#inbound-outbound-server}

這些系統會接收與客戶端不同伺服器對伺服器整合所傳送的資料。 如需詳細資訊，請參 [閱有關傳送觀眾資料](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) 的檔案。

## 日誌檔案 {#log-files}

建立 [!UICONTROL PCS] 資料並將資料寫入日誌檔案。 這些會傳送至其他資料庫系統，以供處理、報告和儲存。

>[!MORELIKETHIS]
>
>* [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)

