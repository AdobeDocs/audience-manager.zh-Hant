---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager 預測受眾
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# [!UICONTROL Predictive Audiences]總覽 {#predictive-audiences}

[!UICONTROL Predictive Audiences]可協助您使用進階的資料科學技術，將未知的受眾即時分類為不重複角色。

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

在行銷領域中，角色是一種受眾區段，由擁有一組共同特定特徵（例如人口統計資料、瀏覽習慣、購物記錄等）的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型可讓您使用 Audience Manager 的機器學習功能，將未知的受眾分類為不重複角色，進一步運用此概念。Audience Manager可協助您針對一組已知的第一方受眾，計算未知第一方受眾的傾向，進而實現此目標。

建立[!UICONTROL Predictive Audiences]模型時，第一步是選擇基線特徵或區段，讓您的目標對象依這些特徵或區段進行分類。 這些特徵或區段將定義您的角色。

在評估階段，模型會為您定義為基準線的每個特徵或區段建立新的[!UICONTROL Predictive Audiences]區段。 下次Audience Manager看到目標受眾中未被分類為角色之訪客（不符合任何基線特徵或區段的資格）時，[!UICONTROL Predictive Audiences]模型會判斷訪客應屬於哪些預測區段，並將訪客新增至該區段。

您可以在[!UICONTROL Segments]頁面中識別模型建立的預測區段。 每個[!UICONTROL Predictive Audiences]模型在[!UICONTROL Predictive Audiences]資料夾下都有自己的資料夾，您可以按一下模型資料夾來檢視每個模型的區段。

![預測對象 — 區段](assets/predictive-audiences-segments.png)

## 使用個案 {#use-cases}

為了協助您更清楚瞭解您如何使用[!UICONTROL Predictive Audiences]以及何時可以使用，以下是Audience Manager客戶可以使用此功能解決的一些使用案例。

### 使用案例#1

身為電子商務公司的行銷人員，我想將所有網頁和行動訪客分類為各種品牌相關性類別，以便個人化其使用者體驗。

### 使用案例#2

身為一家媒體公司的行銷人員，我想要依我最愛的流派將我未經驗證的網頁和行動訪客分類，以便我可以跨所有管道向他們建議個人化內容。

### 使用案例#3

作為一家航空公司的廣告商，我想要確保我根據受眾對旅遊目的地的興趣來分類受眾，以便我可以在短短的重新定位時段內即時向他們做廣告。

### 使用案例#4

身為廣告商，我想即時分類第一方對象，以便快速回應熱門新聞。

### 使用案例#5

作為行銷人員，我想預測我的網站訪客處於哪個客戶歷程階段，例如探索、參與、購買或保留，以便我可以據此鎖定他們。

### 使用案例#6

身為一家媒體公司，我想將我的對象分類，這樣我就能以高價銷售廣告空間，同時為訪客提供相關的廣告。

## [!UICONTROL Predictive Audiences]模型的運作方式 {#how-predictive-audiences-models-work}

建立[!UICONTROL Predictive Audiences]模型時，您需要完成三個步驟：

1. 首先，您至少選取兩個特徵或兩個區段，以定義您的角色。
1. 接著，您可以選擇特徵或區段，定義您要分類的目標對象。
1. 最後，您要選擇模型的名稱、儲存預測區段的資料來源，以及模型的[!UICONTROL Profile Merge Rule]。

### 角色選取條件 {#selection-personas}

您可以選擇任何第一方特徵或區段來定義您的角色。 然而，為獲得最佳結果，以下是建議的一組最佳實務：

