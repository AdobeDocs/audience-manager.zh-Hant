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
source-wordcount: '1485'
ht-degree: 7%

---

# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 幫助您利用先進的資料科學技術，將未知的觀眾分為不同的人物，並即時進行分類。

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

 在行銷環境中，角色是一種受眾區段，由擁有一組共同特定特徵 (例如人口統計、瀏覽習慣、購物記錄等) 的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型可讓您使用 Audience Manager 的機器學習功能，將未知的受眾分類為不重複角色，進一步運用此概念。Audience Manager 可協助您針對一組已知的第一方受眾，計算未知第一方受眾的傾向，進而實現此目標。

建立 [!UICONTROL Predictive Audiences] 模型，第一步是選擇希望目標受眾按其分類的基線特徵或段。 這些特徵或片段將定義您的角色。

在評估階段，模型會建立新 [!UICONTROL Predictive Audiences] 為定義為基線的每個特性或段分段。 下次Audience Manager看到目標受眾中未被分類為個人（未符合任何基準特徵或段落）的訪問者時， [!UICONTROL Predictive Audiences] 模型將確定訪問者應屬於哪個預測段，並將訪問者添加到該段。

您可以在 [!UICONTROL Segments] 的子菜單。 每個 [!UICONTROL Predictive Audiences] 模型的下面有其自己的資料夾 [!UICONTROL Predictive Audiences] 資料夾，通過按一下模型資料夾可查看每個模型的段。

![預測受眾段](assets/predictive-audiences-segments.png)

## 使用個案 {#use-cases}

幫助您更好地瞭解如何和何時使用 [!UICONTROL Predictive Audiences]，下面是Audience Manager客戶可使用此功能解決的幾個使用案例。

### 用例#1

作為一家電子商務公司的營銷人員，我想將我的所有網路和移動訪問者分類到不同的品牌親和性類別，以便我能夠個性化他們的用戶體驗。

### 用例#2

作為一家媒體公司的營銷人員，我希望將未經身份驗證的網路和移動訪問者按他們喜歡的類型分類，這樣我就可以向他們建議跨所有渠道的個性化內容。

### 用例#3

作為一家航空公司的廣告商，我希望確保根據觀眾對旅遊目的地的興趣來對觀眾進行分類，這樣我就可以在很短的重新定位窗口內向他們即時發佈廣告。

### 用例#4

作為廣告商，我希望即時地對我的第一方觀眾進行分類，以便我能夠對趨勢新聞做出快速反應。

### 用例#5

作為營銷人員，我想預測我的網站訪問者處於哪個客戶旅程階段，如發現、訂約、購買或保留，以便我可以相應地瞄準他們。

### 用例#6

作為一家媒體公司，我希望將我的受眾分類，這樣我就可以以高價出售我的廣告空間，同時為我的訪問者提供相關的廣告。

## 如何 [!UICONTROL Predictive Audiences] 模型工作 {#how-predictive-audiences-models-work}

建立 [!UICONTROL Predictive Audiences] 模型：

1. 首先，您至少選擇兩個特徵或兩個段來定義您的角色。
1. 然後，您選擇一個特性或段來定義您要分類的目標受眾。
1. 最後，為模型選擇一個名稱、一個將儲存預測段的資料源，以及 [!UICONTROL Profile Merge Rule] 的下界。

### 個人選擇標準 {#selection-personas}

您可以選擇任何第一方特徵或段來定義您的角色。 但是，為了獲得最佳結果，以下是一組建議的最佳做法：

* 選擇您的性格特徵或段落，使每個人格至少擁有幾百個 [設備ID](../../reference/ids-in-aam.md)。
* 如果你的特徵是基於 [跨設備ID](../../reference/ids-in-aam.md)，可以用 [配置檔案合併規則](../profile-merge-rules/merge-rules-overview.md) 使用 [設備ID](../../reference/ids-in-aam.md)，例如 [!UICONTROL Device Graph]。 這將確保 [設備ID](../../reference/ids-in-aam.md) 算法可以學習的。
* 我們建議為您的個性選擇特徵或簡單片段，由1到3個特徵組成。
* 選擇重疊最小的基線特徵或段。
* 確保在數字屬性中捕獲粒度特徵。

### 目標受眾的選擇標準 {#selection-audience}

根據您的使用案例，無論您是要即時、批處理或兩者都對用戶進行分類，都可選擇目標受眾([!UICONTROL trait] 或 [!UICONTROL segment])具有顯著的即時和/或總人口。 與個人選擇類似，我們建議您的目標受眾 [!UICONTROL trait] 或 [!UICONTROL segment] 具有富配置檔案（富集集）的用戶 [!UICONTROL traits])。

選擇目標受眾時，分析您的使用案例並確定要分類的ID類型： [!UICONTROL device IDs] 或 [!UICONTROL cross-device IDs]。 的 [!UICONTROL Profile Merge Rule] 在建立模型時選擇的資料定義了將用於將每個用戶放入預測中的資料 [!UICONTROL segments]。

