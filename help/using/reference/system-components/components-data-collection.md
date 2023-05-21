---
description: 資料收集元件包括資料收集伺服器、DILAPI、入站伺服器到伺服器的資料傳輸和日誌檔案。
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: 資料收集元件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 6%

---

# 資料收集元件{#data-collection-components}

資料收集元件包括資料收集伺服器、DILAPI、入站伺服器到伺服器的資料傳輸和日誌檔案。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含以下資料收集元件：

* [資料收集伺服器(DCS)和配置檔案快取伺服器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [資料整合程式庫 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站伺服器到伺服器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日誌檔案](../../reference/system-components/components-data-collection.md#log-files)

## 資料收集伺服器(DCS)和配置檔案快取伺服器(PCS) {#dcs-pcs}

DCS和PCS協同工作，分別提供與特性實現、受眾細分和資料儲存相關的服務。

**[!UICONTROL Data Collection Servers (DCS)]函數**

在 [!DNL Audience Manager],DCS:

* 從事件調用接收和評估特性資料。 這包括用於即時分段的資訊以及按預定時間間隔通過伺服器到伺服器傳輸傳入的資料。
* 根據用戶已實現的特性和您使用建立的資格規則對用戶進行細分 [段生成器](../../features/segments/segment-builder.md)。
* 建立並管理設備ID和經過驗證的配置檔案ID。 這包括諸如資料提供程式ID、用戶ID、聲明的ID、整合代碼等標識符。
* 在即時事件調用之前，檢查PCS中用戶已經實現的附加特性。 這使DCS能夠根據即時資料和歷史資料來鑑定用戶。
* 寫入日誌檔案並將其發送到分析系統以進行儲存和處理。

**[!DNL DCS]通過[!UICONTROL Global Server Load Balancing (GSLB)]**

的 [!DNL DCS] 是一個地理上分佈的負載平衡系統。 這意味著 [!DNL Audience Manager] 可以根據站點訪問者的地理位置將請求定向到區域資料中心和從區域資料中心發出請求。 此策略有助於縮短響應時間，因為 [!DNL DCS] 響應將直接指向包含該訪問者資訊的資料中心。 [!UICONTROL GSLB] 使我們的系統高效，因為相關資料快取在離用戶最近的伺服器中。

>[!IMPORTANT]
>
>的 [!DNL DCS] 僅檢測來自使用IPv4的設備的Web通信。

在事件調用中，地理位置被捕獲在JSON資料的較大體中返回的鍵值對中。 此鍵值對是 `"dcs_region": region ID` 的下界。

![](assets/dcs-map.png)

作為客戶，您與 [!DNL DCS] 間接通過我們的資料收集代碼。 您還可以直接與 [!DNL DCS] 通過一組API。 請參閱 [資料採集伺服器(DCS)API方法與代碼](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。

**[!UICONTROL Profile Cache Servers (PCS)]**

的 [!UICONTROL PCS] 是一個大型資料庫（基本上是一個大型伺服器端cookie）。 它會儲存從伺服器對伺服器的傳輸和 [!DNL DCS] 中接收到的作用中使用者資料。[!UICONTROL PCS] 資料包含裝置 ID、已驗證的設定檔 ID 及其相關特徵。當 [!DNL DCS] 接到即時呼叫後，會檢查 [!UICONTROL PCS] 對於用戶可能屬於或符合的其他特徵。 如果在稍後的一段中加入一個特徵，那些特徵ID就會加入 [!UICONTROL PCS] 用戶無需訪問特定站點或應用程式即可自動獲得該段的資格。 的 [!UICONTROL PCS] 深化 [!DNL Audience Manager]瞭解您的用戶，因為它可以即時或在幕後將用戶與新的歷史特性資料進行匹配和細分。 與僅從即時資格中獲取資訊相比，此行為可為您提供更完整、更準確的用戶資訊。

沒有UI控制項可讓我們的客戶直接與 [!UICONTROL PCS]。 客戶訪問 [!UICONTROL PCS] 是間接的，通過它作為資料儲存和資料傳輸的角色。 的 [!UICONTROL PCS] 在阿帕奇·卡桑德拉上運行。

**從[!UICONTROL PCS]**

如前所述， [!UICONTROL PCS] 儲存活動用戶的特性ID。 活動用戶是指已被 [邊緣資料伺服器](../../reference/system-components/components-edge.md) 從任何域獲取。 這些呼叫 [!UICONTROL PCS] 使用戶處於活動狀態：

* [!DNL /event] 呼叫
* [!DNL /ibs] 調用（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

的 [!UICONTROL PCS] 如果某些特徵處於17天不活動狀態，則刷新它們。 然而，這些特質並未消失。 它們被儲存在Hadoop。 如果用戶在另一時間再次被看到，則Hadoop會將其所有特徵都推回 [!UICONTROL PCS]通常在24小時內。

**其他 [!UICONTROL DCS/PCS] 進程：隱私選擇退出**

這些伺服器系統處理隱私和用戶選擇退出請求。 如果用戶已選擇不收集資料，則不會在日誌檔案中收集用戶cookie資訊。 有關隱私策略的詳細資訊，請參閱 [Adobe隱私中心](https://www.adobe.com/tw/privacy/experience-cloud.html)。

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] 是您放在頁面上進行資料收集的代碼。 查看 [DILAPI](../../dil/dil-overview.md) 的子菜單。

## 入站伺服器到伺服器 {#inbound-outbound-server}

這些系統接收通過各種伺服器到伺服器的整合與我們的客戶端發送的資料。 請參閱 [發送受眾資料](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) 的子菜單。

## 日誌檔案 {#log-files}

的 [!UICONTROL PCS] 建立資料並將其寫入日誌檔案。 這些資料庫會發送到其他資料庫系統，以便進行處理、報告和儲存。

>[!MORELIKETHIS]
>
>* [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)

