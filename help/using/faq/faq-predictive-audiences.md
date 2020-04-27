---
description: Predictive Audiences可協助您使用資料科學，將未知的受眾即時分類為不同的角色。
seo-description: Predictive Audiences可協助您使用資料科學，將未知的受眾即時分類為不同的角色。
seo-title: 預測性受眾常見問答集
solution: Audience Manager
title: Audience Manager預測性觀眾
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# 預測性受眾常見問答集

常見的問題 [!UICONTROL Predictive Audiences]。

 

**我何時應[!UICONTROL Predictive Audiences]該使用[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] 提供 [!UICONTROL Look-alike modeling] 不同的使用案例。 這兩種算法的主要差異如下：

1. [!UICONTROL Look-alike modeling] 以小眾作為輸入，並加以擴充。 [!UICONTROL Predictive Audiences] 以大型受眾為輸入，並將其劃分為由您的角色定義的較小不同受眾。
1. 每個演算法的基本區段數不同。 [!UICONTROL Predictive Audiences] 至少需要兩個基線，而最 [!UICONTROL Look-alike modeling] 多使用一個基線。
1. [!UICONTROL Predictive Audiences] 執行即時區段評估，但不 [!UICONTROL Look-alike modeling] 執行。

根據您的使用案例，您應決定與您更相關的模型。

您可以將建立具有多個基準的模型 [!UICONTROL Predictive Audiences] ，視為建立相同數量的相似模型，而不需進行即時評估，而且訪客很有可能屬於多個不同角色，而非一個不同的角色。

 

**我可以建立多少個角色／模型？**

您最多可建立10種 [!UICONTROL Predictive Audiences] 模型。 對於每個模型，您最多可以定義50個基線特徵或區段。

 

**如何從區段建立新區[!UICONTROL Predictive Audiences]段？**

前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**，然後按一下資 **[!UICONTROL Predictive Audiences]** 料夾。 尋找所需的區段、複製區段，然後根據您的需求進行編輯。

 

**為什麼我的訪客沒有分類？**

目前，對象分類僅適用於即時資格，但已驗證的使用者則定義為其中一部分的使用者除外 [!UICONTROL Profile Merge Rules]。

未來的更新將會新增已登入資料的完整支援。

 

**我何時才能看到模型產生的第一個結果？**

[!UICONTROL Predictive Audiences] 如果模型成功運行，則模型結果可在建立模型後24小時內獲得。

若模型未在24小時內產生結果，請聯絡您的Adobe代表。

 

**為什麼我的模型沒有產生結果或顯示警告狀態？**

[!UICONTROL Predictive Audiences] 模型可能由於以下幾個原因而無法產生結果：

1. 所有選取的人格特徵／群體都沒有足夠的使用者設定檔。 我們建議您選擇特徵或群體，以便每個角色至少擁有幾百個使用者個人檔案。
1. 所有選取的個人特徵／群體在其使用者描述檔中都沒有足夠的資料（沒有足夠的特徵可以分析）。
1. 過去30天內，目標讀者特徵／區段沒有任何作用中或已登入的使用者。
1. 過去30天內處於活動狀態或已登入的目標對象使用者，其使用者設定檔中的資料不夠（沒有足夠的特徵可以分析）。

為了產生相關結果， [!UICONTROL Predictive Audiences] 算法根據DCS所看到的即時使用者活動來評估特徵和分段實現。 如果您選取的新基本特徵和群體尚未擁有足夠的使用者，演算法可能需要數天的時間來分類您的觀眾。

為獲得最佳結果，請遵循「角色的選 [擇准則」和「目標對象](../features/algorithmic-models/predictive-audiences.md#selection-personas)[的選擇准則」中的建議准則](../features/algorithmic-models/predictive-audiences.md#selection-audience)。

 

**我的模型為何顯示「錯誤」狀態？**

模型無法運行。 在此情況下，請聯絡您的Adobe代表。

 

**如何變更「預測性對象」區段的描述檔合併規則？**

複製 [!UICONTROL Predictive Audiences] 區段並變更復 [!UICONTROL Profile Merge Rule] 制區段的。

 

**目標對象中不屬於任何角色特徵／群體的使用者是否不可分類？**

是的，萬一使用者在個人檔案中沒有任何特徵。 在這種情況下，使用者將獲得所有人格特徵／區段的比對分數0，因此不會分類為任何預測性區段。

 

**分類為其中一個預測區段的使用者是否可重新分類為不同[!UICONTROL Predictive Audiences]區段？**

是。由於演算法是每日訓練的，因此會在特徵分數方面套用每個角色的變更。 如果屬於區段的使用者 [!UICONTROL Predictive Audiences] 處於作用中狀態，其特徵分數的變更可以根據過去30天的活動來變更分類。

 

**我是否可檢視哪些對象分類是依據哪些特徵？**

是的，您可以在模型報告頁面中查看所有基線的所有影響特徵。 請參 [閱影響特徵](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**如果我編輯其中一個基線特徵或區段，模型會如何？**

模型會評估一天一次特徵或區段。 您應會在更新後的第二天看到更新的分類。

 

**我是否可選擇模型將學習的資料來源？**

否，不支援選取資料來源。 演算 [!UICONTROL Predictive Audiences] 法會從您的所有第一方特徵中學習。