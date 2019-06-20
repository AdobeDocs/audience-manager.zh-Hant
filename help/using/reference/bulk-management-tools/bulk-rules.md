---
description: 建立和更新工作表接受「Tritrule」標題，可讓您在單一作業中套用多個規則。請依照下列指示進行大量規則要求。
seo-description: 建立和更新工作表接受「Tritrule」標題，可讓您在單一作業中套用多個規則。請依照下列指示進行大量規則要求。
seo-title: 建立或更新特徵規則和區段規則
solution: Audience Manager
title: 建立或更新特徵規則和區段規則
uuid: bdd5f8f1-be83-4844-b681-654e45 ACE3 e1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

建立和更新工作表接受「Tritrule」標題，可讓您在單一作業中套用多個規則。請依照下列指示進行大量規則要求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具的提供目的僅限於方便使用。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI](../../features/administration/administration-overview.md) 中指派的RBAC群組權限 [!DNL Audience Manager] 會受到尊重 [!UICONTROL Bulk Management Tools]。

## Working with trait rules {#trait-rules}

在工作表中，特徵規則欄會傳回並接受由布林運算式、比較運算子和規則運算式組成的規則。You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. 或者，如果您熟悉規則語法，則可以直接在工作表中編寫運算式。

## Rule builder example {#rule-builder-example}

Let&#39;s take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. 不過，這並不是這些工具的逐步指示。我們將從一個已建立的簡單規則開始。For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we&#39;ve created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. 這有助於防止您上傳無效規則。

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. 開始之前，請務必閱讀包含運算元、運算式和必要變數等項目的文件。建議您檢閱下列內容：

* [使用特徵產生器中的比較運算子](../../features/traits/trait-comparison-operators.md)
* [操作順序](../../features/traits/trait-operator-precedence.md)
* [關鍵變數的首碼需求](../../features/traits/trait-variable-prefixes.md)
* [使用布林和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)

