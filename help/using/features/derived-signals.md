---
description: 衍生訊號可讓網站訪客根據他們已看到的特性，獲得其他特性的資格。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-description: 衍生訊號可讓網站訪客根據他們已看到的特性，獲得其他特性的資格。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-title: 衍生信號
solution: Audience Manager
title: 衍生信號
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# 衍生信號 {#derived-signals}

依據 [!UICONTROL derived signal] 訪客已看到的特徵，篩選其他特徵的合格網站訪客。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。

<!-- c_tb_derived_signal.xml -->

## 衍生信號的用途

在中 [!DNL Audience Manager]，您可以在事件呼叫期間傳入至其他指定訊號或特徵的訊號（或特徵規則）之間建立關係。 例如，假設事件呼叫在由鍵值()組成的信號中 [!DNL "product = new_car"]`https://<domain alias>/event?product=new_car`傳遞。 [!DNL Audience Manager] 會將該訊號連接至使用工具建立的其他 [!UICONTROL derived signals] 人。 雖然相關信號可以是您指定的任何鍵值，但在連結至已設定為規則的現有信號時，它們最有 [!UICONTROL Trait Builder] 用。 例如，在下圖中，當使用者動作觸發信號時，使用者也 [!DNL "product = new car"] 可符合目標鍵和值訊號所定義的特徵。

![](assets/derived_signal_example.png)

## 導出信號的位置

從側欄導覽 [!UICONTROL derived signals] 中建 **[!UICONTROL Tools > Derived Signals]** 立並管理。

## 建立派生信號 {#create}

<!-- t_tb_create_derived.xml -->

要建立 [!UICONTROL derived signal]:

1. 從功 **[!UICONTROL Derived Signals]** 能表中 [!UICONTROL Tools] 選取。
1. 提供：
   * *（可選）*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Click **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>、、、和欄位 [!UICONTROL Source Key]的字 [!UICONTROL Source Value]元限 [!UICONTROL Target Key]制為 [!UICONTROL Target Value] 228個字元。

## 編輯派生信號 {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. 將滑鼠指標暫留在訊號上，然後按一下 **[!UICONTROL Edit]**。
2. 變更所需的程式碼、金鑰或值，然後按一下 **[!UICONTROL Save]**。

## 刪除派生信號 {#delete}

<!-- t_tb_delete_derived.xml -->

若要刪除 [!UICONTROL derived signal]，請將滑鼠指標暫留在訊號上，然後按一下 **[!UICONTROL Delete]**。
