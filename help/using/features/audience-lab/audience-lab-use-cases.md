---
description: Audience Lab可讓您使用基準區段來建立測試群組，以啓用數個使用案例。您可以將測試群組分為數個互斥測試區段，將這些區段對應至不同目的地，然後判斷哪些區段最有效地推動轉換。
seo-description: Audience Lab可讓您使用基準區段來建立測試群組，以啓用數個使用案例。您可以將測試群組分為數個互斥測試區段，將這些區段對應至不同目的地，然後判斷哪些區段最有效地推動轉換。
seo-title: 觀眾Lab使用案例
solution: Audience Manager
title: 觀眾Lab使用案例
topic: DIL API
uuid: 727bec8a-df9 a-40cc-b8 a7-e1980 d146 a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允許您使用基準區段建立測試群組，啓用數個使用案例。您可以將測試群組分為數個互斥測試區段，將這些區段對應至不同目的地，然後判斷哪些區段最有效地推動轉換。

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] 提供簡單的方式來比較客戶的轉化率。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您會比較不同的模型。You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. 建立互斥區段，讓兩個模型的使用者不會重疊：

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [建立兩個區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ， [!UICONTROL Audience Lab]其中一個包含 *模型區段* 作為基準，另一個用於 *作為基準的* 模型區段。

   * 請為兩個測試群組維持相同的變數：相同目的地、創意、轉化特徵。
   * 請確定測試區段的使用者人數類似(例如，1.6萬和800萬名使用者，而1000000和1000000則並非如此)。
   * 在每個測試區段測試群組中保留控制區段。如此，您就可以將每個區段的一小部分設定為一部分，而不會在測試中明確定位它們。

1. 檢查結果：

   * [「觀眾Lab」報表檢視](../../features/audience-lab/audience-lab-reporting-view.md) 將顯示每個模型驅動的轉換次數。對於基於轉換的促銷活動，驅動最多轉換的測試區段表示表現最佳的模型。
   * 因為您擁有控制區段，所以您也可以評估模型對「標準定位」的執行方式。您不只測試一個模型與另一個模型，而測試「此模型是否比一般實務更好？」

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. 此使用案例也可讓您測量創意轉換，而不是自然發生轉換。

1. [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選取您要將其測試為基準區段的區段。
1. 將基準區段分割為測試區段和控制區段。
1. 將測試區段對應至您想要測試的不同目的地。
1. 控制區段可保留且未對應至任何目的地。測試素材不應定位控制區段，以設定結果基準，以自然發生轉換。
1. 指定測試的開始日期和結束日期。
1. 設定目的地中的區段和創意。
1. [Audience Lab報表檢視將](../../features/audience-lab/audience-lab-reporting-view.md) 顯示創意在目的地中驅動的轉換次數。
1. 因為您建立了控制區段，所以您也可以評估創意對自然發生轉換的效果。您正在測試問題：「這種創意創造的轉換率高於一般的做法嗎？」
