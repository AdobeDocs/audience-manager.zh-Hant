---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾概述
solution: Audience Manager
title: Audience Manager 預測受眾
feature: 演算法模型
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 可協助您使用進階的資料科學技術，將未知的受眾即時分類為不重複角色。

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

 在行銷環境中，角色是一種受眾區段，由擁有一組共同特定特徵 (例如人口統計、瀏覽習慣、購物記錄等) 的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型可讓您使用 Audience Manager 的機器學習功能，將未知的受眾分類為不重複角色，進一步運用此概念。Audience Manager 可協助您針對一組已知的第一方受眾，計算未知第一方受眾的傾向，進而實現此目標。

建立[!UICONTROL Predictive Audiences]模型時，第一步是選取您要依目標對象分類的基線特徵或區段。 這些特徵或區段將定義您的角色。

在評估階段，模型會針對您定義為基線的每個特徵或區段建立新的[!UICONTROL Predictive Audiences]區段。 下次Audience Manager看見來自您目標對象且未分類為角色（不符合任何基準特徵或區段的資格）的訪客時，[!UICONTROL Predictive Audiences]模型將決定訪客應屬於哪些預測區段，並將訪客新增至該區段。

您可以在[!UICONTROL Segments]頁面中識別模型建立的預測區段。 每個[!UICONTROL Predictive Audiences]模型在[!UICONTROL Predictive Audiences]資料夾下都有其自己的資料夾，按一下模型資料夾即可查看每個模型的段。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 使用個案 {#use-cases}

為協助您更清楚了解使用[!UICONTROL Predictive Audiences]的方式和時機，以下是Audience Manager客戶可透過使用此功能解決的一些使用案例。

### 使用案例#1

身為電子商務公司的行銷人員，我想將所有的網頁和行動訪客分類為各種品牌相關性類別，以便個人化其使用者體驗。

### 使用案例#2

身為媒體公司的行銷人員，我想依最喜愛的類型來分類未驗證的網頁和行動訪客，以便針對所有管道的個人化內容提出建議。

### 使用案例#3

身為航空公司的廣告商，我想確定我會根據對旅遊目的地的興趣來分類我的對象，以便在短時間的重新定位視窗內，即時向他們發佈廣告。

### 使用案例#4

身為廣告商，我想要即時分類第一方受眾，以便對趨勢新聞快速做出反應。

### 使用案例#5

身為行銷人員，我想預測我的網站訪客處於哪個客戶歷程階段，例如探索、參與、購買或保留，以便我可以據以鎖定他們。

### 使用案例#6

身為媒體公司，我想對我的受眾進行分類，以便以優惠價格銷售廣告空間，同時提供與訪客相關的廣告。

## [!UICONTROL Predictive Audiences]模型如何運作{#how-predictive-audiences-models-work}

建立[!UICONTROL Predictive Audiences]模型時，需執行三個步驟：

1. 首先，您至少選取兩個特徵或兩個區段來定義您的角色。
1. 接著，您會選取一個特徵或區段來定義您要分類的目標對象。
1. 最後，為模型選擇名稱、將儲存預測段的資料源，以及為模型選擇[!UICONTROL Profile Merge Rule]。

### 角色選擇標準{#selection-personas}

您可以選擇任何第一方特徵或區段來定義您的角色。 不過，為獲得最佳結果，以下是一組建議的最佳實務：

* 選擇您的角色特徵或區段，讓每個角色至少擁有幾百個[裝置ID](../../reference/ids-in-aam.md)。
* 如果您的特徵是以[跨裝置ID](../../reference/ids-in-aam.md)為基礎，您可以使用[使用[裝置ID](../../reference/ids-in-aam.md)的「設定檔合併規則」](../profile-merge-rules/merge-rules-overview.md)將其包裝在區段中，例如[!UICONTROL Device Graph]。 這可確保有足夠的[裝置ID](../../reference/ids-in-aam.md)供演算法學習。
* 建議您為角色選擇特徵或簡單區段，由1到3個特徵組成。
* 選擇重疊最小的基線特徵或區段。
* 請務必在數位屬性中擷取精細特徵。

### 目標對象的選擇標準{#selection-audience}

根據您的使用案例，無論您要以即時、批次或兩者來分類使用者，選擇具有大量即時和/或總母體的目標對象（[!UICONTROL trait]或[!UICONTROL segment]）。 與角色選取類似，我們建議您的目標對象[!UICONTROL trait]或[!UICONTROL segment]有具有豐富設定檔（[!UICONTROL traits]的豐富集）的使用者。

選取目標對象時，分析您的使用案例並決定要分類的ID類型：[!UICONTROL device IDs]或[!UICONTROL cross-device IDs]。 建立模型時您選取的[!UICONTROL Profile Merge Rule]會定義將用來將每個使用者放入預測[!UICONTROL segments]的資料。

建議您選擇與目標對象[!UICONTROL Profile Merge Rule]配置相同的[!UICONTROL Profile Merge Rule]，或包含目標對象的設定檔類型（裝置設定檔或已驗證的設定檔）的。

### [!UICONTROL Predictive Audiences] 模型訓練階段  {#model-training}

演算法必須先訓練資料本身，才能將第一方對象分類為正確的角色。

演算法會針對您定義的每個角色，分析其個別對象，並評估過去30天內使用者的任何即時和/或已上線特徵活動。
此步驟每24小時進行一次，以說明第一方對象中的變更。

### [!UICONTROL Predictive Audiences] 模型分類階段  {#model-classification}

對於即時和批次對象分類，模型會先檢查使用者是否屬於目標對象。 如果使用者符合目標對象的資格，且不屬於任何角色，模型會為他們指派角色資格分數。

評估第一方對象並指派分數時，模型會使用帳戶中定義的預設&#x200B;**[!UICONTROL Profile Merge Rule]**。 最後，訪客被分類為其獲得最高分數的角色。

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 考量事項和限制 {#considerations}

>[!IMPORTANT]
> 繼續進行實作階段之前，請仔細閱讀本節。

設定[!UICONTROL Predictive Audiences]模型時，請記住下列考量事項和限制：

* 您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。
* 對於每個模型，您最多可選擇50個基本特徵/區段。
* [!UICONTROL Predictive Audiences]中目前不支援第二方和第三方資料。
* [!UICONTROL Predictive Audiences] 從所有第一方資料來源，根據您的第一方特徵執行對象分類。
* [!UICONTROL Predictive Audiences]的區段評估使用建立模型期間您選擇的&#x200B;**[!UICONTROL Profile Merge Rule]**。 若要深入了解[!UICONTROL Profile Merge Rules]，請參閱專屬的[檔案](../profile-merge-rules/merge-rules-overview.md)。
* 有些特徵和區段不支援做為基線或目標對象。 [!UICONTROL Predictive Audiences] 選擇下列其中一個項目作為基線或目標對象時，模型將無法儲存：
   * 使用預測特徵建立的預測特徵和區段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 特徵或區段；
   * 演算法特徵；
   * 第二方和第三方特徵。
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 無法在中使 [!UICONTROL Audience Lab]用。

## [!UICONTROL Data Export Controls] {#dec}

由[!UICONTROL Predictive Audiences]模型建立的預測性區段會繼承下列第一方資料來源的[資料匯出控制項](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html):

1. 建立模型時您選擇的第一方資料來源。
1. 目標對象的第一方資料來源。 具體來說，是構成您目標對象的[!UICONTROL traits]或[!UICONTROL segments]資料匯出控制項。
1. 為模型選擇的[!UICONTROL Profile Merge Rule]的[資料導出控制項](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。

新建立的預測性[!UICONTROL traits]和[!UICONTROL segments]將與上述第一方資料來源的聯合具有相同的隱私權限制。

具有不屬於[!UICONTROL Predictive Audiences]區段隱私權限制之其他限制的特徵，將會從訓練階段中排除，且不會對模型產生影響。

## [!UICONTROL Profile Merge Rules] {#pmr}

建立模型時，所有預測區段都會獲派您選取的[!UICONTROL Profile Merge Rule]。 您選擇的[!UICONTROL Profile Merge Rule]非常重要，原因如下：

* 它定義當模型分析具影響力的[!UICONTROL traits]時，在將使用者分類為預測[!UICONTROL segment]時，應考慮哪些裝置和/或已驗證的設定檔。
* 它控制在模型訓練步驟期間應使用哪些[!UICONTROL trait]類型（裝置層級或跨裝置層級），並呈現為具影響力的[!UICONTROL traits]。 預測性[!UICONTROL segments]是目標對象的子集。
   * 如果目標對象是區段，建議您為模型選取與指派給目標對象的相同[!UICONTROL Profile Merge Rule]，或[!UICONTROL Profile Merge Rule]，其中包含目標對象的設定檔類型。
   * 如果目標對象為[!UICONTROL trait]，建議您選取[!UICONTROL Profile Merge Rule]，以存取與目標對象特徵（裝置設定檔資料或跨裝置設定檔資料）相同類型的資料。
* [!UICONTROL Profile Merge Rules] 只支 [!UICONTROL Current Authenticated Profiles] 援 [!UICONTROL No Device Profile] 使用和選項進行即時對象分類。如需詳細資訊，請參閱[定義的設定檔合併規則選項](../profile-merge-rules/merge-rule-definitions.md)。

選取同時使用裝置資料和跨裝置資料的[!UICONTROL Profile Merge Rule]，可將可用於模型訓練和使用者分類的[!UICONTROL traits]數量最大化，並放入預測[!UICONTROL segments]中。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您為角色和對象分類選擇的特徵和區段受Audience Manager[角色型存取控制](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)所限。

Audience Manager使用者只能為角色和目標對象選取特徵或區段，且他們有[檢視](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)的權限。
