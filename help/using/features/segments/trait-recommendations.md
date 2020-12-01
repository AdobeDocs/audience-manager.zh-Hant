---
description: 有了特徵建議功能，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: 在建立區段時取得即時特徵建議。
seo-title: 特徵建議
solution: Audience Manager
title: 特徵建議
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# 特徵建議

從您自己的第一方特徵和[!UICONTROL Audience Marketplace]資料饋送建立區段時，取得即時特徵建議。

## 視訊展示

首先觀看下面的[!UICONTROL Trait Recommendations]視頻，然後閱讀以瞭解詳細資訊。 影片展示會示範如何使用您自己的第一方特徵的建議，以及您已訂閱&#x200B;*之[!UICONTROL Audience Marketplace]資料饋送的特徵建議。*

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一個視訊會概述[!UICONTROL Marketplace Recommendations]的工作流程，顯示如何根據[!UICONTROL Audience Marketplace]中資料饋送的建議，將特徵新增至區段。 這些建議是以您未訂閱&#x200B;*的資料饋送為基礎。*

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations]在Audience Manager的支 [!DNL Adobe Sensei]援下，將資料科學帶入您的日常工作流程。使用[!UICONTROL Trait Recommendations]，當您在[區段產生器](segment-builder.md)中建立或編輯區段時，您會獲得可包含的其他特徵建議，這些特徵類似於區段規則中的特徵。

Audience Manager會從您的第一方特徵、**[!UICONTROL Recommendations]**&#x200B;區段和&#x200B;**[!UICONTROL Audience Marketplace]**&#x200B;區段中，顯示特徵建議。**[!UICONTROL Recommendations from Marketplace]**

將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特徵建議概觀](assets/trait-recommendations-overview-full.png)

**簡而言之：**

* Audience Manager在[!UICONTROL Recommendations]區段中顯示第一方特徵。 您未訂閱之公開和私人動態消息的市場建議會顯示在[!UICONTROL Recommendations from Marketplace]區段中。 按一下動態消息名稱，前往[!UICONTROL Audience Marketplace]並訂閱。
* Audience Manager最多顯示50個類似區段規則中的特徵。
* 您可以篩選不想看到任何建議的資料來源。
* 在計算相似度時，Audience Manager會考慮在過去30天內符合特徵的[UUID](../../reference/ids-in-aam.md)。
* 如果您看到錯誤訊息「找不到類似特徵」。 特徵可能太新。」這表示過去30天內該特徵沒有活動，或Audience Manager尚未更新該特徵的建議。 請在24小時內再試一次。

## 使用個案

有了[!UICONTROL Trait Recommendations]，您可以改善工作流程，視您使用Audience Manager的方式而定：

* 身為行銷人員，您可以透過類似特性的協助，快速找到對互補產品感興趣的受眾，以便擴大觸及面。
* 如果您使用Audience Manager做為發行者，並搭配[!UICONTROL Trait Recommendations]，您就可以瞭解受眾行為，並建立更好的細分，以利廣告銷售或使用者獲取。
* 身為[!UICONTROL Audience Marketplace]資料購買者，我想在不瀏覽大量動態消息的情況下，發現相關的第三方資料。
* 身為[!UICONTROL Audience Marketplace]資料提供者，我想向購買者推薦相關資料，以便從最佳且相關的訂閱中獲益。

## 特徵建議與演算法模型的差異

### 演算法模型

[!UICONTROL Algorithmic Models] 不僅可以找到最具影響力的特徵，還可以根據這些特徵對用戶進行評分，並為每個用戶分配一個單獨的分數。接著您可建立演算法特徵，來鎖定您的使用者。在[!UICONTROL Trait Builder]中，您可以精確控制並觸及控制項，指定您要鎖定哪些具有影響力特性的使用者。

[!UICONTROL Algorithmic Models] 可讓您選擇不同準確度等級的使用者，並測試哪 [!UICONTROL Audience Lab] 組使用者轉換效果更佳。請參閱[在 Audience Lab 中比較模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)中的詳細使用案例。

在[!UICONTROL Algorithmic Models]中，模型每8天執行一次，並重新整理符合演算法特徵的使用者。

### 特徵建議

[!UICONTROL Trait Recommendations] 是取得其他特性見解的快速方式，這些特性與您在群體中使用的特性類似。

您應在下列情況下使用[!UICONTROL Trait Recommendations]:

* 您在建立區段時需要快速的深入分析；
* 您正使用區段進行簡短的行銷活動，或想要快速隱藏轉換的受眾；
* 您正嘗試最大程度提高觸及率。

## 工作流程

在[區段產生器](segment-builder.md)中建立或編輯區段時，您可以探索類似於區段規則中特徵的特性。 [區段產生器](segment-builder.md)工作流程對於新區段和現有區段非常類似：

### 新區段

1. 前往&#x200B;**讀者資料>區段**，然後按一下「新增&#x200B;**」。**
1. 在&#x200B;**Traits**&#x200B;下拉式方塊中，新增至少一個特徵至區段規則。
1. 您可在&#x200B;**[!UICONTROL Recommendations]**&#x200B;區段中，從您訂閱的饋送中看到第一方建議特徵和[!UICONTROL Audience Marketplace]特徵建議。 **[!UICONTROL Recommendations from Marketplace]**&#x200B;區段會顯示您未訂閱之饋送的特徵建議。 所有這些建議都類似於您新增至區段規則的特徵。 向下捲動以查看所有建議的特徵。
1. （選擇性）若要從某些資料來源排除建議的第一方特徵，請按一下您要排除之資料來源的&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除項目，並再次檢視個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

