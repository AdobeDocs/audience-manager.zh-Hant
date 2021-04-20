---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-title: 即時跨裝置隱藏功能
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 是當這些裝置上發生特定體驗時，可抑制連線至其上之多個裝置的使用者。使用[!UICONTROL Instant Cross-Device Suppression]功能，為您的使用者提供跨裝置的一致體驗。 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供兩個主要使用案例：改善使用體驗和媒體效率。

* **改善的使用者體驗**:已購買您產品或服務的使用者不會看到與購買前相同的創意。相反地，您可以針對您知道尚未購買的產品或服務顯示追加銷售或交叉銷售訊息。
* **媒體效率**:透過套用全域頻率上限，最佳化您的宣傳 [!DNL DSP]支出。對於屬於用戶的多個設備，可即時地對頻率帽進行動作。

在[描述檔合併規則與裝置取消分段程式](merge-rule-unsegment.md)中詳細說明即時取消分段的技術細節。 閱讀上述使用案例的實際實作。

## 轉換{#do-not-target-once}後不要定位

確保您的使用者已轉換（購買產品、取得訂閱等） 將看不到與轉換前相同的訊息。 您可以使用[!UICONTROL AND NOT]邏輯來取得此項，如下所示。

1. 使用兩個特徵建立區段，然後使用[!UICONTROL AND NOT]邏輯，如下圖所示。 您必須使用規則型特徵來定義要即時觸發的取消區段轉換事件。 閱讀更多有關如何建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)的資訊。[
2. 將區段對應至任意數目的即時伺服器對伺服器目的地。 閱讀有關如何將區段新增至[伺服器對伺服器目標](../destinations/add-edit-segments.md)的資訊。

只要訪客尚未轉換，即可符合區段資格。 只要符合轉換特徵的資格，就不再遵循區段規則，而會立即從區段中移除。

![](assets/and_not_use_case.png)

## Do Not Target After x印象{#do-not-target-after-x}

您可以設定時近和頻率控制項，確保不會讓相同的創意內容讓使用者滿載而歸。 在此案例中，請建立具有兩個特徵的區段，如下列步驟所述。

1. 使用兩個特徵建立區段，然後使用[!UICONTROL AND]邏輯，如下圖所示。 您必須使用規則型特徵來定義要即時觸發的取消區段印象事件。 閱讀更多有關如何建立規則型特徵](../traits/create-onboarded-rule-based-traits.md)的資訊。[
   >[!NOTE]
   >
   >您可以使用[!UICONTROL Actionable Log Files]或[!UICONTROL Pixel Calls]根據使用者印象建立特徵。 閱讀更多有關[可操作日誌檔案](../../integration/media-data-integration/actionable-log-files.md)和[像素調用](../../integration/media-data-integration/impression-data-pixels.md)的資訊。
2. 將頻率控制套用至第二個特徵。 如果您願意，也可以新增時近控制項。 閱讀更多有關如何套用時近和頻率控制項的資訊](../segments/recency-and-frequency.md)。[
3. 將區段對應至任意數目的即時伺服器對伺服器目的地。 閱讀有關如何將區段新增至[伺服器對伺服器目標](../destinations/add-edit-segments.md)的資訊。

在此案例中，一旦您的使用者累積了超過3個曝光，他們就會從此區隔中移除，而不會再看到此特定的創意素材。

![](assets/impressions_use_case.png)

## 注意的重要方面——處理{#processing-notes}

請記住與處理相關的這些方面：

* 要使即時取消分段功能發揮作用，您必須將所需分段對應至即時伺服器對伺服器目標。
* 對於透過[裝置圖表](profile-link-use-case.md#recommendations)連線至裝置的裝置，我們會針對評估與取消分段強制實行四裝置限制。 此限制在[裝置圖形選項和裝置取消分段](merge-rule-unsegment.md#device-graph-options-unsegmentation)中說明&#x200B;。
* unsegment命令將包含在批次檔案中，每24小時傳送至目的地，適用於由裝置圖形連接的多部裝置。
* 設備必須即時顯示（位於[Edge](../../reference/system-components/components-edge.md)上），以即時提示分段評估。 對於符合特徵[!DNL TTL]時具有[!UICONTROL time-to-live (TTL)]的特徵，裝置將會在24小時內自動透過批次檔案取消區隔&#x200B;。 閱讀有關如何[設定特徵有效期間](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)的更多資訊。
* 如果您使用[!UICONTROL DCS API]來即時使用板載規則型特徵，則可使用[!UICONTROL AND NOT]邏輯來觸發取消區段。 閱讀有關[傳送資料至DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)的更多資&#x200B;訊。

## 注意的重要方面——計時{#timing-notes}

請記住，這些與時機有關的方面：

* 區段會儲存在[Edge](../../reference/system-components/components-edge.md)中，與裝置描述檔儲存在[!UICONTROL Edge]中的相同時段，即自上次即時互動以來的14天。 閱讀[資料保留常見問答集](../../faq/faq-privacy.md#data-retention-faq)中有關資料保留的更多資訊。
* 未分段操作在[!DNL DCS]區域傳播大約需要24小時。 閱讀更多有關[!DNL DCS]地區[這裡](../..//reference/system-components/components-data-collection.md)和[這裡](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)的資訊。
