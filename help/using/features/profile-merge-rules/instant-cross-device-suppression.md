---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能，為使用者提供跨裝置的一致體驗。 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

當這些裝置發生特定體驗時，[!UICONTROL Instant Cross-Device Suppression]能夠抑制連線到這些裝置的多個裝置上的使用者。 使用[!UICONTROL Instant Cross-Device Suppression]功能為使用者提供跨裝置的一致體驗。 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression]提供兩個主要使用案例：改善使用者體驗與媒體效率。

* **改善的使用者體驗**：已購買您產品或服務的使用者將不會看到與購買前相同的創意內容。 反之，您可以針對您知道他們尚未購買的產品或服務，顯示追加銷售或交叉銷售訊息。
* **媒體效率**：透過對所有[!DNL DSP]套用全域頻率上限，將您的行銷活動支出最佳化。頻率上限可以為屬於一個使用者的多個裝置即時操作。

即時取消細分的技術詳細資訊在[設定檔合併規則和裝置取消細分程式](merge-rule-unsegment.md)中有詳細說明。 請閱讀並實際實施上述使用案例。

## 轉換後不要鎖定目標 {#do-not-target-once}

請確定您已轉換的使用者（購買產品、取得訂閱等）不會看到與轉換前相同的訊息。 您可以使用[!UICONTROL AND NOT]邏輯取得此專案，如下所示。

1. 使用兩個特徵建立區段，並使用[!UICONTROL AND NOT]邏輯，如下圖所示。 您必須使用規則型特徵來定義轉換事件，以便即時觸發取消細分動作。 深入瞭解如何[建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)。
2. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀如何新增區段至[伺服器對伺服器目的地](../destinations/add-edit-segments.md)。

只要您的訪客未轉換，即符合該區段的資格。 當他們符合轉換特徵資格時，就會停止遵循區段規則，並立即從區段中移除。

![](assets/and_not_use_case.png)

## x次曝光後不要鎖定目標 {#do-not-target-after-x}

您可以設定造訪間隔和頻率控制，確保使用者不會大量使用相同的創意。 此情境中，請依照下列步驟概述，建立具有兩個特徵的區段。

1. 使用兩個特徵建立區段，並使用[!UICONTROL AND]邏輯，如下圖所示。 您必須使用規則型特徵來定義要即時觸發之取消區段的曝光事件。 深入瞭解如何[建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)。
   >[!NOTE]
   >
   >您可以使用[!UICONTROL Actionable Log Files]或[!UICONTROL Pixel Calls]，根據使用者曝光數建立特徵。 深入瞭解[可操作的記錄檔](../../integration/media-data-integration/actionable-log-files.md)和[畫素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。
2. 將頻率控制項套用至第二個特徵。 您也可以新增造訪間隔控制項。 深入瞭解[如何套用造訪間隔和頻率控制項](../segments/recency-and-frequency.md)。
3. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀如何新增區段至[伺服器對伺服器目的地](../destinations/add-edit-segments.md)。

在此案例中，一旦您的使用者累積超過三次曝光，就會從此區段中移除他們，且不會再看到此特定創意內容。

![](assets/impressions_use_case.png)

## 需要注意的重要方面 — 處理 {#processing-notes}

請記住，這些與處理相關的方面：

* 為了讓即時取消區段功能發揮作用，您必須將所需的區段對應至即時伺服器對伺服器目的地。
* 對於透過[裝置圖表](profile-link-use-case.md#recommendations)連線至裝置的裝置，我們會針對評估與取消細分強制執行四個裝置的限制。 此限制在[裝置圖表選項與裝置取消細分](merge-rule-unsegment.md#device-graph-options-unsegmentation)中說明&#x200B;。
* 對於透過裝置圖表連線的多個裝置，取消分段命令將包含在批次檔案中，每24小時傳送至目的地。
* 必須即時看見裝置(在[Edge](../../reference/system-components/components-edge.md)上)才能即時提示區段評估。 對於在符合特徵[!UICONTROL time-to-live (TTL)]時具有[!DNL TTL]的特徵，裝置將會在24小時內透過批次檔案自動取消分段&#x200B;。 深入瞭解如何[設定特徵過期時間間隔](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果您要即時使用[!UICONTROL DCS API]來內建規則型特徵，可以使用[!UICONTROL AND NOT]邏輯觸發取消分段。 深入瞭解[傳送資料至DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。&#x200B;

## 需要注意的重要方面 — 時間 {#timing-notes}

請記住，這些與時間相關的方面：

* 區段會儲存在[Edge](../../reference/system-components/components-edge.md)上，與裝置設定檔儲存在[!UICONTROL Edge]上的時間相同，也就是自上次即時互動以來的14天。 請參閱我們的[資料保留常見問題集](../../faq/faq-privacy.md#data-retention-faq)，深入瞭解資料保留。
* 取消細分作業大約需要24小時才能傳播至[!DNL DCS]個區域。 詳細瞭解我們的[!DNL DCS]地區[這裡](../../reference/system-components/components-data-collection.md)和[這裡](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
