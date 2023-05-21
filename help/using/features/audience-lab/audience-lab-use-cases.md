---
description: 通過允許您使用基線段建立test組，「觀眾實驗室」啟用了多個使用案例。 您可以將test組分成多個相互排斥的test段，將這些段映射到不同的目標，然後確定哪些段在驅動轉換方面最有效。
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Audience Lab 使用案例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# Audience Lab 使用案例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允許您使用基線段建立test組，從而啟用多個使用案例。 您可以將test組分成多個相互排斥的test段，將這些段映射到不同的目標，然後確定哪些段在驅動轉換方面最有效。

## 在觀眾實驗室中比較模型 {#compare-models}

可以在中使用多種不同類型的模型和模型源 [!DNL Audience Manager]。 [!UICONTROL Audience Lab] 提供了比較客戶在活動模型中的轉換率的簡單方法。

<!-- audience-lab-compare-models.xml -->

在此使用情況下，您將比較不同的模型。 您可以使用通過內部資料倉庫建立的模型，然後將它們導入 [!DNL Audience Manager] 如 [掛接的特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或者你可以 [算法模型](../../features/algorithmic-models/understanding-models.md) 特徵 [!DNL Audience Manager]。

1. 建立兩個模型， [模型生成器](../../features/algorithmic-models/create-model.md)或通過外部平台。
1. 建立 [算法特徵](../../features/traits/create-algorithmic-traits.md) 或者把自己的模型作為附件特徵導入。
1. 建立互斥段，以便兩個模型中的用戶不會重疊：

   * 建立 *模型1段* 和 *型號2段*。
   * 使段規則 *模型1段* 模型1特質 [!DNL AND NOT] 模型2特徵，反之亦然 *型號2段*。

1. [建立兩個段test組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 在 [!UICONTROL Audience Lab]，一個 *模型1段* 作為基線，另一個 *型號2段* 值。

   * 對兩個test組保持變數相同：同樣的目的地，創造性，轉換性。
   * 確保test段的用戶數量相似（例如，160萬和180萬是正確的，160萬和1600萬不是正確的）。
   * 於各test分部test組保留控制分部。 這樣，您就可以留出每個段的一小部分，而不能在test中明確針對它們。

1. 檢查結果：

   * 的 [觀眾實驗室報告視圖](../../features/audience-lab/audience-lab-reporting-view.md) 將顯示每個模型所驅動的轉換次數。 對於基於轉換的市場活動，驅動最多轉換的test段將表示效能最佳的模型。
   * 由於您有控制段，因此您還可以評估模型對「標準目標」的作用。 您不僅僅測試一種模型與另一種模型，還測試「此模型是否比常規方法做得更好？」

## 測試目標中的創意 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用 [!UICONTROL Audience Lab] 為了衡量創意人員在不同目的地間駕駛的轉換次數。 此使用案例還允許您測量創意與自然發生的轉換的轉換。

1. [建立段Test組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選擇要將創作對象test為基線段的段。
1. 將基線段拆分為test段和控制段。
1. 將test段映射到要test的不同目標。
1. 控制段可以預扣而不映射到任何目標。 控制段不應由test建立者針對自然發生的轉換設定結果基線。
1. 指定test的開始日期和結束日期。
1. 設定目標中的段和創意。
1. 的 [觀眾實驗室報告視圖](../../features/audience-lab/audience-lab-reporting-view.md) 將顯示創意者在各目的地的轉換次數。
1. 因為您建立了一個控制段，所以您還可以評估創意對自然發生的轉換的影響。 你正在測試這個問題：「這種創意是否產生了比正常做法更高的轉換率？」
