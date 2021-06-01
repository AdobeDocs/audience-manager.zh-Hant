---
description: Audience Lab可讓您使用基線區段來建立測試群組，以啟用數個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段最能有效促進轉換。
seo-description: Audience Lab可讓您使用基線區段來建立測試群組，以啟用數個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段最能有效促進轉換。
seo-title: Audience Lab 使用案例
solution: Audience Manager
title: Audience Lab 使用案例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Audience Lab 使用案例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允許您使用基線區段來建立測試群組，以啟用數個使用案例。您可以將測試群組劃分為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪個區段最能有效促進轉換。

## 在Audience Lab {#compare-models}中比較模型

在[!DNL Audience Manager]中，可以使用幾種不同的模型類型和源。 [!UICONTROL Audience Lab] 可讓您輕鬆比較使用中模型上客戶的轉換率。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您會比較不同的模型。 您可以使用透過內部資料倉庫建立的模型，並在[!DNL Audience Manager]中將其匯入為[已上線特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)，或使用[!DNL Audience Manager]中的[演算法模型](../../features/algorithmic-models/understanding-models.md)功能。

1. 在[模型產生器](../../features/algorithmic-models/create-model.md)中，或透過外部平台建立兩個模型。
1. 從演算法模型建立[演算法特徵](../../features/traits/create-algorithmic-traits.md)，或將您自己的模型匯入為已上線特徵。
1. 建立互斥的區段，使兩個模型中的使用者不會重疊：

   * 建立&#x200B;*模型1段*&#x200B;和&#x200B;*模型2段*。
   * 讓&#x200B;*模型1區段*&#x200B;的區段規則為模型1特徵[!DNL AND NOT]模型2特徵，而&#x200B;*模型2區段*&#x200B;的區段規則為反向。

1. [在中建立兩個](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 區段測 [!UICONTROL Audience Lab]試組，一個以模 *型1* 段作為基線，另一個以模型2 *段作* 為基線。

   * 兩個測試群組的變數保持相同：相同的目的地、創意、轉換特徵。
   * 請確定測試區段的使用者人數相似（例如160萬和180萬是正常值、160萬和1600萬不是正常值）。
   * 在每個測試區段測試群組中保留一個控制區段。 這樣，您就可以設定每個區段的一小部分，而不是在測試中明確鎖定這些區段。

1. 檢查結果：

   * [Audience Lab報表檢視](../../features/audience-lab/audience-lab-reporting-view.md)將顯示每個模型的轉換次數。 對於轉換型促銷活動，推動最多轉換的測試區段表示表現最佳的模型。
   * 因為您有控制區段，您也可以評估模型對「標準鎖定目標」的運作方式。 您不僅測試了一個模型還是另一個模型，還測試了「此模型是否比正常做法更好？」

## 測試各目的地的創作素材{#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]測量創意在不同目的地推動的轉換次數。 此使用案例也可讓您測量創意內容的轉換與自然發生的轉換。

1. [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選取您要測試創意素材的區段作為基準區段。
1. 將基線區段分割為測試區段和控制區段。
1. 將測試區段對應至您要測試的不同目的地。
1. 控制區段可以預扣，且不會對應至任何目的地。 測試創意素材不應將控制區段設為目標，以設定自然發生的轉換的結果基線。
1. 指定測試的開始日期和結束日期。
1. 在目的地中設定區段和創意內容。
1. [Audience Lab報表檢視](../../features/audience-lab/audience-lab-reporting-view.md)將顯示創意在各個目的地的轉換次數。
1. 由於您已建立控制區段，因此您也可以評估創意如何針對自然發生的轉換而執行。 您正在測試以下問題：「此創意產生的轉換率是否高於一般實務？」
