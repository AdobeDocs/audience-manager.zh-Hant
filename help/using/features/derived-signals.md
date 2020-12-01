---
description: 衍生訊號可讓網站訪客根據他們已看到的特性，獲得其他特性的資格。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-description: 衍生訊號可讓網站訪客根據他們已看到的特性，獲得其他特性的資格。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-title: 衍生訊號
solution: Audience Manager
title: 衍生訊號
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# 衍生訊號 {#derived-signals}

[!UICONTROL derived signal]會根據網站訪客已看到的特性，讓其他特性符合網站訪客的資格。 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。

<!-- c_tb_derived_signal.xml -->

## 衍生信號的用途

在[!DNL Audience Manager]中，您可以在事件呼叫期間傳入至其他指定訊號或特徵的訊號（或特徵規則）之間建立關係。 例如，假設事件呼叫在由key-value [!DNL "product = new_car"](`https://<domain alias>/event?product=new_car`)組成的信號中傳遞。 [!DNL Audience Manager] 會將該訊號連接至使用工具建立的其他 [!UICONTROL derived signals] 人。雖然相關信號可以是您指定的任何鍵值，但在連結至已設為[!UICONTROL Trait Builder]規則的現有信號時，它們最有用。 例如，在下圖中，當使用者動作觸發[!DNL "product = new car"]訊號時，使用者也可符合目標鍵和值訊號所定義的特性。

![](assets/derived_signal_example.png)

## 導出信號的位置

從側欄導覽建立並管理&#x200B;**[!UICONTROL Tools > Derived Signals]**&#x200B;中的[!UICONTROL derived signals]。

## 建立派生信號{#create}

<!-- t_tb_create_derived.xml -->

要建立[!UICONTROL derived signal]:

1. 從[!UICONTROL Tools]菜單中選擇&#x200B;**[!UICONTROL Derived Signals]**。
1. 提供：
   * *（可選）* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 按一下 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>[!UICONTROL Source Key]、[!UICONTROL Source Value]、[!UICONTROL Target Key]和[!UICONTROL Target Value]欄位的字元限制為228個字元。

## 編輯派生信號{#edit}

<!-- t_tb_edit_derived.xml -->

要編輯[!UICONTROL derived signal]:

1. 將滑鼠指標暫留在訊號上，然後按一下&#x200B;**[!UICONTROL Edit]**。
2. 變更所需的程式碼、金鑰或值，然後按一下&#x200B;**[!UICONTROL Save]**。

## 刪除派生信號{#delete}

<!-- t_tb_delete_derived.xml -->

若要刪除[!UICONTROL derived signal]，請將滑鼠指標暫留在訊號上，然後按一下&#x200B;**[!UICONTROL Delete]**。
