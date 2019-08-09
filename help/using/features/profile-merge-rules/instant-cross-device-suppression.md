---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-title: 即時跨裝置隱藏功能
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-7aa9-91b0-c2715857 d821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 可抑制在任何裝置上發生特定體驗時，與其連接的多個裝置使用者。Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供兩個主要使用案例：改善的使用者體驗和媒體效率。

* **改善的使用者體驗**：已購買您產品或服務的使用者在購買之前不會看見相同的創意素材。相反地，您可以針對您知道尚未購買的產品或服務，顯示追加銷售或交叉銷售訊息。
* **媒體效率**：跨所有 [!DNL DSP]網站套用全域頻率上限，最佳化宣傳支出。可對屬於使用者的多個裝置即時執行頻率片段。

[描述檔合併規則和裝置取消分段程序中的長度說明即時取消劃分的技術細節](../../features/profile-merge-rules/merge-rule-unsegment.md)。請參閱以實際實作上述使用案例的實作。

## 轉換後不要定位 {#do-not-target-once}

確定已轉換的使用者(購買產品、取得訂閱等)將無法看見與轉換相同的訊息。您可以使用 [!UICONTROL AND NOT] 邏輯取得此項目，如下所示。

1. 使用兩個特性建立區段，並使用 [!UICONTROL AND NOT] 邏輯，如下圖所示。您必須使用規則型特徵來定義要即時觸發之取消區段的轉換事件。進一步瞭解 [如何建立規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)。
1. 將區段對應至任意數量的即時伺服器至伺服器目的地。瞭解如何新增區段至 [伺服器至伺服器目的地](../../features/destinations/add-edit-segments.md)。

只要訪客未轉換，您的訪客就符合資格。當他們符合轉換特徵的資格後，即停止遵循區段規則並立即從區段中移除。

![](assets/and_not_use_case.png)

## 在x曝光後不要定位 {#do-not-target-after-x}

您可以設定最近的頻率和頻率控制，以確保不會讓使用者以相同的創意來膨脹。在此案例中，請建立具有兩個特性的區段，如下所示。

1. 使用兩個特性建立區段，並使用 [!UICONTROL AND] 邏輯，如下圖所示。您必須使用規則型特徵來定義要即時觸發之取消區段的曝光事件。進一步瞭解 [如何建立規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)。
   >[!NOTE]
   >
   >您可以根據使用者印象來使用 [!UICONTROL Actionable Log Files] 或 [!UICONTROL Pixel Calls] 建立特徵。閱讀更多有關 [可ActionLog檔案](../../integration/media-data-integration/actionable-log-files.md) 和 [像素呼叫](../../integration/media-data-integration/impression-data-pixels.md)的資訊。
1. 將頻率控制套用至第二個特徵。您也可以加入最近的控制項。詳細瞭解 [如何套用最近一次和頻率控制](../../features/segments/recency-and-frequency.md)。
1. 將區段對應至任意數量的即時伺服器至伺服器目的地。瞭解如何新增區段至 [伺服器至伺服器目的地](../../features/destinations/add-edit-segments.md)。

在這種情況下，當您的使用者累積了超過三印象後，將會從此區段移除這些印象，而不會再看到這個特定創意。

![](assets/impressions_use_case.png)

## 注意事項-處理程序 {#processing-notes}

請記住以下與處理相關的方面：

* 若要讓即時取消區段功能運作，您必須將所需區段對應至伺服器至伺服器目的地。
* 對於 [裝置圖形](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)連接裝置的裝置，我們強制對評估和取消分段強制執行四裝置限制。這項限制會在 [「裝置圖表選項」和「裝置取消分段](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)」中說明。
* 取消區段命令將會包含在批次檔案中，每24小時就會傳送到目的地，適用於裝置圖表連接的多個裝置。
* 裝置必須即時檢視( [Edge](../../reference/system-components/components-edge.md))，才能進行區段評估。對於具有 [!UICONTROL time-to-live (TTL)] 值的特徵，即使符合特徵 [!DNL TTL] ，裝置 *也不* 會自動在下次看到裝置時進行分段。詳細瞭解 [如何設定特徵過期間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果您即時 [!UICONTROL DCS API] 使用即時規則型特徵，可以使用 [!UICONTROL AND NOT] 邏輯來觸發取消區段。詳細瞭解 [如何將資料傳送至DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## 注意事項-時間表 {#timing-notes}

請記住下列與時間相關的方面：

* 區段將會儲存 [在與](../../reference/system-components/components-edge.md) 裝置描述檔儲存在相同時段的Edge， [!UICONTROL Edge]即上次即時互動後14天。閱讀 [我們的資料保留常見問題，進一步瞭解資料保留](../../faq/faq-privacy.md#data-retention-faq)。
* 解除區段作業大約需要24小時，才能跨 [!UICONTROL DCS] 地區傳播。請在這裡 [!UICONTROL DCS][](../../reference/system-components/components-data-collection.md) 和 [這裡閱讀更多有關本公司](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)地區的資訊。