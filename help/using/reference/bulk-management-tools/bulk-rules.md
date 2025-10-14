---
description: 建立和更新工作表接受traitRule標頭，可讓您在單一作業中套用多個規則。 請依照這些指示，提出大量規則要求。
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: 建立或更新特徵規則和區段規則
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# 建立或更新特徵規則和區段規則{#create-or-update-trait-rules-and-segment-rules}

建立和更新工作表接受traitRule標頭，可讓您在單一作業中套用多個規則。 請依照這些指示，提出大量規則要求。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>在[&#x200B; UI中指派的](../../features/administration/administration-overview.md)RBAC群組許可權[!DNL Audience Manager]已在[!UICONTROL Bulk Management Tools]中接受。

## 使用特徵規則 {#trait-rules}

在您的工作表中，特徵規則欄會傳回並接受包含布林運算式、比較運運算元和規則運算式的規則。 您可以在[!DNL Audience Manager]中使用特徵或區段產生器建立規則，並將這些規則複製到您的工作表中。 或者，如果您熟悉規則語法，可以直接在工作表中編寫運算式。

## 規則產生器範例 {#rule-builder-example}

讓我們看一個範例，此範例示範如何使用[!UICONTROL Segment Builder]建立您可以大量使用的規則。 不過，這不是這些工具的一組逐步指示。 相反地，我們將以已建立的簡單規則開始。 如需如何使用規則產生器的指示，請參閱[區段產生器](../../features/segments/segment-builder.md)和[特徵產生器](../../features/traits/about-trait-builder.md)。

使用視覺化規則產生器，我們已建立具有3個特徵和Boolean [!UICONTROL AND]運運算元的區段規則。

![](assets/visualrule.png)

按一下&#x200B;**[!UICONTROL Code View]**&#x200B;以取得此規則的文字版本。

>[!TIP]
>
>按一下&#x200B;**[!UICONTROL Validate Expression]**&#x200B;以檢查您的規則邏輯。 這有助於防止您上傳無效的規則。

![](assets/coderule.png)

將規則貼入[!UICONTROL Bulk Management Tools]工作表並認可您的變更，以大量更新區段規則。

![](assets/segmentrule.png)

## 建立您自己的規則 {#create-rules}

您可以在[!UICONTROL Rule Builder]之外撰寫您自己的規則。 開始之前，請務必閱讀涵蓋運運算元、運算式和必要變數等內容的檔案。 建議您檢閱下列內容：

* [在特徵產生器中使用比較運運算元](../../features/traits/trait-comparison-operators.md)
* [作業順序](../../features/traits/trait-operator-precedence.md)
* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)
* [使用布林值和比較運運算元的運算式範例](../../features/traits/trait-expression-samples.md)
