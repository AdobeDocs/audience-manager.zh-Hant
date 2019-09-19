---
description: Audience lab可讓您使用基準區段來建立測試群組，借以啟用數個使用案例。 您可以將測試群組分割為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段對於驅動轉換最有效。
seo-description: Audience lab可讓您使用基準區段來建立測試群組，借以啟用數個使用案例。 您可以將測試群組分割為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段對於驅動轉換最有效。
seo-title: Audience lab使用案例
solution: Audience Manager
title: Audience lab使用案例
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience lab使用案例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允許您使用基線區段來建立測試群組，以啟用數個使用案例。 您可以將測試群組分割為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段對於驅動轉換最有效。

## Audience lab中的模型比較 {#compare-models}

您可以在中使用幾種不同的模型類型和來源 [!DNL Audience Manager]。 [!UICONTROL Audience Lab] 提供比較客戶在各個作用中模型轉換率的簡單方式。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您會比較不同的模型。 您可以使用透過內部資料倉庫建立的模型，並將其匯入為「已登入特徵」( [!DNL Audience Manager][Onhocted Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) )，或使用 [中的「演算模型](../../features/algorithmic-models/understanding-models.md) 」功能 [!DNL Audience Manager]。

1. 在 [Model Builder](../../features/algorithmic-models/create-model.md)，或透過外部平台建立兩個模型。
1. 從演 [算法模型建立演算法特徵](../../features/traits/create-algorithmic-traits.md) ，或將您自己的模型匯入為已登入特徵。
1. 建立互斥的區段，讓兩個模型中的使用者不會重疊：

   * 建立 *模型1段* 和 *模型2段*。
   * 讓模型1區段的區 *段規則為模型* 1特徵 [!DNL AND NOT] 模型2特徵，而模型2區段的區段規則 *亦然*。

1. [在中建立兩個段測試組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，一個 [!UICONTROL Audience Lab]以模型1段作為基線 *，另一個以模型2段作為基線*** 。

   * 請讓兩個測試群組的變數保持相同：相同的目的地、創意、轉換特性。
   * 請確定測試區段的使用者數量相近（例如160萬和180萬是正確的，160萬和1600萬不是正確的）。
   * 在每個測試區段測試群組中保留控制區段。 如此，您就可以保留每個區段的一小部分，而不會在測試中明確定位。

1. 檢查結果：

   * Audience lab報 [表檢視](../../features/audience-lab/audience-lab-reporting-view.md) ，將顯示每個模型所推動的轉換數。 對於轉換型促銷活動，驅動最多轉換的測試區段將代表執行成效最佳的模型。
   * 由於您擁有控制區段，因此您也可以評估模型對「標準定位」的運作方式。 您不僅測試一種模型，還測試「此模型是否比一般做法更好？」

## 測試各目標地的創意素材 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用 [!UICONTROL Audience Lab] 測量創意人員在不同目標上所推動的轉換數。 此使用案例也可讓您測量創意素材的轉換與自然發生的轉換。

1. [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選取您要針對創意素材進行測試的區段作為基準區段。
1. 將基準區段分割為測試區段和控制區段。
1. 將測試區段對應至您要測試的不同目的地。
1. 控制段可以預扣且不映射至任何目的地。 測試創意人員不應將控制區段定位為設定自然發生的轉換結果基準。
1. 指定測試的開始日期和結束日期。
1. 在目標位置設定區段和創意素材。
1. Audience Lab [報表檢視](../../features/audience-lab/audience-lab-reporting-view.md) ，將顯示創意人員在各目標地區推動的轉換次數。
1. 由於您建立了控制區段，因此您也可以評估創意對自然發生的轉換有何影響。 您正在測試這個問題：「此創意產生的轉換率是否高於一般實務？」
