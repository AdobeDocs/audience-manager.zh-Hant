---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: 預測受眾常見問題集
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 59%

---

# 預測受眾常見問題集

關於 [!UICONTROL Predictive Audiences] 的常見問題集。

 

**我何時應使用 [!UICONTROL Predictive Audiences] 而非 [!UICONTROL Look-alike modeling]？**

[!UICONTROL Predictive Audiences] 和 [!UICONTROL Look-alike modeling] 運用在不同的使用案例。這兩種演算法的主要差異如下：

1. [!UICONTROL Look-alike modeling] 以小型受眾作為輸入，並加以擴充。[!UICONTROL Predictive Audiences] 以大型受眾作為輸入，並將其劃分為由您的角色定義的較小不重複受眾。
1. 每個演算法的基本區段數不同。[!UICONTROL Predictive Audiences] 至少需要兩個基線，而最 [!UICONTROL Look-alike modeling] 多使用一個基線。
1. [!UICONTROL Predictive Audiences] 執行即時區段評估，但 [!UICONTROL Look-alike modeling] 不執行。

您應根據您的使用案例，決定相關度較高的模型。

您可以將建立含有多個基線的 [!UICONTROL Predictive Audiences] 模型視為等同於建立相同數量的相似模型，差別在於不需進行即時評估，而且訪客很有可能屬於多個不重複角色，而非一個不重複角色。

 

**我可以建立多少個角色/模型？**

您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。針對每個模型，您最多可定義 50 個基線特徵或區段。

 

**如何從 [!UICONTROL Predictive Audiences] 區段建立新區段？**

前往「**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**」，然後按一下 **[!UICONTROL Predictive Audiences]** 資料夾。找到所需的區段，複製該區段，然後根據您的需求加以編輯。

 

**何時才能看到模型產生的第一個結果？**

如果模型成功運作，可在建立模型後 24 小時內取得 [!UICONTROL Predictive Audiences] 模型結果。

若模型沒有在 24 小時內產生結果，請洽詢您的 Adobe 代表。

 

**為什麼我的模型沒有產生結果或顯示警告狀態？**

[!UICONTROL Predictive Audiences] 模型可能由於以下幾個原因而無法產生結果：

1. 未選擇任何選定角色 [!UICONTROL traits] / [!UICONTROL segments] 擁有足夠的用戶配置檔案。 我們建議您 [!UICONTROL traits] 或 [!UICONTROL segments] 使每個角色至少擁有幾百個用戶配置檔案。
1. 未選擇任何選定角色 [!UICONTROL traits] / [!UICONTROL segments] 在其用戶配置檔案中擁有足夠的資料（沒有足夠的特徵進行分析）。
1. 目標受眾特性/段沒有任何活動用戶或已掛接用戶。
1. 過去 30 天內處於作用中狀態或已上線的目標受眾使用者，其使用者設定檔中的資料不足 (沒有足夠的特徵可進行分析)。
1. 目標受眾段使用不同的 [!UICONTROL Profile Merge Rule] 從你為模型選的那個。
1. 您的目標受眾特徵的資料源可能未包含在 [!UICONTROL Profile Merge Rule] 你為模型選的。

為獲得最佳結果，請遵循[角色選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目標受眾選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建議准則。

 

**為什麼我的模特 [!UICONTROL Error] 狀態？**

模型無法執行。在這種情況下，請聯繫 [!DNL Adobe] 代表。

 

**如何更改 [!UICONTROL Profile Merge Rule] 為 [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

通過選擇與上一個模型相同的角色和目標受眾來建立新模型。 在建立模型期間，指定不同的 [!UICONTROL Profile Merge Rule]。

>[!WARNING]
> 或者，您可以 [段生成器](../features/segments/segment-builder.md) 手動建立 [!UICONTROL segment] 具有現有預測 [!UICONTROL trait] 並指定 [!UICONTROL Profile Merge Rule] 你選擇的。
> 
> 但是，我們不推薦這種做法，因為 [!UICONTROL traits] 自動繼承 [!UICONTROL Profile Merge Rule] 他們所屬的模型，是由 [!UICONTROL traits] 符合 [!UICONTROL Profile Merge Rule] 模型。

 

**什麼 [!UICONTROL Profile Merge Rule] 我該選嗎？**

選擇 [!UICONTROL Profile Merge Rule] 對於模型，仔細分析使用案例。

假設你的目標受眾 [!UICONTROL segment] 使用 [!UICONTROL Profile Merge Rule] 基於經過驗證的配置檔案+ [!DNL Device Graph] 配置式，並選擇相同 [!UICONTROL Profile Merge Rule] 用於預測 [!UICONTROL segments]。 在這種情況下，設備級和跨設備級 [!UICONTROL traits] 將用於訓練模型和將用戶放置為預測 [!UICONTROL segment]。

但是，如果 [!UICONTROL Profile Merge Rule] 僅基於設備配置檔案，無跨設備 [!UICONTROL traits] 將會產生影響，不會有助於將用戶安排成預測性 [!UICONTROL segment]。 這可能會對模型的準確性和精度產生不利影響。

仔細分析您的使用案例並決定 [!UICONTROL trait] 希望模型學習的類型以及希望模型用於分類的資料類型。

**目標受眾中不屬於任何角色特徵/區段的使用者是否不可分類？**

是的，萬一使用者的個人檔案中沒有任何特徵，在這種情況下，使用者的所有角色特徵/區段比對分數將為 0，因此不會分類為任何預測區段。

 

**分類為其中一個預測區段的使用者是否可重新分類為不同 [!UICONTROL Predictive Audiences] 區段？**

是。由於演算法每天都在學習並進步，因此會將變更套用到每個角色的特徵分數上。如果屬於某個 [!UICONTROL Predictive Audiences] 區段的使用者處於作用中狀態，其特徵分數的變化可根據過去 30 天的活動來變更分類。

 

**我是否可檢視哪些受眾分類是依據哪些特徵？**

是的，您可以在模型報表頁面中查看所有基線的所有具影響力的特徵。請參閱[具影響力的特徵](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**是否可以更改預測性狀的生存時間(TTL)?**

預測特性TTL設定為0（生存期），不能更改。 [!UICONTROL Predictive Audiences] 只有當用戶符合基本段或被重新分類到不同的預測段時，才能從預測段中取消分段。

如果需要，可以通過建立包含預測特性和具有指定TTL的活動特性的新段來處理此功能。

 


**如果編輯其中一個基線特徵或區段，模型會發生什麼事？**

模型一天會評估一次特徵或區段。您應會在做出更新後的隔天看到更新的分類。

 

**我是否可選擇模型要向哪個資料來源學習？**

否，不支援選取資料來源。[!UICONTROL Predictive Audiences] 演算法會向您的所有第一方特徵學習。
