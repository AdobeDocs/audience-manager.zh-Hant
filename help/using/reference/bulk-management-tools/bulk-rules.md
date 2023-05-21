---
description: 建立和更新工作表接受traitRule標題，該標題允許您在單個操作中應用多個規則。 按照以下說明進行批量規則請求。
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: 建立或更新特徵規則和區段規則
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 8%

---

# 建立或更新特徵規則和區段規則{#create-or-update-trait-rules-and-segment-rules}

建立和更新工作表接受traitRule標題，該標題允許您在單個操作中應用多個規則。 按照以下說明進行批量規則請求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

## 使用特質規則 {#trait-rules}

在工作表中，特性規則列返回並接受由布爾表達式、比較運算子和規則運算式組成的規則。 可以在中建立具有特徵或段生成器的規則 [!DNL Audience Manager] 並複製到您的工作表中。 或者，如果您熟悉規則語法，則可以直接在工作表中編寫表達式。

## 規則生成器示例 {#rule-builder-example}

讓我們看一個演示如何使用的示例 [!UICONTROL Segment Builder] 要建立規則，您可以訪問批量工作表。 但是，這不是這些工具的一組逐步說明。 相反，我們將從一個已經建立的簡單規則開始。 有關如何使用規則生成器的說明，請參閱 [段生成器](../../features/segments/segment-builder.md) 和 [特性生成器](../../features/traits/about-trait-builder.md)。

利用可視化規則生成器，我們建立了一個包含3個特徵的段規則和一個布爾型 [!UICONTROL AND] 運算子。

![](assets/visualrule.png)

按一下 **[!UICONTROL Code View]** 獲取此規則的文本版本。

>[!TIP]
>
>按一下 **[!UICONTROL Validate Expression]** 檢查規則邏輯。 這將有助於阻止您上載無效規則。

![](assets/coderule.png)

將規則貼上到 [!UICONTROL Bulk Management Tools] 並提交更改以批量更新段規則。

![](assets/segmentrule.png)

## 建立您自己的規則 {#create-rules}

你可以在外部寫你自己的規則 [!UICONTROL Rule Builder]。 開始之前，請務必閱讀包含運算子、表達式和必需變數等內容的文檔。 我們建議您查看以下內容：

* [在特徵生成器中使用比較運算子](../../features/traits/trait-comparison-operators.md)
* [操作順序](../../features/traits/trait-operator-precedence.md)
* [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md)
* [使用布林值和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)
