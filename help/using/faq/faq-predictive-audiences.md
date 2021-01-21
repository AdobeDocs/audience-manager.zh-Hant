---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾常見問題集
solution: Audience Manager
title: Audience Manager 預測受眾
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: c2c392b1201b5de08a3f4d58bbb7be5ef31545d0
workflow-type: tm+mt
source-wordcount: '968'
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

1. 所有選定的角色[!UICONTROL traits] / [!UICONTROL segments]都沒有足夠的用戶配置檔案。 我們建議您選擇[!UICONTROL traits]或[!UICONTROL segments]，以便每個角色至少擁有幾百個用戶配置檔案。
1. 選取的角色[!UICONTROL traits] / [!UICONTROL segments]在其使用者設定檔中沒有足夠的資料（沒有足夠的特徵可以分析）。
1. 目標讀者特徵／群體沒有任何作用中或已登入的使用者。
1. 過去 30 天內處於作用中狀態或已上線的目標受眾使用者，其使用者設定檔中的資料不足 (沒有足夠的特徵可進行分析)。
1. 目標對象區段使用與您為模型選擇的[!UICONTROL Profile Merge Rule]不同的。
1. 您為模型選擇的[!UICONTROL Profile Merge Rule]中，可能不包含目標對象特徵的資料來源。

為獲得最佳結果，請遵循[角色選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目標受眾選擇標準](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建議准則。

 

**為什麼我的模型顯示 [!UICONTROL Error] 狀態？**

模型無法執行。在此情況下，請聯絡您的[!DNL Adobe]代表。

 

**我要如何變 [!UICONTROL Profile Merge Rule] 更 [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

選取與先前模型相同的角色和目標對象，以建立新模型。 在建立模型期間，指定不同的[!UICONTROL Profile Merge Rule]。

>[!WARNING]
> 或者，您可以使用[區段產生器](../features/segments/segment-builder.md)手動建立具有現有預測性[!UICONTROL trait]的[!UICONTROL segment]，並指派您選擇的[!UICONTROL Profile Merge Rule]。
> 
> 但是，我們不建議這種做法，因為預測性[!UICONTROL traits]會自動繼承其所屬模型的[!UICONTROL Profile Merge Rule]，而且它們是根據符合模型[!UICONTROL Profile Merge Rule]的有影響的[!UICONTROL traits]建立的。

 

**我應 [!UICONTROL Profile Merge Rule] 該選擇什麼？**

為模型選擇[!UICONTROL Profile Merge Rule]時，請仔細分析使用案例。

假設您的目標對象[!UICONTROL segment]使用基於已驗證的配置檔案+ [!DNL Device Graph]配置檔案的[!UICONTROL Profile Merge Rule]，並且您為預測性[!UICONTROL segments]選擇了相同的[!UICONTROL Profile Merge Rule]。 在這種情況下，設備級別和跨設備級別[!UICONTROL traits]都將用於培訓模型以及將用戶放置到預測性[!UICONTROL segment]中。

但是，如果您只根據裝置設定檔選取[!UICONTROL Profile Merge Rule]，則跨裝置[!UICONTROL traits]將不會發揮任何影響力，而且不會對將使用者放置在預測性[!UICONTROL segment]中有任何貢獻。 這可能會對模型的精確度和觸及度產生負面影響。

仔細分析您的使用案例，並決定您希望模型學習的[!UICONTROL trait]類型，以及您希望模型用於分類的資料類型。

**目標受眾中不屬於任何角色特徵/區段的使用者是否不可分類？**

是的，萬一使用者的個人檔案中沒有任何特徵，在這種情況下，使用者的所有角色特徵/區段比對分數將為 0，因此不會分類為任何預測區段。

 

**分類為其中一個預測區段的使用者是否可重新分類為不同 [!UICONTROL Predictive Audiences] 區段？**

是。由於演算法每天都在學習並進步，因此會將變更套用到每個角色的特徵分數上。如果屬於某個 [!UICONTROL Predictive Audiences] 區段的使用者處於作用中狀態，其特徵分數的變化可根據過去 30 天的活動來變更分類。

 

**我是否可檢視哪些受眾分類是依據哪些特徵？**

是的，您可以在模型報表頁面中查看所有基線的所有具影響力的特徵。請參閱[具影響力的特徵](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**我是否可以變更預測性狀的存留時間(TTL)?**

預測性狀TTL設定為0（存留期），無法變更。 [!UICONTROL Predictive Audiences] 只有當使用者符合基本區段的資格或重新分類至不同的預測區段時，才能將其從預測區段中取消分段。

如有需要，您可以建立新區段來處理此功能，該區段同時包含具有指定TTL的預測性特徵和活動特性。

 


**如果編輯其中一個基線特徵或區段，模型會發生什麼事？**

模型一天會評估一次特徵或區段。您應會在做出更新後的隔天看到更新的分類。

 

**我是否可選擇模型要向哪個資料來源學習？**

否，不支援選取資料來源。[!UICONTROL Predictive Audiences] 演算法會向您的所有第一方特徵學習。