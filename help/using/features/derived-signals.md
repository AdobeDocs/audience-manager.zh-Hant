---
description: 衍生的信號根據站點訪問者已看到的特性確定其他特性。 換句話說，額外的特質鑑定可以從當前所展示的特質中獲得，即使用戶以前從未見過新的特質。
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: 衍生訊號
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# 衍生訊號 {#derived-signals}

A [!UICONTROL derived signal] 根據他們已經看到的特性，為網站訪問者提供其他特性。 換句話說，額外的特質鑑定可以從當前所展示的特質中獲得，即使用戶以前從未見過新的特質。

<!-- c_tb_derived_signal.xml -->

## 派生信號的目的

在 [!DNL Audience Manager]，可以在事件調用期間傳遞到其它、指定的信號或特徵的信號（或特徵規則）之間建立關係。 例如，假定事件調用在由key-value組成的信號中通過 [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`)。 [!DNL Audience Manager] 會把信號與任何其他 [!UICONTROL derived signals] 工具欄。 雖然關聯的信號可以是您指定的任何鍵值，但當連結到已設定為的現有信號時，它們最有用 [!UICONTROL Trait Builder] 規則。 例如，在下圖中，當用戶操作觸發信號時 [!DNL "product = new car"] 用戶還可以符合由目標鍵和值信號定義的特徵。

![](assets/derived_signal_example.png)

## 派生信號的位置

建立和管理 [!UICONTROL derived signals] 在 **[!UICONTROL Tools > Derived Signals]** 欄。

## 建立派生信號 {#create}

<!-- t_tb_create_derived.xml -->

建立 [!UICONTROL derived signal]:

1. 選擇 **[!UICONTROL Derived Signals]** 從 [!UICONTROL Tools] 的子菜單。
1. 提供：
   * *（可選）* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 按一下 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>的字元限制 [!UICONTROL Source Key]。 [!UICONTROL Source Value]。 [!UICONTROL Target Key], [!UICONTROL Target Value] 欄位為228個字元。

## 編輯派生的信號 {#edit}

<!-- t_tb_edit_derived.xml -->

編輯 [!UICONTROL derived signal]:

1. 將滑鼠懸停在信號上，然後按一下 **[!UICONTROL Edit]**。
2. 更改所需的代碼、鍵或值，然後按一下 **[!UICONTROL Save]**。

## 刪除派生信號 {#delete}

<!-- t_tb_delete_derived.xml -->

刪除 [!UICONTROL derived signal]，懸停在信號上，然後按一下 **[!UICONTROL Delete]**。