>[!IMPORTANT]
>
>將[!UICONTROL Marketplace]特徵新增至區段時，這些特徵僅用於區段估計，直到您訂閱對應的資料饋送為止。 來自您未訂閱之資料饋送的特徵會在特徵清單中標示為購物車圖示。 按一下特徵名稱，前往資料饋送頁面並加以訂閱。
>
>![marketplace-not-subscriped](assets/trait-recommendations-marketplace.png)
>
>您只能在訂閱對應的資料饋送後，才能儲存具有第三方特徵的區段。

### 現有區段

1. 前往&#x200B;**[!UICONTROL Audience Data]>[!UICONTROL Segments]**，選取您要編輯的區段，然後按一下「編輯![](assets/edit-button.png)」。
1. 向下捲動至[!UICONTROL Traits]下拉式方塊。
1. 您可以看到與區段規則中現有特徵類似的建議特徵。 向下捲動以查看所有建議的特徵。
1. （可選）若要從某些資料來源排除建議的特徵，請按一下您要排除之資料來源的&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除項目，並再次檢視個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

當您建立或編輯區段並新增特徵至區段規則時，最多會看到50個建議特徵，與您新增的特徵類似。 如果區段規則包含多個特徵，Audience Manager會在區段規則中使用循環方式顯示每個特徵的最佳比對，接著顯示每個特徵的次佳比對，依人口數計算，以及最多50個特徵的次佳比對等。

![三種基本特徵](assets/three-base-traits.png)

例如，當區段規則中有三個特徵（如下所示）時，建議的特徵為：

1. 特徵3（人口最多的特徵）的最佳匹配；
1. 特徵1的最佳匹配；
1. 特徵2的最佳匹配；
1. 特徵3的次佳匹配；
1. 特徵1的次佳匹配，等等，直到您獲得50個特徵。

若要取得特定特徵的建議，您可以按一下區段規則(1)或建議特徵檢視(2)中的特徵。

![base-traits-example](assets/three-base-traits-numbered.png)

按一下第一方特徵會開啟快顯視窗，如下圖所示。 如果建議的特徵不屬於區段，您可以按&#x200B;**+**&#x200B;將其新增至區段。

![新增至區段](assets/add_to_segments.png)

>[!TIP]
>
>在特徵資訊快顯視窗中產生建議時，會考慮來自首頁面的已排除資料來源。 此外，如果您在此檢視中排除資料來源，排除將套用至首頁面。

>[!NOTE]
>
>建議的特徵可以是您在[!UICONTROL Audience Marketplace]中訂閱之資料饋送的第一方特徵或第三方特徵。

## 運作方式

若要產生特徵建議，Audience Manager會計算目標特徵和您的帳戶可存取的所有其他特徵（包括第三方資料）之間的[Jaccard相似性](https://en.wikipedia.org/wiki/Jaccard_index)。 然後，Audience Manager會顯示最多50個相似度最高的特徵。

## 特徵相似性分數{#trait-similarity-score}

Audience Manager會根據[!UICONTROL UUID]s的數目計算交叉點和並，然後將兩個特徵分割，以計算兩個特徵之間的[!UICONTROL Trait Similarity Score]。 對於兩個特徵A和B，計算結果如下：

![jaccard-similiar](assets/jaccard_similarity.png)

另請參見以下兩個示例。

### 範例1 —— 低特徵相似性分數

假設有兩個特徵A和B，假設每個特徵的人口為1,000,000個[!UICONTROL UUID]s,25,000個[!UICONTROL UUID]s，其中兩個特徵都符合。
使用上述公式，將產生：25,000 / 1,975,000 = 0.012。這是一個低[!UICONTROL Trait Similarity Score]的特徵，這兩個特徵非常不同。

![特徵——建議——低重疊](assets/Trait-Recommendations-Low-overlap.png)

### 範例2 —— 特徵相似性分數

如果相同的特徵A和B有400,000個[!UICONTROL UUID]s符合這兩個特徵，則[!UICONTROL Trait Similarity Score]要高得多：
400,000 / 1,600,000 = 0.25

![特徵——建議——高重疊](assets/Trait-Recommendations-High-overlap.png)

### 如何解讀特徵相似度分數

使用下表作為特徵相似性的粗略指南。 本指南基於在大多數特徵上觀察到的相似性得分。

| [!UICONTROL Trait Similarity Score] | 重要性 |
---------|----------|
| 0.1及以上版本 | 特徵之間的高度相似性 |
| 0.03 - 0.1 | 特徵之間的中度相似性 |
| 0.01 - 0.03 | 特徵之間的低相似性 |
| 0 - 0.01 | 特徵之間的相似性很低 |

## 基於角色的訪問控制(RBAC)

對於使用[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])的公司，您必須擁有建立和編輯區段的權限，才能查看建議的特徵。 您看到的特徵建議僅是您可透過[!UICONTROL RBAC]存取的資料來源。

>[!IMPORTANT]
>
>若要新增[!UICONTROL Marketplace Recommendations]至區段，使用者必須先訂閱對應的資料饋送。 只有具有管理員權限的使用者才能訂閱[!UICONTROL Audience Marketplace]資料饋送。

閱讀更多[!UICONTROL RBAC]控制項[的相關資訊。](../administration/administration-overview.md)

## 限制

* 目前，Audience Manager不會將資料夾特徵顯示為建議特徵。 閱讀更多有關資料夾特徵[的資訊，請參閱](../traits/manage-folder-traits.md)。
* 在顯示「特徵建議」時，Audience Manager不會在區段規則中考慮[!DNL Boolean]運算子([!DNL AND]、[!DNL OR]、[!DNL NOT])。
