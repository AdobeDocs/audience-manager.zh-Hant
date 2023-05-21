---
description: 即時跨裝置隱藏功能可以在任一裝置出現特殊狀況時，在多個裝置上隱藏連接到這些裝置的使用者。使用即時跨裝置隱藏功能可以為使用者提供跨裝置的一致體驗。透過 Audience Manager 的即時不分區功能便能提供一致的體驗。
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: 即時跨裝置隱藏功能
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 9%

---

# 即時跨裝置隱藏功能 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 能夠在這些設備中的任何設備上出現特定體驗時，抑制連接到它們的多個設備上的用戶。 使用 [!UICONTROL Instant Cross-Device Suppression] 能夠跨設備向用戶提供一致的體驗。 透過 Audience Manager 的即時不分區功能便能提供一致的體驗。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供了兩個關鍵使用案例：提高了用戶體驗和媒體效率。

* **改善的用戶體驗**:已購買您的產品或服務的用戶將看不到與購買前相同的創意。 相反，您可以為您知道尚未購買的產品或服務顯示追加銷售或交叉銷售消息。
* **媒體效率**:通過應用全球頻率上限來優化您的促銷活動支出 [!DNL DSP]s該頻率帽可以即時地對屬於用戶的多個設備進行操作。

對即時非分割的技術細節進行了長度描述。 [配置檔案合併規則和設備非分割過程](merge-rule-unsegment.md)。 閱讀上述使用案例的實際實施。

## 轉換後不目標 {#do-not-target-once}

確保已轉換（購買產品、購買訂閱等）的用戶 將看不到與轉換前相同的消息。 可以使用 [!UICONTROL AND NOT] 邏輯，如下所示。

1. 使用兩個特徵建立段，並使用 [!UICONTROL AND NOT] 邏輯，如下圖所示。 必須使用基於規則的特性來定義要即時觸發的取消段的轉換事件。 閱讀有關如何 [建立基於規則的特徵](../traits/create-onboarded-rule-based-traits.md)。
2. 將段映射到任意數量的即時伺服器到伺服器目標。 閱讀有關如何將段添加到 [伺服器到伺服器目標](../destinations/add-edit-segments.md)。

您的訪問者只要尚未轉換，就有資格進入該段。 一旦它們符合轉換特性，就不再遵循分段規則，並立即從分段中移除。

![](assets/and_not_use_case.png)

## X印象後不要瞄準 {#do-not-target-after-x}

通過設定頻率和頻率控制，您可以確保不會向用戶注入相同的創意。 在此方案中，建立具有以下步驟中概述的兩個特徵的段。

1. 使用兩個特徵建立段，並使用 [!UICONTROL AND] 邏輯，如下圖所示。 必須使用基於規則的特性來定義要即時觸發的取消段的印象事件。 閱讀有關如何 [建立基於規則的特徵](../traits/create-onboarded-rule-based-traits.md)。
   >[!NOTE]
   >
   >您可以使用 [!UICONTROL Actionable Log Files] 或 [!UICONTROL Pixel Calls] 根據用戶印象建立特徵。 閱讀有關 [可操作的日誌檔案](../../integration/media-data-integration/actionable-log-files.md) 和 [像素調用](../../integration/media-data-integration/impression-data-pixels.md)。
2. 將頻率控制應用於第二個特性。 如果需要，也可以添加頻率控制項。 閱讀有關 [如何應用頻率和頻率控制](../segments/recency-and-frequency.md)。
3. 將段映射到任意數量的即時伺服器到伺服器目標。 閱讀有關如何將段添加到 [伺服器到伺服器目標](../destinations/add-edit-segments.md)。

在此方案中，一旦您的用戶累積了三種以上的印象，他們將從此段中刪除，並且不會再看到此特定的創意。

![](assets/impressions_use_case.png)

## 要注意的重要方面 — 處理 {#processing-notes}

請記住與處理相關的以下方面：

* 要使即時取消段功能正常工作，必須將所需段映射到即時伺服器到伺服器目標。
* 用於通過 [設備圖](profile-link-use-case.md#recommendations)對於評價和不分割，我們實施四設備限制。 此限制在 [設備圖形選項和設備未分割](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* unsegment命令將包含在批處理檔案中，該批處理檔案每24小時發送一次，用於通過設備圖形連接的多個設備。
* 設備必須即時(在 [邊緣](../../reference/system-components/components-edge.md) 即時提示分段評估。 對於那些有 [!UICONTROL time-to-live (TTL)]  當這個特徵 [!DNL TTL] 在24小時內，設備將通過批處理檔案自動被分割&#x200B;。 閱讀有關如何 [設定特性到期間隔](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果使用 [!UICONTROL DCS API] 對基於規則的線上特徵進行即時處理，可以使用 [!UICONTROL AND NOT] 邏輯。 閱讀有關 [向DCS API發送資料](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## 要注意的重要方面 — 時間安排 {#timing-notes}

請記住與時間安排有關的以下方面：

* 段將儲存在 [邊緣](../../reference/system-components/components-edge.md) 與設備配置檔案儲存在 [!UICONTROL Edge]即上次即時交互後14天。 閱讀有關我們 [資料保留常見問題](../../faq/faq-privacy.md#data-retention-faq)。
* 取消分段操作要傳播到 [!DNL DCS] 區域。 閱讀有關我們 [!DNL DCS] 區域 [這裡](../../reference/system-components/components-data-collection.md) 和 [這裡](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
