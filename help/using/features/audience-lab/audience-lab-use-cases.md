---
description: Audience Lab可讓您使用基準區段來建立測試群組，進而啟用數個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，並將這些區段對應至不同的目的地，然後判斷哪些區段在推動轉換方面最有效。
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Audience Lab使用案例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Audience Lab使用案例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab]可讓您使用基準線區段來建立測試群組，以啟用數個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，並將這些區段對應至不同的目的地，然後判斷哪些區段在推動轉換方面最有效。

## 在Audience Lab中比較模型 {#compare-models}

您可以在[!DNL Audience Manager]中使用數種不同型別的模型和來源。 [!UICONTROL Audience Lab]可讓您輕鬆比較使用中模型間客戶的轉換率。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您會比較不同的模型。 您可以使用透過內部資料倉儲建立的模型，並在[!DNL Audience Manager]中將其匯入為[已上線特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)，或者您可以使用[中的](../../features/algorithmic-models/understanding-models.md)演演算法模型[!DNL Audience Manager]功能。

1. 在[模型產生器](../../features/algorithmic-models/create-model.md)中或透過外部平台建立兩個模型。
1. 從演演算法模型建立[演演算法特徵](../../features/traits/create-algorithmic-traits.md)，或將您自己的模型匯入為已登入的特徵。
1. 建立互斥區段，讓兩個模型中的使用者不會重疊：

   * 建立&#x200B;*模型1區段*&#x200B;和&#x200B;*模型2區段*。
   * 讓&#x200B;*模型1區段*&#x200B;的區段規則成為[!DNL AND NOT]模型2區段&#x200B;*的模型1特徵*&#x200B;模型2特徵，反之亦然。

1. [在](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)中建立兩個區段測試群組[!UICONTROL Audience Lab]，一個以&#x200B;*模型1區段*&#x200B;作為基準，另一個以&#x200B;*模型2區段*&#x200B;作為基準。

   * 讓兩個測試群組的變數保持相同：相同的目的地、創意和轉換特徵。
   * 確定測試區段具有相似的使用者人數（例如160萬和180萬正確，160萬和1600萬不正確）。
   * 在每個測試區段測試群組中保留控制區段。 如此一來，您可以預留每個區段的一小部分，且不會在測試中明確鎖定這些區段。

1. 檢查結果：

   * [Audience Lab報表檢視](../../features/audience-lab/audience-lab-reporting-view.md)將顯示每個模型正在推動的轉換次數。 對於以轉換為基礎的促銷活動，驅動最多轉換的測試區段將表示績效最佳的模式。
   * 由於您有控制區段，因此也可以根據「標準鎖定目標」評估模型的表現。 您不僅要測試一個模型與另一個模型，還要測試「此模型是否比正常實務做得更好？」的問題。

## 跨目的地測試創意 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]測量創意內容在不同目的地推動的轉換次數。 此使用案例也可讓您根據自然發生的轉換來測量創意的轉換。

1. [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選取您要用來測試創意作為基準區段的區段。
1. 將基準線區段分割成測試區段和控制區段。
1. 將測試區段對應至您要測試的不同目的地。
1. 控制區段可以保留，並且不會對應到任何目的地。 測試創意不應將控制區段設為目標，以設定自然發生轉換的結果基準。
1. 指定測試的開始日期和結束日期。
1. 在目的地中設定區段和創意內容。
1. [Audience Lab報告檢視](../../features/audience-lab/audience-lab-reporting-view.md)會顯示創意內容在目的地推動的轉換次數。
1. 由於您建立了控制區段，因此您也可以根據自然發生的轉換來評估創意表現。 您正在測試問題：「此創意是否產生比一般實務更高的轉換率？」
