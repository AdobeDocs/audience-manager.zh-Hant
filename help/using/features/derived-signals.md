---
description: 衍生訊號會根據網站訪客已看到的特徵，讓他們符合其他特徵的資格。 換言之，即使使用者以前從未見過新特徵，也可從目前展示的特徵衍生出其他特徵資格。
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: 衍生訊號
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 衍生訊號 {#derived-signals}

[!UICONTROL derived signal]會根據網站訪客已看到的特徵，讓他們符合其他特徵的資格。 換言之，即使使用者以前從未見過新特徵，也可從目前展示的特徵衍生出其他特徵資格。

<!-- c_tb_derived_signal.xml -->

## 衍生訊號的用途

在[!DNL Audience Manager]中，您可以在事件呼叫其他指定訊號或特徵時傳入的訊號（或特徵規則）之間建立關聯性。 例如，假設事件呼叫傳入由機碼值[!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`)組成的訊號。 [!DNL Audience Manager]會將該訊號連線到使用[!UICONTROL derived signals]工具建立的任何其他訊號。 雖然關聯的訊號可以是您指定的任何機碼值，但是當連結到已設定為[!UICONTROL Trait Builder]規則的現有訊號時，這些訊號最有用。 例如，在下圖中，當使用者動作引發訊號[!DNL "product = new car"]時，使用者也可以符合目標索引鍵和值訊號所定義的特徵。

![](assets/derived_signal_example.png)

## 衍生訊號的位置

從側欄導覽在&#x200B;**[!UICONTROL Tools > Derived Signals]**&#x200B;中建立和管理[!UICONTROL derived signals]。

## 建立衍生訊號 {#create}

<!-- t_tb_create_derived.xml -->

若要建立[!UICONTROL derived signal]：

1. 從[!UICONTROL Tools]功能表選取&#x200B;**[!UICONTROL Derived Signals]**。
1. 提供：
   * *（選擇性）* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 按一下 **[!UICONTROL Add Signal]**。

>[!NOTE]
>
>[!UICONTROL Source Key]、[!UICONTROL Source Value]、[!UICONTROL Target Key]和[!UICONTROL Target Value]欄位的字元限製為228個字元。

## 編輯衍生訊號 {#edit}

<!-- t_tb_edit_derived.xml -->

若要編輯[!UICONTROL derived signal]：

1. 將游標暫留在訊號上，然後按一下&#x200B;**[!UICONTROL Edit]**。
2. 進行必要的程式碼、索引鍵或值變更，然後按一下&#x200B;**[!UICONTROL Save]**。

## 刪除衍生訊號 {#delete}

<!-- t_tb_delete_derived.xml -->

若要刪除[!UICONTROL derived signal]，請將游標停留在訊號上，然後按一下&#x200B;**[!UICONTROL Delete]**。
