---
description: 建立和更新工作表接受traitRule標題，可讓您在單一操作中套用多個規則。 請依照下列指示，提出大量規則要求。
seo-description: 建立和更新工作表接受traitRule標題，可讓您在單一操作中套用多個規則。 請依照下列指示，提出大量規則要求。
seo-title: 建立或更新特徵規則和區段規則
solution: Audience Manager
title: 建立或更新特徵規則和區段規則
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# 建立或更新特徵規則和區段規則{#create-or-update-trait-rules-and-segment-rules}

建立和更新工作表接受traitRule標題，可讓您在單一操作中套用多個規則。 請依照下列指示，提出大量規則要求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

## 使用特徵規則{#trait-rules}

在您的工作表中，特徵規則欄會傳回並接受由布林運算式、比較運算子和規則運算式組成的規則。 您可以在[!DNL Audience Manager]中建立具有特徵或區段產生器的規則，並將其複製至您的工作表。 或者，如果您熟悉規則語法，則可以直接在工作表中撰寫運算式。

## 規則產生器範例{#rule-builder-example}

讓我們來看一個範例，示範如何使用[!UICONTROL Segment Builder]來建立可用於大量工作表的規則。 不過，這不是這些工具的一組逐步指示。 相反，我們將從一個已經建立的簡單規則開始。 如需規則產生器的使用說明，請參閱[區段產生器](../../features/segments/segment-builder.md)和[特徵產生器](../../features/traits/about-trait-builder.md)。

我們使用可視化規則產生器建立了具有3個特徵的區段規則，並使用布林值[!UICONTROL AND]運算子。

![](assets/visualrule.png)

按一下&#x200B;**[!UICONTROL Code View]**&#x200B;以取得此規則的文字版本。

>[!TIP]
>
>按一下&#x200B;**[!UICONTROL Validate Expression]**&#x200B;以檢查規則邏輯。 這有助於防止您上傳無效規則。

![](assets/coderule.png)

將規則貼入[!UICONTROL Bulk Management Tools]工作表，並提交您的變更以大量更新區段規則。

![](assets/segmentrule.png)

## 建立您自己的規則{#create-rules}

您可以在[!UICONTROL Rule Builder]之外撰寫您自己的規則。 開始之前，請務必閱讀涵蓋運算子、運算式和必要變數等內容的檔案。 建議您檢閱下列項目：

* [在特徵產生器中使用比較運算子](../../features/traits/trait-comparison-operators.md)
* [操作順序](../../features/traits/trait-operator-precedence.md)
* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)
* [使用布林值和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)
