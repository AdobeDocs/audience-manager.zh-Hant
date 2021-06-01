---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-title: 即時跨裝置隱藏功能
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: 個人資料合併
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 可在任一裝置上發生特定體驗時，在多個裝置上隱藏連線至使用者的使用者。使用[!UICONTROL Instant Cross-Device Suppression]功能，為使用者提供跨裝置的一致體驗。 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供兩個主要使用案例：改善使用者體驗和媒體效率。

* **改善的使用者體驗**:已購買您產品或服務的使用者看不到與購買前相同的創意內容。相反地，您可以針對您知道尚未購買的產品或服務顯示追加銷售或交叉銷售訊息。
* **媒體效率**:對所有應用全域頻率上限，以最佳化行銷活動 [!DNL DSP]支出。對於屬於用戶的多個設備，可以即時地對頻率蓋進行操作。

即時取消細分的技術詳細資訊在[設定檔合併規則和裝置取消細分程式](merge-rule-unsegment.md)中有詳細說明。 閱讀上述使用案例的實際實施。

## 轉換後請勿定位{#do-not-target-once}

向已轉換（購買產品、取得訂閱等）的使用者保證 不會看到與轉換前相同的訊息。 您可以使用[!UICONTROL AND NOT]邏輯來取得，如下所示。

1. 使用兩個特徵建立區段，然後使用[!UICONTROL AND NOT]邏輯，如下圖所示。 您必須使用規則型特徵來定義要即時觸發取消細分的轉換事件。 深入了解如何[建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)。
2. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀有關如何將區段新增至[伺服器對伺服器目的地](../destinations/add-edit-segments.md)的資訊。

只要您的訪客尚未轉換，就符合區段的資格。 只要符合轉換特徵的資格，他們就不再遵循區段規則，而會立即從區段中移除。

![](assets/and_not_use_case.png)

## 在X曝光次數{#do-not-target-after-x}後不定位

您可以設定時近和頻率控制，確保不會讓相同的創意內容淹沒使用者。 在此案例中，請建立具有兩個特徵的區段，如下列步驟所述。

1. 使用兩個特徵建立區段，然後使用[!UICONTROL AND]邏輯，如下圖所示。 您必須使用規則型特徵來定義即時觸發取消細分的曝光事件。 深入了解如何[建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)。
   >[!NOTE]
   >
   >您可以使用[!UICONTROL Actionable Log Files]或[!UICONTROL Pixel Calls]根據使用者曝光數建立特徵。 深入了解[可操作的記錄檔](../../integration/media-data-integration/actionable-log-files.md)和[像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。
2. 將頻率控制套用至第二個特徵。 您也可以新增造訪間隔控制項。 深入閱讀[如何套用造訪間隔和頻率控制項](../segments/recency-and-frequency.md)。
3. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀有關如何將區段新增至[伺服器對伺服器目的地](../destinations/add-edit-segments.md)的資訊。

在此案例中，當您的使用者累積了超過三次曝光數後，就會從此區段中移除這些曝光數，不會再看到此特定創意內容。

![](assets/impressions_use_case.png)

## 注意事項的重要方面 — 處理{#processing-notes}

請記住以下與處理相關的方面：

* 為了讓即時取消細分功能發揮作用，您必須將所需的區段對應至即時伺服器對伺服器目的地。
* 對於透過[裝置圖表](profile-link-use-case.md#recommendations)連線至裝置的裝置，我們強制對評估和取消細分實行四裝置限制。 [裝置圖表選項和裝置取消細分](merge-rule-unsegment.md#device-graph-options-unsegmentation)中會說明此限&#x200B;制。
* 取消細分命令將包含在批次檔案中，對於由裝置圖表連線的多部裝置，此檔案每24小時傳送至目的地。
* 必須即時看到設備（位於[Edge](../../reference/system-components/components-edge.md)上），才能即時提示進行段評估。 若特徵[!DNL TTL]符合時具有[!UICONTROL time-to-live (TTL)]，裝置會在24小時內透過批次檔案自動取消分&#x200B;段。 深入了解如何[設定特徵過期時間間隔](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果您使用[!UICONTROL DCS API]來即時使用板載規則型特徵，則可使用[!UICONTROL AND NOT]邏輯來觸發取消細分。 深入了解[傳送資料至DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。&#x200B;

## 注意事項的重要方面 — 計時{#timing-notes}

請記住與時間相關的以下方面：

* 在[Edge](../../reference/system-components/components-edge.md)上儲存一個區段，與在[!UICONTROL Edge]上儲存一個設備配置檔案的相同時段，即距上次即時交互的14天。 請前往[資料保留常見問題集](../../faq/faq-privacy.md#data-retention-faq)，深入了解資料保留。
* 取消細分操作需要大約24小時才能跨[!DNL DCS]區域傳播。 請詳閱[!DNL DCS]地區[此處](../..//reference/system-components/components-data-collection.md)和[此處](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)的相關資訊。
