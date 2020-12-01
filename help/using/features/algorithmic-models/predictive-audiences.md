---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾概述
solution: Audience Manager
title: Audience Manager 預測受眾
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 協助您使用進階的資料科學技術，將未知的受眾即時分類為不同的角色。

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

 在行銷環境中，角色是一種受眾區段，由擁有一組共同特定特徵 (例如人口統計、瀏覽習慣、購物記錄等) 的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型可讓您使用 Audience Manager 的機器學習功能，將未知的受眾分類為不重複角色，進一步運用此概念。Audience Manager 可協助您針對一組已知的第一方受眾，計算未知第一方受眾的傾向，進而實現此目標。

當您建立[!UICONTROL Predictive Audiences]模型時，第一步是選擇您希望目標對象分類的基準特徵或區段。 這些特徵或群體將定義您的角色。

在評估階段，模型會針對您定義為基準的每個特徵或區段建立新的[!UICONTROL Predictive Audiences]區段。 下次Audience Manager從目標對象看到未分類為人物的訪客（不符合任何基準特徵或區段的資格）時，[!UICONTROL Predictive Audiences]模型將決定訪客應屬於哪個預測區段，並將訪客新增至該區段。

您可以在[!UICONTROL Segments]頁面中識別模型建立的預測性區段。 每個[!UICONTROL Predictive Audiences]模型在[!UICONTROL Predictive Audiences]資料夾下都有其自己的資料夾，按一下模型資料夾可查看每個模型的段。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 使用個案 {#use-cases}

為協助您更清楚瞭解如何使用[!UICONTROL Predictive Audiences]，以下是Audience Manager客戶可使用此功能解決的一些使用案例。

### 使用案例#1

身為電子商務公司的行銷人員，我想將所有的網路和行動訪客分類為不同的品牌相似性類別，以便個人化其使用者體驗。

### 使用案例#2

身為媒體公司的行銷人員，我想依照最愛的類型，將未驗證的網路和行動訪客分類，以便我建議他們透過所有通道提供個人化內容。

### 使用案例#3

身為航空公司的廣告商，我想確定我會根據受眾對旅遊目的地的興趣來分類受眾，以便在短暫的重新定位視窗中即時向受眾發佈廣告。

### 使用案例#4

身為廣告商，我想即時將第一方受眾分類，以便對趨勢新聞做出快速反應。

### 使用案例#5

身為行銷人員，我想預測我的網站訪客所處的客戶歷程階段，例如發現、參與、購買或保留，以便我能夠據以鎖定他們。

### 使用案例#6

身為媒體公司，我想將受眾分類，以便以優惠價格銷售廣告空間，同時為訪客提供相關廣告。

## [!UICONTROL Predictive Audiences]模型如何運作{#how-predictive-audiences-models-work}

建立[!UICONTROL Predictive Audiences]模型時，需要執行三個步驟：

1. 首先，您至少選取兩個特徵或兩個區段來定義您的角色。
1. 然後，您選擇一個特徵或群體，以定義您要分類的目標對象。
1. 最後，您為模型選擇名稱、儲存預測性區段的資料來源，以及模型的[!UICONTROL Profile Merge Rule]。

### 角色選擇標準{#selection-personas}

您可以選擇任何第一方特徵或群體來定義您的角色。 不過，為獲得最佳結果，以下是一組建議的最佳實務：

* 選擇您的角色特徵或群體，使每個角色至少擁有幾百個[設備ID](../../reference/ids-in-aam.md)。
* 如果您的特徵是以[跨裝置ID](../../reference/ids-in-aam.md)為基礎，則可以使用[裝置ID](../../reference/ids-in-aam.md)的[描述檔合併規則](../profile-merge-rules/merge-rules-overview.md)將其包住區段，例如[!UICONTROL Device Graph]。 這可確保有足夠的[裝置ID(a1/>)可供演算法學習。](../../reference/ids-in-aam.md)
* 我們建議您為個人選擇特徵或簡單區段，由1到3個特徵組成。
* 選擇重疊最小的基線特徵或區段。
* 請確定您正在擷取數位屬性中的細微特徵。

### 目標對象的選擇標準{#selection-audience}

視您的使用案例而定，不論您是要即時、批次或兩者皆要分類使用者，請選擇具有大量即時和／或總人口的目標對象（[!UICONTROL trait]或[!UICONTROL segment]）。 與人物角色選擇類似，我們建議您的目標對象[!UICONTROL trait]或[!UICONTROL segment]有擁有豐富設定檔的使用者（[!UICONTROL traits]的豐富集）。

選取目標對象時，請分析您的使用案例，並決定您要分類的ID類型：[!UICONTROL device IDs]或[!UICONTROL cross-device IDs]。 在建立模型時選擇的[!UICONTROL Profile Merge Rule]定義了將每個用戶放置到預測性[!UICONTROL segments]中的資料。

建議您選擇與目標對象[!UICONTROL Profile Merge Rule]具有相同設定的[!UICONTROL Profile Merge Rule]，或選擇包含目標對象的描述檔類型（裝置描述檔或已驗證的描述檔）的&lt;a0/>。

### [!UICONTROL Predictive Audiences] 模型培訓階段  {#model-training}

在演算法將您的第一方受眾分類為適當角色之前，它必須先針對您的資料進行自我訓練。

對於您定義的每個角色，演算法會分析其個別對象，並評估其使用者在過去30天內的任何即時和／或已登入特徵活動。
此步驟每24小時進行一次，以說明您第一方受眾的變更。

### [!UICONTROL Predictive Audiences] 模型分類階段  {#model-classification}

對於即時和批次對象分類，模型會先檢查使用者是否屬於目標對象。 如果使用者符合目標對象的資格且不屬於任何角色，模型會為其指派個人資格分數。

在評估第一方對象及指派分數時，模型會使用您帳戶中定義的預設&#x200B;**[!UICONTROL Profile Merge Rule]**。 最後，訪客被分類為獲得最高分的人物。

![預測對象圖](assets/predictive-audiences-graph.png)

## 注意事項和限制{#considerations}

>[!IMPORTANT]
> 請仔細閱讀本節內容，然後再轉至實施階段。

配置[!UICONTROL Predictive Audiences]型號時，請記住以下注意事項和限制：

* 您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。
* 對於每個模型，您最多可以選擇50個基本特徵／區段。
* [!UICONTROL Predictive Audiences]目前不支援第二方和第三方資料。
* [!UICONTROL Predictive Audiences] 從所有第一方資料來源，根據您的第一方特徵執行對象分類。
* [!UICONTROL Predictive Audiences]的區段評估使用在建立模型期間選擇的&#x200B;**[!UICONTROL Profile Merge Rule]**。 若要進一步瞭解[!UICONTROL Profile Merge Rules]，請參閱專屬的[說明檔案](../profile-merge-rules/merge-rules-overview.md)。
* 部分特徵和區段不支援做為基準或目標對象。 [!UICONTROL Predictive Audiences] 當選擇下列其中一項作為基準或目標對象時，模型將無法保存：
   * 預測性特徵和使用預測性特徵建立的群體；
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform特徵或細分；
   * 算法特徵；
   * 第二方和第三方特徵。
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 無法用於 [!UICONTROL Audience Lab]。

## [!UICONTROL Data Export Controls] {#dec}

由[!UICONTROL Predictive Audiences]模型建立的預測性區段會繼承[資料匯出控制](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)的下列第一方資料來源：

1. 建立模型時您選擇的第一方資料來源。
1. 目標對象的第一方資料來源。 具體來說，是構成目標對象的[!UICONTROL traits]或[!UICONTROL segments]的資料匯出控制項。
1. 為模型選擇的[!UICONTROL Profile Merge Rule][資料導出控制](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。

新建立的預測性[!UICONTROL traits]和[!UICONTROL segments]將具有與上述第一方資料來源的合併相同的隱私權限制。

具有不屬於[!UICONTROL Predictive Audiences]區段隱私權限制之其他限制的特性將會排除在培訓階段之外，不會對模型產生影響。

## [!UICONTROL Profile Merge Rules] {#pmr}

所有預測性區段都會指派您在建立模型時選取的[!UICONTROL Profile Merge Rule]。 您選擇的[!UICONTROL Profile Merge Rule]很重要，原因如下：

* 它定義當模型分析影響[!UICONTROL traits]時，在將用戶分類為預測[!UICONTROL segment]時，應考慮哪些設備和／或已驗證的配置檔案。
* 它規範在模型培訓步驟中應使用[!UICONTROL trait]類型（裝置層級或跨裝置層級），並呈現為具影響力的[!UICONTROL traits]。 預測[!UICONTROL segments]是目標對象的子集。
   * 如果目標對象是群體，建議您為模型選取與指派給目標對象的模型相同的[!UICONTROL Profile Merge Rule]，或是包含目標對象的描述檔類型的[!UICONTROL Profile Merge Rule]。
   * 如果目標對象為[!UICONTROL trait]，建議您選取[!UICONTROL Profile Merge Rule]，以存取與目標對象特徵（裝置描述檔資料或跨裝置描述檔資料）相同的資料類型。
* [!UICONTROL Profile Merge Rules] 使用 [!UICONTROL Current Authenticated Profiles] 和 [!UICONTROL No Device Profile] 選項僅支援即時對象分類。有關詳細資訊，請參閱[配置檔案合併規則選項定義](../profile-merge-rules/merge-rule-definitions.md)。

選擇同時使用裝置資料和跨裝置資料的[!UICONTROL Profile Merge Rule]，可將用於模型訓練和使用者分類的[!UICONTROL traits]數量最多化為預測性[!UICONTROL segments]。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您為角色和對象分類選擇的特徵和區段受Audience Manager [角色型存取控制](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)的規範。

Audience Manager使用者只能為角色和目標對象選取其擁有[檢視權限](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)的特徵或區段。
