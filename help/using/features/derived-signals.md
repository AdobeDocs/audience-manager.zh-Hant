---
description: 衍生的信號會根據訪客已看過的特徵，使網站訪客符合其他特徵。換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-description: 衍生的信號會根據訪客已看過的特徵，使網站訪客符合其他特徵。換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。
seo-title: 衍生訊號
solution: Audience Manager
title: 衍生訊號
uuid: e52600e3-26d1-4607-9b96-afd6086 a252 d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Derived Signals {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they've already seen. 換言之，即使使用者從未看過新特徵，也可以從目前展示的特徵衍生其他特徵資格。

<!-- c_tb_derived_signal.xml -->

## 衍生訊號的用途

In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] 會將該訊號連接至使用 [!UICONTROL derived signals] 工具建立的任何其他人。Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## 衍生訊號的位置

[!UICONTROL derived signals]**[!UICONTROL Tools > Derived Signals]** 從側邊欄導覽建立及管理。

## Create a Derived Signal {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. 提供a：
   * *(可選)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Click **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>[!UICONTROL Source Key][!UICONTROL Source Value]、 [!UICONTROL Target Key][!UICONTROL Target Value] 和欄位的字元限制為228字元。

## Edit a Derived Signal {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Hover over the signal, then click **[!UICONTROL Edit]**.
2. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.

## Delete a Derived Signal {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.