作為最佳做法，我們建議選擇 [!UICONTROL Profile Merge Rule] 與目標受眾具有相同配置 [!UICONTROL Profile Merge Rule]或包括目標受眾的配置檔案類型（設備配置檔案或經過驗證的配置檔案）的配置檔案。

### [!UICONTROL Predictive Audiences] 模型培訓階段 {#model-training}

在算法將第一方受眾分類為正確角色之前，它需要根據您的資料進行自我培訓。

對於您定義的每個角色，算法分析其各自的受眾，並評估其用戶在過去30天內的任何即時和/或特徵活動。
此步驟每24小時發生一次，以說明第一方觀眾中的更改。

### [!UICONTROL Predictive Audiences] 模型分類階段 {#model-classification}

對於即時和批量受眾分類，模型首先檢查用戶是否屬於目標受眾。 如果用戶符合目標受眾資格且不屬於任何個人，則模型會為其分配個人資格分數。

在評估第一方受眾和分配分數時，模型使用預設 **[!UICONTROL Profile Merge Rule]** 在您的帳戶中定義。 最後，遊客被歸為他們獲得最高分的人物。

![預測受眾圖](assets/predictive-audiences-graph.png)

## 注意事項和限制 {#considerations}

>[!IMPORTANT]
> 在進入實施階段之前，請仔細閱讀本節。

配置 [!UICONTROL Predictive Audiences] 模型，請牢記以下考慮和限制：

* 您最多可建立 10 個 [!UICONTROL Predictive Audiences] 模型。
* 對於每個模型，最多可以選擇50個基本特徵/段。
* 中當前不支援第二和第三方資料 [!UICONTROL Predictive Audiences]。
* [!UICONTROL Predictive Audiences] 根據您的第一方特徵從所有第一方資料源執行受眾分類。
* 分部評估 [!UICONTROL Predictive Audiences] 使用 **[!UICONTROL Profile Merge Rule]** 在模型建立過程中選擇的。 瞭解有關 [!UICONTROL Profile Merge Rules] 查看 [文檔](../profile-merge-rules/merge-rules-overview.md)。
* 某些特徵和段不支援作為基線或目標受眾。 [!UICONTROL Predictive Audiences] 當選擇下列對象之一作為基線或目標受眾時，模型將無法保存：
   * 預測性狀和用預測性狀建立的片段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 特徵或片段；
   * 算法特徵；
   * 第二和第三方特徵。
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 不能在中使用 [!UICONTROL Audience Lab]。

## [!UICONTROL Data Export Controls] {#dec}

由建立的預測段 [!UICONTROL Predictive Audiences] 模型繼承 [資料導出控制項](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) 從以下第一方資料源：

1. 在構建模型時選擇的第一方資料源。
1. 目標受眾的第一方資料源。 具體而言， [!UICONTROL traits] 或 [!UICONTROL segments] 構成目標受眾。
1. 的 [資料導出控制項](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) 的 [!UICONTROL Profile Merge Rule] 為模型選取的。

新建立的預測 [!UICONTROL traits] 和 [!UICONTROL segments] 將具有與上述第一方資料源聯合相同的隱私限制。

具有不屬於 [!UICONTROL Predictive Audiences] 部分隱私限制將被排除在培訓階段，不會對模型產生影響。

## [!UICONTROL Profile Merge Rules] {#pmr}

所有預測段將分配 [!UICONTROL Profile Merge Rule] 在建立模型時選擇的。 的 [!UICONTROL Profile Merge Rule] 您選擇的選項很重要，原因如下：

* 它定義了當模型分析影響時應考慮哪些設備和/或經過驗證的簡檔 [!UICONTROL traits]，在將用戶分類為預測 [!UICONTROL segment]。
* 它決定著 [!UICONTROL trait] 類型（設備級或跨設備級）應在模型培訓步驟中使用，並且在影響力方面浮出水面 [!UICONTROL traits]。 預測 [!UICONTROL segments] 是目標受眾的子集。
   * 如果目標受眾是段，建議您選擇相同 [!UICONTROL Profile Merge Rule] 作為分配給目標受眾的模型，或 [!UICONTROL Profile Merge Rule] 包括目標受眾的配置檔案類型。
   * 如果目標受眾是 [!UICONTROL trait]，建議您選擇 [!UICONTROL Profile Merge Rule] 可以訪問與目標受眾特性（設備配置檔案資料或跨設備配置檔案資料）相同類型的資料。
* [!UICONTROL Profile Merge Rules] 使用 [!UICONTROL Current Authenticated Profiles] 和 [!UICONTROL No Device Profile] 只支援即時訪問群體分類的選項。 有關詳細資訊，請參閱 [配置檔案合併規則選項已定義](../profile-merge-rules/merge-rule-definitions.md)。

選擇 [!UICONTROL Profile Merge Rule] 同時使用設備資料和跨設備資料的設備數量最大 [!UICONTROL traits] 可用於模型訓練和用戶分類到預測 [!UICONTROL segments]。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您為個人和受眾分類選擇的特徵和段受Audience Manager [基於角色的訪問控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)。

Audience Manager用戶只能為角色和目標受眾選擇他們具有的特徵或段 [權限](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)。
