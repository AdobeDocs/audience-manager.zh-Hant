---
description: 衍生訊號會根據網站訪客已看到的特徵，讓網站訪客符合其他特徵的資格。 換句話說，即使使用者以前從未看過新特徵，其他特徵資格也可能衍生自目前展現的特徵。
seo-description: 衍生訊號會根據網站訪客已看到的特徵，讓網站訪客符合其他特徵的資格。 換句話說，即使使用者以前從未看過新特徵，其他特徵資格也可能衍生自目前展現的特徵。
seo-title: 衍生訊號
solution: Audience Manager
title: 衍生訊號
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 特徵
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# 衍生訊號 {#derived-signals}

[!UICONTROL derived signal]會根據已看到的特徵，讓網站訪客符合其他特徵的資格。 換句話說，即使使用者以前從未看過新特徵，其他特徵資格也可能衍生自目前展現的特徵。

<!-- c_tb_derived_signal.xml -->

## 衍生訊號的用途

在[!DNL Audience Manager]中，您可以在對其他指定訊號或特徵進行事件呼叫期間傳入的訊號（或特徵規則）之間建立關係。 例如，假設事件呼叫傳入由鍵值[!DNL "product = new_car"](`https://<domain alias>/event?product=new_car`)組成的訊號。 [!DNL Audience Manager] 會將該訊號連結至使用工具建立的其 [!UICONTROL derived signals] 他。雖然相關聯的訊號可以是您指定的任何鍵值，但在連結至已設為[!UICONTROL Trait Builder]規則的現有訊號時，這些訊號最有用。 例如，在下圖中，當使用者動作觸發訊號[!DNL "product = new car"]時，該使用者也可符合目標索引鍵和值訊號所定義特徵的資格。

![](assets/derived_signal_example.png)

## 衍生訊號的位置

從側欄導覽中建立並管理&#x200B;**[!UICONTROL Tools > Derived Signals]**&#x200B;中的[!UICONTROL derived signals]。

## 建立衍生訊號 {#create}

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

## 編輯衍生訊號 {#edit}

<!-- t_tb_edit_derived.xml -->

要編輯[!UICONTROL derived signal]:

1. 將滑鼠指標暫留在訊號上，然後按一下&#x200B;**[!UICONTROL Edit]**。
2. 變更所需的程式碼、索引鍵或值，然後按一下&#x200B;**[!UICONTROL Save]**。

## 刪除衍生訊號 {#delete}

<!-- t_tb_delete_derived.xml -->

若要刪除[!UICONTROL derived signal]，請將滑鼠指標暫留在訊號上，然後按一下&#x200B;**[!UICONTROL Delete]**。
