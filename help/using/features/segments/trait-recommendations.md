---
description: 有了特徵建議功能，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: 在建立區段時取得即時特徵建議。
seo-title: 特徵建議
solution: Audience Manager
title: 特徵建議
feature: 區段
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# 特徵建議

從您自己的第一方特徵和[!UICONTROL Audience Marketplace]資料摘要，在建立區段時取得即時特徵建議。

## 影片示範

首先觀看下方的[!UICONTROL Trait Recommendations]影片，然後閱讀以取得詳細資訊。 影片示範會示範如何使用您自己第一方特徵的建議，以及[!UICONTROL Audience Marketplace]資料摘要中&#x200B;*您已訂閱*&#x200B;的特徵建議。

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一部影片會概述[!UICONTROL Marketplace Recommendations]的工作流程，顯示如何根據[!UICONTROL Audience Marketplace]中資料摘要的建議，將特徵新增至區段。 這些建議以您未訂閱&#x200B;*的資料摘要為基礎。*

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations]由提供技 [!DNL Adobe Sensei]術支援，將資料科學帶入您的Audience Manager日常工作流程中。若使用[!UICONTROL Trait Recommendations]，當您在[區段產生器](segment-builder.md)中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。

Audience Manager會同時顯示第一方特徵、**[!UICONTROL Recommendations]**&#x200B;區段和&#x200B;**[!UICONTROL Audience Marketplace]**&#x200B;區段中的特徵建議。**[!UICONTROL Recommendations from Marketplace]**

將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特徵Recommendations概觀](assets/trait-recommendations-overview-full.png)

**簡言之：**

* Audience Manager在[!UICONTROL Recommendations]區段中顯示第一方特徵。 您未訂閱之公開和私人摘要的Marketplace建議會顯示在[!UICONTROL Recommendations from Marketplace]區段中。 按一下摘要名稱以前往[!UICONTROL Audience Marketplace]並訂閱。
* Audience Manager最多會顯示50個類似於區段規則中的特徵。
* 您可以篩選掉不想看見任何建議的資料來源。
* 計算相似度時，Audience Manager會考量過去30天內符合特徵資格的[UUID](../../reference/ids-in-aam.md)。
* 如果您看到錯誤訊息「找不到類似特徵」。 特徵可能太新。」這表示過去30天內沒有該特徵的活動，或Audience Manager尚未更新該特徵的建議。 請在24小時後再試一次。

## 使用個案

透過[!UICONTROL Trait Recommendations]，您可以根據使用Audience Manager的方式來改善工作流程：

* 身為行銷人員，您可以透過類似特徵，快速找到對補充性產品感興趣的對象，以便您擴大觸及範圍。
* 如果您以Audience Manager作為發佈者，透過[!UICONTROL Trait Recommendations]，便可了解受眾行為，並為廣告銷售或使用者贏取建立更好的區段。
* 身為[!UICONTROL Audience Marketplace]資料購買者，我想要探索相關的第三方資料，而不瀏覽大量摘要。
* 身為[!UICONTROL Audience Marketplace]資料提供者，我想向購買者建議相關資料，以便從最佳且相關的訂閱中獲益。

## 特徵Recommendations與演算法模型之間的差異

### 演算法模型

[!UICONTROL Algorithmic Models] 不僅可找出最具影響力的特徵，還根據這些特徵對使用者進行評分，並為每位使用者指派個別的分數。接著您可建立演算法特徵，來鎖定您的使用者。在[!UICONTROL Trait Builder]中，您可以透過精確度和觸及控制項，指定哪些使用者擁有您要鎖定的具影響力特徵。

[!UICONTROL Algorithmic Models] 可讓您選取不同準確度等級的使用者，並測試哪 [!UICONTROL Audience Lab] 組使用者轉換效果較佳。請參閱[在 Audience Lab 中比較模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)中的詳細使用案例。

在[!UICONTROL Algorithmic Models]中，模型每8天執行一次，並重新整理符合演算法特徵資格的使用者。

### 特徵建議

[!UICONTROL Trait Recommendations] 可讓您快速深入分析其他與您在區段中使用的特徵相似的特徵。

在下列情況下，應使用[!UICONTROL Trait Recommendations]:

* 您在建立區段時需要快速的深入分析；
* 您正使用區段進行簡短的行銷活動，或想要快速隱藏轉換的受眾；
* 您正嘗試最大程度提高觸及率。

## 工作流程

在[區段產生器](segment-builder.md)中建立或編輯區段時，您可以探索類似區段規則中特徵的特徵。 新區段和現有區段的[區段產生器](segment-builder.md)工作流程非常類似：

### 新區段

1. 前往「**受眾資料>區段**」，然後按一下「**新增**」。
1. 在&#x200B;**特徵**&#x200B;下拉式方塊中，至少新增一個特徵至區段規則。
1. 您可以在&#x200B;**[!UICONTROL Recommendations]**&#x200B;區段中，從您訂閱的摘要中看到第一方建議特徵和[!UICONTROL Audience Marketplace]特徵建議。 **[!UICONTROL Recommendations from Marketplace]**&#x200B;區段會顯示您未訂閱之摘要的特徵建議。 這些建議全都類似於您新增至區段規則的特徵。 向下捲動以查看所有建議的特徵。
1. （選用）若要從特定資料來源排除建議的第一方特徵，請針對您要排除的資料來源按一下&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除項目，並再次查看個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