* 選擇您的角色特徵或區段，讓每個角色至少擁有幾百個[裝置ID](../../reference/ids-in-aam.md)。
* 如果您的特徵是以[跨裝置ID](../../reference/ids-in-aam.md)為基礎，您可以將其包裝在使用[裝置ID](../../reference/ids-in-aam.md)的[設定檔合併規則](../profile-merge-rules/merge-rules-overview.md)的區段中，例如[!UICONTROL Device Graph]。 這將確保有足夠的裝置ID[&#128279;](../../reference/ids-in-aam.md)可供演演算法學習。
* 我們建議您為角色選擇特徵或簡單區段，包含1到3個特徵。
* 選擇重疊程度最低的基線特徵或區段。
* 請務必在數位財產上擷取精細的特徵。

### 目標對象的選取條件 {#selection-audience}

視您的使用案例而定，若要以即時、批次，或兩者同時分類，請選擇具有大量即時和/或總母體的目標對象（[!UICONTROL trait]或[!UICONTROL segment]）。 與角色選擇類似，我們建議您的目標對象[!UICONTROL trait]或[!UICONTROL segment]具有具有豐富設定檔（[!UICONTROL traits]的豐富集合）的使用者。

選取目標對象時，請分析您的使用案例，並決定您要分類的ID型別： [!UICONTROL device IDs]或[!UICONTROL cross-device IDs]。 您在建立模型時選取的[!UICONTROL Profile Merge Rule]會定義用來將每個使用者放入預測性[!UICONTROL segments]的資料。

根據最佳實務，建議您選擇與目標對象[!UICONTROL Profile Merge Rule]具有相同設定的[!UICONTROL Profile Merge Rule]，或是包含目標對象的設定檔型別（裝置設定檔或已驗證的設定檔）的設定檔。

### [!UICONTROL Predictive Audiences]模型訓練階段 {#model-training}

演演算法必須先根據您的資料自我訓練，才能將第一方對象分類為正確的角色。

演演算法會針對您定義的每個角色，分析各自的對象，並評估其使用者在過去30天內任何即時和/或已上線特徵活動。
此步驟每24小時執行一次，以說明第一方對象中的變更。

### [!UICONTROL Predictive Audiences]模型分類階段 {#model-classification}

對於即時和批次對象分類，模型會先檢查使用者是否屬於目標對象。 如果使用者符合目標受眾資格且不屬於任何角色，模型會為其指派角色資格分數。

評估第一方對象並指派分數時，模型會使用您帳戶中定義的預設&#x200B;**[!UICONTROL Profile Merge Rule]**。 最後，訪客會分類為獲得最高分數的角色。

![預測對象 — 圖表](assets/predictive-audiences-graph.png)

## 考量事項和限制 {#considerations}

>[!IMPORTANT]
> 在進入實作階段之前，請仔細閱讀本節。

設定[!UICONTROL Predictive Audiences]模型時，請記住下列考量事項和限制：

* 您最多可以建立10個[!UICONTROL Predictive Audiences]模型。
* 對於每個模型，您最多可以選擇50個基本特徵/區段。
* [!UICONTROL Predictive Audiences]目前不支援第二方和第三方資料。
* [!UICONTROL Predictive Audiences]會根據您第一方特徵，從您所有第一方資料來源執行對象分類。
* [!UICONTROL Predictive Audiences]的區段評估使用您在模型建立期間選擇的&#x200B;**[!UICONTROL Profile Merge Rule]**。 若要深入瞭解[!UICONTROL Profile Merge Rules]，請參閱專屬的[檔案](../profile-merge-rules/merge-rules-overview.md)。
* 部分特徵和區段不支援作為基線或目標對象。 選擇下列其中一個做為基準或目標對象時，[!UICONTROL Predictive Audiences]模型將無法儲存：
   * 預測性特徵和使用預測性特徵建立的區段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md)特徵或區段；
   * 演演算法特徵；
   * 第二方和第三方特徵。
* [!UICONTROL Predictive Audience] [!UICONTROL segments]不能在[!UICONTROL Audience Lab]中使用。

## [!UICONTROL Data Export Controls] {#dec}

[!UICONTROL Predictive Audiences]模型建立的預測區段會繼承下列第一方資料來源的[資料匯出控制項](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)：

1. 您在建立模型時選擇的第一方資料來源。
1. 目標對象的第一方資料來源。 具體來說，就是組成您目標對象之[!UICONTROL traits]或[!UICONTROL segments]的資料匯出控制項。
1. 您為模型選取之[!UICONTROL Profile Merge Rule]的[資料匯出控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)。

新建立的預測性[!UICONTROL traits]和[!UICONTROL segments]將與上述第一方資料來源的聯合有相同的隱私許可權制。

具有不屬於[!UICONTROL Predictive Audiences]區段隱私許可權制之其他限制的特徵，將從訓練階段中排除，且不會影響模型。

## [!UICONTROL Profile Merge Rules] {#pmr}

所有預測區段都會指派給您建立模型時選取的[!UICONTROL Profile Merge Rule]。 您選擇的[!UICONTROL Profile Merge Rule]很重要，原因如下：

* 它定義在模型分析具影響力的[!UICONTROL traits]時，將使用者分類為預測性[!UICONTROL segment]時，應該考慮哪些裝置和/或驗證的設定檔。
* 它決定模型訓練步驟期間應該使用哪些[!UICONTROL trait]型別（裝置層級或跨裝置層級），並顯示為有影響力的[!UICONTROL traits]。 預測性[!UICONTROL segments]是目標對象的子集。
   * 如果目標對象是區段，我們建議您為模型選取與指派給目標對象相同的[!UICONTROL Profile Merge Rule]，或選取包含目標對象之設定檔型別的[!UICONTROL Profile Merge Rule]。
   * 如果目標對象是[!UICONTROL trait]，我們建議您選取一個可以存取與目標對象特徵相同資料型別的[!UICONTROL Profile Merge Rule] （裝置設定檔資料或跨裝置設定檔資料）。
* 使用[!UICONTROL Current Authenticated Profiles]和[!UICONTROL No Device Profile]選項的[!UICONTROL Profile Merge Rules]僅支援即時對象分類。 如需詳細資訊，請參閱[定義的設定檔合併規則選項](../profile-merge-rules/merge-rule-definitions.md)。

選取同時使用裝置資料與跨裝置資料的[!UICONTROL Profile Merge Rule]，可將可用於模型訓練與使用者分類的[!UICONTROL traits]數目增加到預測性[!UICONTROL segments]。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您為角色和對象分類選擇的特徵和區段須遵守Audience Manager[角色型存取控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)。

Audience Manager使用者只能選取其具有[檢視](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)許可權之角色和Target對象的特徵或區段。
