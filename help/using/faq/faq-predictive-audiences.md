---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾常見問題集
solution: Audience Manager
title: Audience Manager 預測受眾
translation-type: ht
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb
workflow-type: ht
source-wordcount: '773'
ht-degree: 100%

---


# 預測受眾常見問題集

關於 [!UICONTROL Predictive Audiences] 的常見問題集。

 

**我何時應使用[!UICONTROL Predictive Audiences]而非[!UICONTROL Look-alike modeling]？**

[!UICONTROL Predictive Audiences] 和 [!UICONTROL Look-alike modeling] 運用在不同的使用案例。這兩種演算法的主要差異如下：

1. [!UICONTROL Look-alike modeling] 以小型受眾作為輸入，並加以擴充。[!UICONTROL Predictive Audiences] 以大型受眾作為輸入，並將其劃分為由您的角色定義的較小不重複受眾。
1. 每個演算法的基本區段數不同。[!UICONTROL Predictive Audiences] 至少需要兩個基線，而最 [!UICONTROL Look-alike modeling] 多使用一個基線。
1. [!UICONTROL Predictive Audiences] 執行即時區段評估，但 [!UICONTROL Look-alike modeling] 不執行。

您應根據您的使用案例，決定相關度較高的模型。

您可以將建立含有多個基線的 [!UICONTROL Predictive Audiences] 模型視為等同於建立相同數量的相似模型，差別在於不需進行即時評估，而且訪客很有可能屬於多個不重複角色，而非一個不重複角色。

 

**我可以建立多少個角色/模型？**

您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。針對每個模型，您最多可定義 50 個基線特徵或區段。

 

**如何從[!UICONTROL Predictive Audiences]區段建立新區段？**

前往「**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**」，然後按一下 **[!UICONTROL Predictive Audiences]** 資料夾。找到所需的區段，複製該區段，然後根據您的需求加以編輯。

 

**為什麼我的已上線訪客沒有進行分類？**

目前受眾分類僅適用於即時資格，但定義為 [!UICONTROL Profile Merge Rules] 其中一部分的已驗證使用者除外。

未來的更新將會新增對已上線資料的完整支援。

 

**何時才能看到模型產生的第一個結果？**

如果模型成功運作，可在建立模型後 24 小時內取得 [!UICONTROL Predictive Audiences] 模型結果。

若模型沒有在 24 小時內產生結果，請洽詢您的 Adobe 代表。

 

**為什麼我的模型沒有產生結果或顯示警告狀態？**

[!UICONTROL Predictive Audiences] 模型可能由於以下幾個原因而無法產生結果：

1. 所有選取的角色特徵/區段都沒有足夠的使用者設定檔。建議您選擇特徵或區段，讓每個角色至少擁有幾百個使用者個人檔案。
1. 所選的角色特徵/區段之使用者設定檔中的資料不足 (沒有足夠的特徵可進行分析)。
1. 過去 30 天內，目標受眾特徵/區段沒有任何作用中或已上線的使用者。
1. 過去 30 天內處於作用中狀態或已上線的目標受眾使用者，其使用者設定檔中的資料不足 (沒有足夠的特徵可進行分析)。

為了產生相關結果，[!UICONTROL Predictive Audiences] 演算法會根據 DCS 觀察到的即時使用者活動來評估特徵和區段實現。如果您選取的新基本特徵和區段尚未擁有足夠的使用者，那麼演算法可能需要數天時間才能將您的受眾分類。

為獲得最佳結果，請遵循[角色選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目標受眾選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建議准則。

 

**我的模型為何顯示「錯誤」狀態？**

模型無法執行。在這種情況下，請洽詢您的 Adobe 代表。

 

**如何變更預測受眾區段的設定檔合併規則？**

複製 [!UICONTROL Predictive Audiences] 區段並變更所複製區段的[!UICONTROL Profile Merge Rule]。

 

**目標受眾中不屬於任何角色特徵/區段的使用者是否不可分類？**

是的，萬一使用者的個人檔案中沒有任何特徵，在這種情況下，使用者的所有角色特徵/區段比對分數將為 0，因此不會分類為任何預測區段。

 

**分類為其中一個預測區段的使用者是否可重新分類為不同[!UICONTROL Predictive Audiences]區段？**

是。由於演算法每天都在學習並進步，因此會將變更套用到每個角色的特徵分數上。如果屬於某個 [!UICONTROL Predictive Audiences] 區段的使用者處於作用中狀態，其特徵分數的變化可根據過去 30 天的活動來變更分類。

 

**我是否可檢視哪些受眾分類是依據哪些特徵？**

是的，您可以在模型報表頁面中查看所有基線的所有具影響力的特徵。請參閱[具影響力的特徵](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**如果編輯其中一個基線特徵或區段，模型會發生什麼事？**

模型一天會評估一次特徵或區段。您應會在做出更新後的隔天看到更新的分類。

 

**我是否可選擇模型要向哪個資料來源學習？**

否，不支援選取資料來源。[!UICONTROL Predictive Audiences] 演算法會向您的所有第一方特徵學習。