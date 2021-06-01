---
description: 在特徵產生器中，運算式產生器可讓您建立並測試規則，以建立受眾資格要求。 規則包含機碼值組，例如「color == blue」或「price &gt;100英吋。 比較運算子會建立索引鍵和值之間的關係。 布林運算式決定規則群組之間的關係。
seo-description: 在特徵產生器中，運算式產生器可讓您建立並測試規則，以建立受眾資格要求。 規則包含機碼值組，例如「color == blue」或「price &gt;100英吋。 比較運算子會建立索引鍵和值之間的關係。 布林運算式決定規則群組之間的關係。
seo-title: 管理特徵規則
solution: Audience Manager
title: 管理特徵規則
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: 特徵
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# 管理特徵規則 {#managing-trait-rules}

在[!UICONTROL Trait Builder]中， [!UICONTROL Expression Builder]可讓您建立並測試建立受眾資格要求的規則。 規則包含機碼值組，例如`color == blue`或`price > 100`。 比較運算子會建立索引鍵和值之間的關係。 [!DNL Boolean] 運算式會決定規則群組之間的關係。

<!-- c_tb_rules.xml -->

## 說明的主要訊號規則功能

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]**&#x200B;或&#x200B;**[!UICONTROL Code View]**&#x200B;標籤提供特徵規則的概觀。 **[!UICONTROL Expression Builder]**&#x200B;標籤可讓您建立包含欄位和下拉式功能表的規則。 **[!UICONTROL Code View]**&#x200B;可讓您手動將這些運算式寫入程式碼，以建立規則。 上圖顯示一個簡單特徵，由一個信號組成，該信號用於評估產品鍵等於特定值（在此例中為`color == "blue"`）的合格條件的資料。

1. 本節中的欄位和控制項可讓您從索引鍵值配對建立訊號，並使用比較運算子設定兩者之間的關係。 索引鍵、運算子和值為必要項目。
1. [!UICONTROL Data Explorer Options]可讓您回填訊號的特徵實現。

   >[!NOTE]
   >
   >此選項僅適用於[!UICONTROL Data Explorer]客戶。 如需詳細資訊，請連絡您的Adobe顧問。

1. 本節針對[!UICONTROL Expression Builder]中定義的訊號，顯示過去7天內回填和非回填特徵的特徵實現估計值。

   >[!NOTE]
   >
   >此選項僅適用於[!UICONTROL Data Explorer]客戶。 如需詳細資訊，請連絡您的Adobe顧問。

1. 測試欄位可讓您驗證訊號規則的組合，或在將資料傳送至Audience Manager時要使用的[!DNL URL]。

## 建立特徵規則{#create-trait-rule}

規則（或運算式）由個別或機碼值組群組組成。 比較運算子會設定機碼值組之間的關係。 若要建立規則，請提供索引鍵、值、選取運算子，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

在&#x200B;*建立特徵規則之前，填寫&#x200B;**[!UICONTROL Basic Information]**區段*&#x200B;中的必填欄位。

1. 展開&#x200B;**[!UICONTROL Trait Expression]**&#x200B;區段，並輸入索引鍵和值名稱。 這會建立&#x200B;*`signal`*。

   >[!NOTE]
   >
   >如果您的事件呼叫使用該語法將資料傳送至[!DNL Audience Manager]，請加入金鑰變數的`c_`首碼（或任何其他命名慣例）。

1. 從&#x200B;**[!UICONTROL Operator]**&#x200B;下拉式清單中選取[比較運算子](../../features/traits/trait-comparison-operators.md)。 比較運算子評估信號中各元素之間的關係。

   >[!NOTE]
   >
   >[!DNL Boolean] [!UICONTROL OR]運算子在&#x200B;*組內建立多個信號*&#x200B;之間的關係，並且不能更改。

1. 按一下 **[!UICONTROL Add Rule]**. 儲存的規則會顯示在特徵工作區中資料輸入欄位上方。

### 範例 {#example-trait-rule}

在下列範例中，使用者已根據產品ID建立新的特徵規則。 若要建立此規則，使用者將連結有等於運算子(`==`)的索引鍵`productkey`提供至值`2093`。

![](assets/tb_sample_rule1.png)

按一下&#x200B;**[!UICONTROL Add Rule]**&#x200B;會儲存特徵並將其移入[!UICONTROL Expression Builder]工作區。

![](assets/tb_sample_rule2.png)

## 建立新規則組{#create-rule-group}

此程式說明如何建立新規則群組。

<!-- t_tb_new_rule_group.xml -->

您的特徵必須至少包含兩個規則，才能建立新的規則群組。

1. 將游標移到要移動的規則上以突出顯示它。
1. 將滑鼠指標暫留在醒目提示的規則邊框上。

   這會自動將規則與其目前群組分開，並將其移入新群組。

   >[!NOTE]
   >
   >如果您無意中將規則移回原始群組，請將其拖曳回原始群組。

1. 從下拉式選單中選取[!DNL Boolean]運算子([!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT])，以設定規則群組之間的關係。

## 在組之間移動規則{#move-rules-between-groups}

若要移動規則，請按一下，然後將其拖曳至其他群組。

## 編輯特徵{#edit-trait}

此程式說明如何編輯特徵。

<!-- t_tb_edit.xml -->

1. 在[!UICONTROL Traits]控制面板中，將滑鼠移至&#x200B;**[!UICONTROL Actions]**&#x200B;欄上方，即可找到您要編輯的特徵。 這會顯示特徵管理圖示。
1. 按一下鉛筆即可編輯特徵。

   ![](assets/tb_edit_trait.png)

## 刪除特徵規則{#delete-trait}

此程式說明如何刪除特徵規則。

<!-- t_tb_delete_rule.xml -->

1. 在[!UICONTROL Traits]控制面板中，將滑鼠移至您要編輯之特徵的[!UICONTROL Actions]欄上，然後按一下鉛筆圖示。 這會顯示特徵管理圖示。
1. 展開[!UICONTROL Trait Expression]區段。
1. 將滑鼠指標暫留在您要刪除的規則上，然後按一下X圖示。 規則會立即刪除。

>[!MORELIKETHIS]
>
>* [建立新規則群組](../../features/traits/manage-trait-rules.md#create-rule-group)
* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
* [建立特徵規則](../../features/traits/manage-trait-rules.md#create-trait-rule)
* [刪除特徵規則](../../features/traits/manage-trait-rules.md#delete-trait)
* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

