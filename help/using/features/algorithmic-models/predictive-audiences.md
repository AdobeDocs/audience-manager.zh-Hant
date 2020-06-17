---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾概述
solution: Audience Manager
title: Audience Manager 預測受眾
translation-type: tm+mt
source-git-commit: 4df2a7536155d42133c0873ed4e3376eb24cba1a
workflow-type: tm+mt
source-wordcount: '1275'
ht-degree: 9%

---


# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 協助您使用進階的資料科學技術，將未知的受眾即時分類為不同的角色。

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

 在行銷環境中，角色是一種受眾區段，由擁有一組共同特定特徵 (例如人口統計、瀏覽習慣、購物記錄等) 的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型可讓您使用 Audience Manager 的機器學習功能，將未知的受眾分類為不重複角色，進一步運用此概念。Audience Manager 可協助您針對一組已知的第一方受眾，計算未知第一方受眾的傾向，進而實現此目標。

當您建立模 [!UICONTROL Predictive Audiences] 型時，第一步是選擇您希望目標對象依據的基準特徵或區段。 這些特徵或群體將定義您的角色。

在評估階段，模型會針對您定義為基 [!UICONTROL Predictive Audiences] 線的每個特徵或區段建立新區段。 下次Audience Manager從您的目標對象看到未分類為角色的訪客（不符合任何基準特徵或區段的資格）時，模型會決定訪客應屬於哪個預測區段，並將訪客新增至該區段。 [!UICONTROL Predictive Audiences]

您可以在頁面中識別由模型建立的預測性 [!UICONTROL Segments] 區段。 每個 [!UICONTROL Predictive Audiences] 模型在資料夾下都有其自己的 [!UICONTROL Predictive Audiences] 資料夾，通過按一下模型資料夾可以查看每個模型的段。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 使用個案 {#use-cases}

為協助您更清楚瞭解您的使用方式 [!UICONTROL Predictive Audiences]和時間，以下是Audience Manager客戶可使用此功能解決的一些使用案例。

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

## 預測性受眾模型的運作方式

建立模型時， [!UICONTROL Predictive Audiences] 需要執行三個步驟：

1. 首先，您至少選取兩個特徵或兩個區段來定義您的角色。
1. 然後，您選擇一個特徵或群體，以定義您要分類的目標對象。
1. 最後，您為模型選擇名稱，並選取將儲存預測性區段的資料來源。

### 角色選擇標準 {#selection-personas}

您可以選擇任何第一方特徵或群體來定義您的角色。 不過，為獲得最佳結果，以下是一組建議的最佳實務：

* 選擇您的角色特徵或群體，讓每個角色至少擁有幾百個 [裝置ID](../../reference/ids-in-aam.md)。
* 如果您的特徵是以跨裝 [置ID為基礎](../../reference/ids-in-aam.md)，您可以使用使用裝置ID的描述檔合併規則 [(](../profile-merge-rules/merge-rules-overview.md) 例如)將其包住區段 [](../../reference/ids-in-aam.md)[!UICONTROL Device Graph]。 這可確保有足夠的 [裝置ID](../../reference/ids-in-aam.md) ，讓演算法學習。
* 我們建議您為個人選擇特徵或簡單區段，由1到3個特徵組成。
* 選擇重疊最小的基線特徵或區段。
* 請確定您正在擷取數位屬性中的細微特徵。

### 目標對象的選擇標準 {#selection-audience}

與個人選擇類似，您應選擇您的特徵或群體來定義目標受眾，讓其擁有具有豐富特徵集的即時用戶，以便將其分類為正確的個人。

### 預測性受眾模型培訓階段 {#model-training}

在演算法將您的第一方受眾分類為適當角色之前，它必須先針對您的資料進行自我訓練。

對於您定義的每個角色，演算法會分析其個別對象，並評估其使用者在過去30天內的任何即時和／或已登入特徵活動。
此步驟每24小時進行一次，以說明您第一方受眾的變更。

### 預測性觀眾模型分類階段 {#model-classification}

當即時檢視屬於目標對象的訪客時，模型會評估該訪客是否屬於已定義角色。 對於不屬於任何角色的每位訪客，模型會指派角色資格分數。

在評估第一方受眾並指派分數時，模型會使用您帳戶中 **[!UICONTROL Profile Merge Rule]** 定義的預設值。 最後，訪客被分類為獲得最高分的人物。

![預測對象圖](assets/predictive-audiences-graph.png)

## 考量事項與限制 {#considerations}

>[!IMPORTANT]
> 請仔細閱讀本節內容，然後再轉至實施階段。

在設定模 [!UICONTROL Predictive Audiences] 型時，請記住下列考量和限制：

* 您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。
* 對於每個模型，您最多可以選擇50個基本特徵／區段。
* 目前不支援第二方和第三方資料 [!UICONTROL Predictive Audiences]。
* 觀眾分類僅針對即時的第一方觀眾進行。 未來更新可能支援已登入的第一方觀眾分類。
   >[!IMPORTANT]
   > 目前，預 [!UICONTROL Total Segment Population] 測性區段的顯示為0，而預測性 [對象不支援批次傳出資料傳輸](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) 。 此行為在未來的更新中將會改變。
* [!UICONTROL Predictive Audiences] 從所有第一方資料來源，根據您的第一方特徵執行對象分類。
* 區段評估 [!UICONTROL Predictive Audiences] 會使用您在帳 **[!UICONTROL Profile Merge Rule]** 戶中定義的預設值。 若要進一步瞭解 [!UICONTROL Profile Merge Rules] 專用的 [檔案](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)。
* 部分特徵和區段不支援做為基準或目標對象。 [!UICONTROL Predictive Audiences] 當選擇下列其中一項作為基準或目標對象時，模型將無法保存：
   * 預測性特徵和使用預測性特徵建立的群體；
   * [Adobe Experience Platform特性](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 或細分；
   * 算法特徵；
   * 第二方和第三方特徵。

## 資料匯出控制{#dec}

模型建立的預 [!UICONTROL Predictive Audiences] 測性區段會從 [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) 下列第一方資料來源繼承「資料匯出控制」:

1. 建立模型時您選擇的第一方資料來源。
1. 目標對象的第一方資料來源。 具體來說，是構成您目標對象之特徵或區段的資料匯出控制。

新建立的預測性特徵和區段的隱私權限制與上述第一方資料來源的合併相同。

具有不屬於區段隱私權限制之其他限制的特 [!UICONTROL Predictive Audiences] 徵，將會排除在培訓階段之外，不會對模型產生影響。

## 基於角色的訪問控制{#rbac}

您為角色和對象分類選擇的特徵和區段受Audience Manager角色型存 [取控制的約束](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)。

Audience Manager使用者只能為其有權檢視的角色和目標對象選取特徵 [或區段](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)。
