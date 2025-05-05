---
description: 在特徵產生器中，運算式產生器可讓您建立和測試建立對象資格要求的規則。 規則包含索引鍵值配對，例如"color == blue"或"price&amp；gt； 100"。 比較運運算元建立索引鍵和值之間的關係。 布林值運算式決定規則群組之間的關係。
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: 管理特徵規則
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# 管理特徵規則 {#managing-trait-rules}

在[!UICONTROL Trait Builder]中，[!UICONTROL Expression Builder]可讓您建立和測試建立對象資格要求的規則。 規則包含`color == blue`或`price > 100`之類的機碼值組。 比較運運算元建立索引鍵和值之間的關係。 [!DNL Boolean]運算式決定規則群組之間的關係。

<!-- c_tb_rules.xml -->

## 主要訊號規則功能說明

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]**&#x200B;或&#x200B;**[!UICONTROL Code View]**&#x200B;標籤會提供您特徵中規則的概觀。 **[!UICONTROL Expression Builder]**&#x200B;索引標籤可讓您使用欄位和下拉式功能表建立規則。 **[!UICONTROL Code View]**&#x200B;可讓您以手動方式將這些運算式寫入程式碼來建立規則。 上圖顯示由訊號組成的簡單特徵，該訊號會針對產品金鑰等於特定值（在此例中為`color == "blue"`）的合格條件評估資料。

1. 本節中的欄位和控制項可讓您從索引鍵/值組建立訊號，並使用比較運運算元設定它們之間的關係。 需要索引鍵、運運算元和值。
1. [!UICONTROL Data Explorer Options]可讓您回填訊號的特徵實現。

   >[!NOTE]
   >
   >此選項僅適用於[!UICONTROL Data Explorer]個客戶。 如需詳細資訊，請聯絡您的Adobe顧問。

1. 本節針對[!UICONTROL Expression Builder]中定義的訊號，針對回填和非回填的特徵，顯示過去7天特徵實現的預估值。

   >[!NOTE]
   >
   >此選項僅適用於[!UICONTROL Data Explorer]個客戶。 如需詳細資訊，請聯絡您的Adobe顧問。

1. 測試欄位可讓您驗證傳送資料至Audience Manager時所使用的訊號規則或[!DNL URL]組合。

## 建立特徵規則 {#create-trait-rule}

規則（或運算式）由索引鍵值配對的個別或群組組成。 比較運運算元設定機碼值組之間的關係。 若要建立規則，請提供索引鍵、值、選取運運算元，然後按一下&#x200B;**[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

在建立特徵規則之前&#x200B;*，請先完成&#x200B;**[!UICONTROL Basic Information]**&#x200B;區段*&#x200B;中的必填欄位。

1. 展開&#x200B;**[!UICONTROL Trait Expression]**&#x200B;區段並輸入索引鍵和值名稱。 這會建立&#x200B;*`signal`*。

   >[!NOTE]
   >
   >如果您的事件呼叫使用該語法將資料傳送至[!DNL Audience Manager]，請包含索引鍵變數的`c_`首碼（或任何其他命名慣例）。

1. 從&#x200B;**[!UICONTROL Operator]**&#x200B;下拉式清單中選取[比較運運算元](../../features/traits/trait-comparison-operators.md)。 比較運運算元會評估訊號中元素之間的關係。

   >[!NOTE]
   >
   >[!DNL Boolean] [!UICONTROL OR]運運算元在群組&#x200B;*內的多個訊號*&#x200B;之間建立關係，且無法變更。

1. 按一下&#x200B;**[!UICONTROL Add Rule]**。 已儲存的規則會顯示在資料輸入欄位上方的特徵工作區中。

### 範例 {#example-trait-rule}

在以下範例中，使用者已根據產品ID建立新特徵規則。 若要建置此規則，使用者提供的索引鍵`productkey`連結到值`2093`的equals運運算元( `==`)。

![](assets/tb_sample_rule1.png)

按一下「**[!UICONTROL Add Rule]**」儲存特徵並將其移動到[!UICONTROL Expression Builder]工作區。

![](assets/tb_sample_rule2.png)

## 建立新的規則群組 {#create-rule-group}

此程式說明如何建立新的規則群組。

<!-- t_tb_new_rule_group.xml -->

特徵必須至少包含兩個規則，才能建立新規則群組。

1. 將游標移至您要移動的規則上方，以反白顯示它。
1. 將滑鼠停留在醒目提示的規則邊框上。

   這會自動將規則與其目前群組分開，並將它移動到新群組中。

   >[!NOTE]
   >
   >如果您不小心移動規則，請將規則拖回其原始群組。

1. 從下拉式功能表中選取[!DNL Boolean]運運算元([!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT])，以設定規則群組之間的關係。

## 在群組之間移動規則 {#move-rules-between-groups}

若要移動規則，請按一下「 」，然後將其拖曳至其他群組。

## 編輯特徵 {#edit-trait}

此程式說明如何編輯特徵。

<!-- t_tb_edit.xml -->

1. 在[!UICONTROL Traits]儀表板中，針對您要編輯的特徵，將滑鼠游標停留在&#x200B;**[!UICONTROL Actions]**&#x200B;欄上。 這會顯示特徵管理圖示。
1. 按一下鉛筆以編輯特徵。

   ![](assets/tb_edit_trait.png)

## 刪除特徵規則 {#delete-trait}

此程式說明如何刪除特徵規則。

<!-- t_tb_delete_rule.xml -->

1. 在[!UICONTROL Traits]儀表板中，將滑鼠指標暫留在您要編輯的特徵的[!UICONTROL Actions]欄上，然後按一下鉛筆圖示。 這會顯示特徵管理圖示。
1. 展開[!UICONTROL Trait Expression]區段。
1. 將游標停留在您要刪除的規則上，然後按一下X圖示。 規則會立即刪除。

>[!MORELIKETHIS]
>
>* [建立新的規則群組](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [建立特徵規則](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [刪除特徵規則](../../features/traits/manage-trait-rules.md#delete-trait)
>* [在群組之間移動規則](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