>[!IMPORTANT]
>
>將[!UICONTROL Marketplace]特徵新增至區段時，這些特徵只會用於區段估計，直到您訂閱對應的資料摘要為止。 來自您未訂閱之資料摘要的特徵會在特徵清單中標示為購物車圖示。 按一下特徵名稱即可前往資料摘要頁面並訂閱。
>
>![marketplace-not subscriped](assets/trait-recommendations-marketplace.png)
>
>只有在訂閱對應的資料摘要後，才能儲存具有第三方特徵的區段。

### 現有區段

1. 前往&#x200B;**[!UICONTROL Audience Data]>[!UICONTROL Segments]**，選取您要編輯的區段，然後按一下![Edit](assets/edit-button.png)。
1. 向下捲動至[!UICONTROL Traits]下拉式方塊。
1. 您可以看到與區段規則中已有的特徵類似的建議特徵。 向下捲動以查看所有建議的特徵。
1. （選用）若要從特定資料來源排除建議的特徵，請針對您要排除的資料來源按一下&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除項目，並再次查看個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

當您建立或編輯區段並將特徵新增至區段規則時，您最多會看到50個建議特徵，類似於您所新增的特徵。 如果區段規則包含多個特徵，Audience Manager會使用循環方式來顯示每個特徵的最佳比對，以及每個特徵的次佳比對，以此類推，在區段規則中顯示最多五十個特徵（依母體）的最佳比對，依此類推。

![三個基本特徵](assets/three-base-traits.png)

例如，當區段規則中有三個特徵時（如下所示），建議的特徵為：

1. 最符合特徵3（人口最多的特徵）;
1. 最符合特徵1;
1. 最符合特徵2;
1. 特徵3的次佳匹配；
1. 特徵1等的次佳比對，直到您取得50個特徵為止。

若要取得特定特徵的建議，您可以按一下區段規則(1)或建議特徵檢視(2)中的特徵。

![base-traits-example](assets/three-base-traits-numbered.png)

按一下第一方特徵會開啟快顯視窗，如下圖所示。 如果建議的特徵不屬於區段，您可以按&#x200B;**+**&#x200B;將其新增至區段。

![新增至區段](assets/add_to_segments.png)

>[!TIP]
>
>在特徵資訊快顯視窗內產生建議時，會考量主要頁面中排除的資料來源。 此外，如果您在此檢視中排除資料來源，排除將套用至主要頁面。

>[!NOTE]
>
>建議的特徵可以是您在[!UICONTROL Audience Marketplace]中訂閱之資料摘要的第一方特徵或第三方特徵。

## 運作方式

若要產生特徵建議，Audience Manager會計算目標特徵與您的帳戶可存取的每個其他特徵（包括第三方資料）之間的[Jaccard相似度](https://en.wikipedia.org/wiki/Jaccard_index)。 Audience Manager接著會顯示最多50個相似度最高的特徵。

## 特徵相似度分數{#trait-similarity-score}

Audience Manager根據[!UICONTROL UUID]s的數量計算交集和聯合，然後將兩個特徵進行分割，以計算兩個特徵之間的[!UICONTROL Trait Similarity Score]。 針對兩個特徵A和B，計算方式如下：

![jaccard-similiary](assets/jaccard_similarity.png)

另請參閱以下兩個範例。

### 範例1 — 低特徵相似度分數

根據兩個特徵A和B，假設每個特徵的母體為1,000,000 [!UICONTROL UUID]s,25,000 [!UICONTROL UUID]s，符合這兩個特徵的資格。
使用上述公式，將產生：25,000 / 1,975,000 = 0.012。這是一個低[!UICONTROL Trait Similarity Score]的值，這兩個特徵非常不同。

![trait-recommendations-low-overplad](assets/Trait-Recommendations-Low-overlap.png)

### 範例2 — 特徵相似度分數

如果相同的特徵A和B有400,000個[!UICONTROL UUID]s符合這兩個特徵的資格，則[!UICONTROL Trait Similarity Score]要高得多：
400,000 / 1,600,000 = 0.25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### 如何解讀特徵相似度分數

使用下表作為特徵相似度的粗略指南。 本指南以大部分特徵觀察到的相似度分數為基礎。

| [!UICONTROL Trait Similarity Score] | 顯著性 |
---------|----------|
| 0.1及以上版本 | 特徵之間的高度相似性 |
| 0.03 - 0.1 | 特徵之間的中等相似度 |
| 0.01 - 0.03 | 特徵之間的低相似度 |
| 0 - 0.01 | 特徵之間的相似性非常低 |

## 基於角色的訪問控制(RBAC)

對於使用[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])的公司，您必須擁有建立和編輯區段的權限，才能查看建議的特徵。 您看到的特徵建議只是您透過[!UICONTROL RBAC]存取的資料來源。

>[!IMPORTANT]
>
>若要新增[!UICONTROL Marketplace Recommendations]至區段，使用者必須先訂閱對應的資料饋送。 只有具有管理員權限的用戶才能訂閱[!UICONTROL Audience Marketplace]資料摘要。

請詳閱[!UICONTROL RBAC]控制項[此處](../administration/administration-overview.md)了解詳情。

## 限制

* 目前，Audience Manager未將資料夾特徵顯示為建議特徵。 請前往[這裡](../traits/manage-folder-traits.md)，深入了解資料夾特徵。
* 顯示特徵Recommendations時，Audience Manager不會考慮區段規則中的[!DNL Boolean]運算子([!DNL AND]、[!DNL OR]、[!DNL NOT])。
