---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-title: 即時跨裝置隱藏功能
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-7aa9-91b0-c2715857 d821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 可抑制在任何裝置上發生特定體驗時，與其連接的多個裝置使用者。Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供兩個主要使用案例：改善的使用者體驗和媒體效率。

* **改善的使用者體驗**：已購買您產品或服務的使用者在購買之前不會看見相同的創意素材。相反地，您可以針對您知道尚未購買的產品或服務，顯示追加銷售或交叉銷售訊息。
* **媒體效率**：跨所有 [!DNL DSP]網站套用全域頻率上限，最佳化宣傳支出。可對屬於使用者的多個裝置即時執行頻率片段。

[描述檔合併規則和裝置取消分段程序中的長度說明即時取消劃分的技術細節](../../features/profile-merge-rules/merge-rule-unsegment.md)。請參閱以實際實作上述使用案例的實作。

## Do Not Target Once Converted {#do-not-target-once}

確定已轉換的使用者(購買產品、取得訂閱等)將無法看見與轉換相同的訊息。You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. 您必須使用規則型特徵來定義要即時觸發之取消區段的轉換事件。Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. 將區段對應至任意數量的即時伺服器至伺服器目的地。Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

只要訪客未轉換，您的訪客就符合資格。當他們符合轉換特徵的資格後，即停止遵循區段規則並立即從區段中移除。

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

您可以設定最近的頻率和頻率控制，以確保不會讓使用者以相同的創意來膨脹。在此案例中，請建立具有兩個特性的區段，如下所示。

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. 您必須使用規則型特徵來定義要即時觸發之取消區段的曝光事件。Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. 將頻率控制套用至第二個特徵。您也可以加入最近的控制項。Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. 將區段對應至任意數量的即時伺服器至伺服器目的地。Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

在這種情況下，當您的使用者累積了超過三印象後，將會從此區段移除這些印象，而不會再看到這個特定創意。

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

請記住以下與處理相關的方面：

* 若要讓即時取消區段功能運作，您必須將所需區段對應至伺服器至伺服器目的地。
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* 取消區段命令將會包含在批次檔案中，每24小時就會傳送到目的地，適用於裝置圖表連接的多個裝置。
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.&#x200B; Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Important Aspects to Note - Timing {#timing-notes}

請記住下列與時間相關的方面：

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).