---
description: 在「特徵產生器」中，「運算式產生器」可讓您建立並測試建立讀者資格要求的規則。 規則由關鍵值配對組成，例如「color == blue」或「price > 100」。 比較運算子可建立索引鍵與值之間的關係。 布林運算式會決定規則群組之間的關係。
seo-description: 在「特徵產生器」中，「運算式產生器」可讓您建立並測試建立讀者資格要求的規則。 規則由關鍵值配對組成，例如「color == blue」或「price > 100」。 比較運算子可建立索引鍵與值之間的關係。 布林運算式會決定規則群組之間的關係。
seo-title: 管理特徵規則
solution: Audience Manager
title: 管理特徵規則
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# 管理特徵規則 {#managing-trait-rules}

在中 [!UICONTROL Trait Builder]，您可 [!UICONTROL Expression Builder] 以建立並測試建立受眾資格要求的規則。 規則由鍵值對組成，如 `color == blue` 或 `price > 100`。 比較運算子可建立索引鍵與值之間的關係。 [!DNL Boolean] 運算式會決定規則群組之間的關係。

<!-- c_tb_rules.xml -->

## 說明的主要信號規則功能

![](assets/manage-trait-rules.png)

1. 此 **[!UICONTROL Expression Builder]** 或 **[!UICONTROL Code View]** 標籤提供特徵規則的概述。 此標 **[!UICONTROL Expression Builder]** 簽可讓您使用欄位和下拉式選單建立規則。 您可 **[!UICONTROL Code View]** 以透過手動將這些運算式寫入程式碼來建立規則。 上圖顯示由信號組成的簡單特徵，該信號用於評估產品鍵等於特定值的合格條件（在本例中） `color == "blue"`。

1. 本節中的欄位和控制項可讓您從鍵值配對建立訊號，並使用比較運算子來設定它們之間的關係。 索引鍵、運算子和值是必要項。
1. 可 [!UICONTROL Data Explorer Options] 讓您回填訊號的特徵實現。
   >[!NOTE]
   >
   >此選項僅適用於客 [!UICONTROL Data Explorer] 戶。 如需詳細資訊，請洽詢您的Adobe顧問。
1. 本節顯示過去7天內回填和非回填特徵的特徵實現估計值，以及在中定 [!UICONTROL Expression Builder]義的信號。
   >[!NOTE]
   >
   >此選項僅適用於客 [!UICONTROL Data Explorer] 戶。 如需詳細資訊，請洽詢您的Adobe顧問。
1. 測試欄位可讓您驗證訊號規則的組合， [!DNL URL]或是您要在傳送資料至Audience Manager時使用的組合。

## 建立特徵規則 {#create-trait-rule}

規則（或運算式）由個別或索引鍵值配對群組組成。 比較運算子會設定鍵值對之間的關係。 若要建立規則，請提供索引鍵、值、選取運算子，然後按一下 **[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

建立特徵規則前，請先填 **[!UICONTROL Basic Information]** 寫 *區段* 的必要欄位。

1. 展開該 **[!UICONTROL Trait Expression]** 部分並輸入鍵和值名稱。 這會建立 *`signal`*。
   >[!NOTE]
   >
   >如果您的 `c_` 事件呼叫使用該語法傳送資料給，請加入關鍵變數的首碼(或任何其他命 [!DNL Audience Manager] 名慣例)。
1. 從下拉式清 [單中選取比較運](../../features/traits/trait-comparison-operators.md) 算 **[!UICONTROL Operator]** 子。 比較運算子評估信號中各元素之間的關係。
   >[!NOTE]
   >
   >操 [!DNL Boolean] 作器 [!UICONTROL OR] 建立群組內多個信號 *之間的關* 系，且不能更改。
1. 按一下 **[!UICONTROL Add Rule]**. 儲存的規則會顯示在資料輸入欄位上方的特徵工作區中。

### 範例 {#example-trait-rule}

在下列範例中，使用者已根據產品ID建立新的特徵規則。 若要建立此規則，使用者會將連結有等 `productkey` 於運算元( `==`)的索引鍵提供給值 `2093`。
![](assets/tb_sample_rule1.png)

按一 **[!UICONTROL Add Rule]** 下可儲存特徵並將特徵移至工 [!UICONTROL Expression Builder] 作區。

![](assets/tb_sample_rule2.png)

## Create a New Rule Group {#create-rule-group}

此程式說明如何建立新的規則群組。

<!-- t_tb_new_rule_group.xml -->

您的特徵必須至少包含兩個規則，才能建立新的規則群組。

1. 將游標移到要移動的規則上，以反白顯示。
1. 將滑鼠指標暫留在反白顯示的規則邊框上。
這會自動將規則與其目前群組分開，並將其移入新群組。
   >[!NOTE]
   >
   >如果您無意中移動規則，請將規則拖回其原始群組。
1. 從下拉 [!DNL Boolean] 式選單中選 [!UICONTROL AND]取運算 [!UICONTROL OR]子(、、 [!UICONTROL AND NOT])，以設定規則群組之間的關係。

## 在群組之間移動規則 {#move-rules-between-groups}

若要移動規則，請按一下並拖曳至其他群組。

## 編輯特徵 {#edit-trait}

此程式說明如何編輯特徵。

<!-- t_tb_edit.xml -->

1. 在控制 [!UICONTROL Traits] 面板中，將滑鼠指標暫 **[!UICONTROL Actions]** 留在您要編輯之特徵的欄上。 這會顯示特徵管理圖示。
1. 按一下鉛筆以編輯特徵。

   ![](assets/tb_edit_trait.png)

## 刪除特徵規則 {#delete-trait}

此程式說明如何刪除特徵規則。

<!-- t_tb_delete_rule.xml -->

1. 在控制 [!UICONTROL Traits] 面板中，將滑鼠指標暫 [!UICONTROL Actions] 留在您要編輯的特徵欄上，然後按一下鉛筆圖示。 這會顯示特徵管理圖示。
1. Expand the [!UICONTROL Trait Expression] section.
1. 將滑鼠指標暫留在您要刪除的規則上，然後按一下X圖示。 規則會立即刪除。

>[!MORELIKETHIS]
>
>* [建立新規則群組](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [建立特徵規則](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [刪除特徵規則](../../features/traits/manage-trait-rules.md#delete-trait)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

