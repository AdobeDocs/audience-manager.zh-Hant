---
description: 在特性生成器中，表達式生成器允許您建立和test建立受眾資格要求的規則。 規則由鍵值對組成，如"color == blue"或"price &gt;100」。 比較運算子建立鍵和值之間的關係。 布爾表達式確定規則組之間的關係。
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: 管理特徵規則
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# 管理特徵規則 {#managing-trait-rules}

在 [!UICONTROL Trait Builder]，也請參見Wiki頁。 [!UICONTROL Expression Builder] 允許您建立和test規則，以建立受眾資格要求。 規則由鍵值對組成，如 `color == blue` 或 `price > 100`。 比較運算子建立鍵和值之間的關係。 [!DNL Boolean] 表達式確定規則組之間的關係。

<!-- c_tb_rules.xml -->

## 主要信號規則功能說明

![](assets/manage-trait-rules.png)

1. 的 **[!UICONTROL Expression Builder]** 或 **[!UICONTROL Code View]** 頁籤提供特性規則的概述。 的 **[!UICONTROL Expression Builder]** 頁籤中，您可以使用欄位和下拉菜單建立規則。 的 **[!UICONTROL Code View]** 允許您通過手動將這些表達式寫入代碼來建立規則。 上圖顯示了一個簡單特性，該特性由一個信號組成，該信號對產品鍵等於特定值的限定條件計算資料 `color == "blue"`。

1. 此部分中的欄位和控制項允許您從鍵值對建立信號，並設定它們與比較運算子之間的關係。 需要鍵、運算子和值。
1. 的 [!UICONTROL Data Explorer Options] 讓你回過頭來瞭解你的信號。

   >[!NOTE]
   >
   >此選項僅適用於 [!UICONTROL Data Explorer] 客戶。 請與Adobe顧問聯繫以瞭解詳細資訊。

1. 本節將為您介紹過去7天中定義的信號的特性實現的估計 [!UICONTROL Expression Builder]，用於回填和非回填特徵。

   >[!NOTE]
   >
   >此選項僅適用於 [!UICONTROL Data Explorer] 客戶。 請與Adobe顧問聯繫以瞭解詳細資訊。

1. test欄位允許您驗證信號規則或 [!DNL URL]在將資料發送到Audience Manager時要使用的。

## 建立特性規則 {#create-trait-rule}

規則（或表達式）由單個或一組鍵值對組成。 比較運算子設定鍵值對之間的關係。 要建立規則，請提供鍵、值，選擇運算子，然後按一下 **[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

完成 **[!UICONTROL Basic Information]** 節 *先* 創造特質規則。

1. 展開 **[!UICONTROL Trait Expression]** ，然後輸入鍵和值名稱。 這將建立 *`signal`*。

   >[!NOTE]
   >
   >包括 `c_` 如果事件調用將資料發送到，則鍵變數的前置詞（或任何其他命名約定） [!DNL Audience Manager] 用那句語法。

1. 選擇 [比較算子](../../features/traits/trait-comparison-operators.md) 從 **[!UICONTROL Operator]** 下拉清單。 比較算子評估信號中的元素之間的關係。

   >[!NOTE]
   >
   >的 [!DNL Boolean] [!UICONTROL OR] 操作者建立多個信號之間的關係 *內* 組，不能更改。

1. 按一下 **[!UICONTROL Add Rule]**. 保存的規則顯示在資料輸入欄位上方的traits工作區中。

### 範例 {#example-trait-rule}

在下例中，用戶已基於產品ID建立了新的特性規則。 要生成此規則，用戶提供了 `productkey` 與等號運算子連結( `==`)到值 `2093`。

![](assets/tb_sample_rule1.png)

按一下 **[!UICONTROL Add Rule]** 保存並移入 [!UICONTROL Expression Builder] 工作區。

![](assets/tb_sample_rule2.png)

## 建立新規則組 {#create-rule-group}

此過程介紹如何建立新規則組。

<!-- t_tb_new_rule_group.xml -->

您的特性必須至少包含兩個規則，然後才能建立新規則組。

1. 將游標移到要移動的規則上以突出顯示它。
1. 懸停在突出顯示的規則邊框上。

   這會自動將規則與其當前組分離，並將其移入新組。

   >[!NOTE]
   >
   >如果無意中移動規則，請將其拖回其原始組。

1. 選擇 [!DNL Boolean] 運算子([!UICONTROL AND]。 [!UICONTROL OR]。 [!UICONTROL AND NOT])，以設定規則組之間的關係。

## 在組之間移動規則 {#move-rules-between-groups}

要移動規則，請按一下並將其拖動到另一個組。

## 編輯特性 {#edit-trait}

此過程說明如何編輯特性。

<!-- t_tb_edit.xml -->

1. 在 [!UICONTROL Traits] 操控板，懸停在 **[!UICONTROL Actions]** 的子菜單。 這就引出了特質管理表徵圖。
1. 按一下鉛筆編輯特徵。

   ![](assets/tb_edit_trait.png)

## 刪除特性規則 {#delete-trait}

此過程說明如何刪除特性規則。

<!-- t_tb_delete_rule.xml -->

1. 在 [!UICONTROL Traits] 操控板，懸停在 [!UICONTROL Actions] 列，然後按一下鉛筆表徵圖。 這就引出了特質管理表徵圖。
1. 展開 [!UICONTROL Trait Expression] 的子菜單。
1. 將滑鼠懸停在要刪除的規則上，然後按一下X表徵圖。 該規則將立即刪除。

>[!MORELIKETHIS]
>
>* [建立新規則組](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [建立特性規則](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [刪除特性規則](../../features/traits/manage-trait-rules.md#delete-trait)
>* [在組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

