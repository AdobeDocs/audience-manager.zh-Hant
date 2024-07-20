---
description: 有了特徵Recommendations，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。 將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: 特徵Recommendations
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 5%

---

# 特徵Recommendations

在建立區段時，從您自己的第一方特徵和[!UICONTROL Audience Marketplace]資料摘要取得即時特徵建議。

## 影片示範

從觀看下面的[!UICONTROL Trait Recommendations]影片開始，然後閱讀以取得更多資訊。 影片示範會示範如何使用您自己的第一方特徵建議，以及&#x200B;*您已訂閱*&#x200B;之[!UICONTROL Audience Marketplace]資料摘要的特徵建議。

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一個影片概述[!UICONTROL Marketplace Recommendations]的工作流程，說明如何根據[!UICONTROL Audience Marketplace]中資料摘要的建議將特徵新增至您的區段。 這些建議是根據&#x200B;*您未訂閱*&#x200B;的資料摘要。

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations] （由[!DNL Adobe Sensei]提供技術支援）將資料科學帶入您的Audience Manager日常工作流程中。
透過[!UICONTROL Trait Recommendations]，當您在[區段產生器](segment-builder.md)中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。

Audience Manager會顯示第一方特徵在&#x200B;**[!UICONTROL Recommendations]**&#x200B;區段中的特徵建議，以及來自&#x200B;**[!UICONTROL Audience Marketplace]**&#x200B;在&#x200B;**[!UICONTROL Recommendations from Marketplace]**&#x200B;區段中的特徵建議。

將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特徵Recommendations概觀](assets/trait-recommendations-overview-full.png)

**簡略說明：**

* Audience Manager會在[!UICONTROL Recommendations]區段中顯示第一方特徵。 您未訂閱的公開和私人摘要中的Marketplace建議會顯示在[!UICONTROL Recommendations from Marketplace]區段中。 按一下摘要名稱以移至[!UICONTROL Audience Marketplace]並訂閱。
* Audience Manager最多會顯示50個特徵，與區段規則中的特徵類似。
* 您可以篩選掉不想看到任何建議的資料來源。
* 計算相似性時，Audience Manager會考慮過去30天內符合特徵的[個UUID](../../reference/ids-in-aam.md)。
* 如果您看到錯誤訊息「找不到類似特徵。 特徵可能太新。」，這表示在過去30天內沒有該特徵的活動，或Audience Manager尚未更新該特徵的建議。 請24小時後再試一次。

## 使用個案

透過[!UICONTROL Trait Recommendations]，您可以根據使用Audience Manager的方式改善工作流程：

* 行銷人員可透過類似特徵快速找到對互補產品感興趣的對象，進而擴大您的觸角。
* 如果您使用Audience Manager作為具有[!UICONTROL Trait Recommendations]的發佈者，則可以瞭解對象行為並為廣告銷售或使用者贏取建立更好的區段。
* 身為[!UICONTROL Audience Marketplace]資料購買者，我想要探索相關的協力廠商資料，而不需瀏覽大量摘要。
* 身為[!UICONTROL Audience Marketplace]資料提供者，我想向買家建議相關資料，以便從最佳化及相關訂閱中受益。

## 特徵Recommendations和演演算法模型之間的差異

### 演演算法模型

[!UICONTROL Algorithmic Models]不僅會尋找最具影響力的特徵，還會根據這些特徵對使用者進行評分，並為每位使用者指派個別的分數。 接著您可建立演算法特徵，來鎖定您的使用者。透過[!UICONTROL Trait Builder]中的精確度和觸及控制，您可以指定哪些使用者擁有您想要鎖定的具影響力特徵。

[!UICONTROL Algorithmic Models]可讓您選取不同精確度等級的使用者，並在[!UICONTROL Audience Lab]中測試哪一組使用者轉換效果較佳。 請參閱[在 Audience Lab 中比較模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)中的詳細使用案例。

在[!UICONTROL Algorithmic Models]中，模型每8天執行一次，並重新整理符合演演算法特徵的使用者。

### 特徵Recommendations

[!UICONTROL Trait Recommendations]可快速深入分析有哪些其他特徵與您在區段中使用的特徵類似。

您應在下列情況下使用[!UICONTROL Trait Recommendations]：

* 您在建立區段時需要快速的深入分析；
* 您正使用區段進行簡短的行銷活動，或想要快速隱藏轉換的受眾；
* 您正嘗試最大程度提高觸及率。

## 工作流程

在[區段產生器](segment-builder.md)中建立或編輯區段時，您可以探索與區段規則中的特徵相似的特徵。 新區段和現有區段的[區段產生器](segment-builder.md)工作流程非常類似：

### 新區段

1. 前往&#x200B;**對象資料>區段**，然後按一下&#x200B;**新增**。
1. 在&#x200B;**特徵**&#x200B;下拉式方塊中，將至少一個特徵新增至區段規則。
1. 您可以在&#x200B;**[!UICONTROL Recommendations]**&#x200B;區段中檢視您所訂閱之摘要的第一方建議特徵和[!UICONTROL Audience Marketplace]特徵建議。 **[!UICONTROL Recommendations from Marketplace]**&#x200B;區段會顯示您未訂閱之摘要的特徵建議。 所有這些建議與新增至區段規則的特徵類似。 向下捲動以檢視所有建議的特徵。
1. （選擇性）若要從特定資料來源排除建議的第一方特徵，請按一下您要排除的資料來源的&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除專案，並再次檢視個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

>[!IMPORTANT]
>
>將[!UICONTROL Marketplace]個特徵新增至區段時，這些特徵僅用於區段估計，直到您訂閱對應的資料摘要為止。 來自您未訂閱之資料摘要的特徵，會在特徵清單中標示購物車圖示。 按一下特徵名稱，前往資料摘要頁面並訂閱。
>
>![市集未訂閱](assets/trait-recommendations-marketplace.png)
>
>您必須先訂閱對應的資料摘要，才能儲存具有第三方特徵的區段。

### 現有區段

1. 移至&#x200B;**[!UICONTROL Audience Data]>[!UICONTROL Segments]**，選取您要編輯的區段，然後按一下![編輯](assets/edit-button.png)。
1. 向下捲動至[!UICONTROL Traits]下拉式方塊。
1. 您可以看到建議的特徵，這些特徵與區段規則中已存在的特徵類似。 向下捲動以檢視所有建議的特徵。
1. （選擇性）若要從特定資料來源排除建議的特徵，請按一下您要排除的資料來源的&#x200B;**X**&#x200B;符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下灰色方塊中的&#x200B;**X**&#x200B;以移除排除專案，並再次檢視個別資料來源的結果。
1. 若要將建議的特徵新增至區段規則，請按一下&#x200B;**+**&#x200B;符號。

當您建立或編輯區段並將特徵新增至區段規則時，最多會看到50個建議特徵，與您新增的特徵類似。 如果區段規則包含多個特徵，Audience Manager會使用循環配置圖方法來顯示每個特徵的最佳相符專案，接著顯示區段規則中母體數量最多的50個特徵的第二個最佳相符專案，以此類推。

![三個基本特徵](assets/three-base-traits.png)

例如，區段規則中有三個特徵時（如下所示），建議的特徵為：

1. 特徵3 （人口最多的特徵）的最佳相符專案；
1. 特徵1的最佳相符專案；
1. 特徵2的最佳相符專案；
1. 特徵3的次佳匹配；
1. 第二個最符合特徵1，以此類推，直到您獲得50個特徵為止。

若要取得特定特徵的建議，您可以在區段規則(1)或建議的特徵檢視(2)中按一下特徵。

![base-traits-example](assets/three-base-traits-numbered.png)

按一下第一方特徵會開啟快顯視窗，如下圖所示。 如果建議的特徵不是區段的一部分，您可以按&#x200B;**+**&#x200B;將它們新增至區段。

![新增至區段](assets/add_to_segments.png)

>[!TIP]
>
>在特徵資訊快顯視窗中產生建議時，會考慮從首頁面排除的資料來源。 此外，如果您在此檢視中排除資料來源，排除專案會套用至首頁面。

>[!NOTE]
>
>建議的特徵可以是您在[!UICONTROL Audience Marketplace]中訂閱之資料摘要的第一方特徵或第三方特徵。

## 運作方式

為了產生特徵建議，Audience Manager會計算目標特徵與您的帳戶可存取的所有其他特徵（包括第三方資料）之間的[Jaccard相似度](https://en.wikipedia.org/wiki/Jaccard_index)。 Audience Manager接著會顯示最多50個具有最高相似度的特徵。

## 特徵相似度分數 {#trait-similarity-score}

Audience Manager計算兩個特徵之間的[!UICONTROL Trait Similarity Score]，方法是以[!UICONTROL UUID]的數目計算交集和聯合，然後將兩個特徵相除。 針對兩個特徵A和B，計算方式如下：

![jaccard-similarity](assets/jaccard_similarity.png)

另請參閱下列兩個範例。

### 範例1 — 低特徵相似度分數

假設有兩個特徵A和B，假設每個特徵都有1,000,000個[!UICONTROL UUID]和25,000個[!UICONTROL UUID]母體，都符合兩個特徵的資格。
使用上述公式，這會產生：25,000 / 1,975,000 = 0.012。這是低[!UICONTROL Trait Similarity Score]，兩個特徵非常不同。

![特徵 — 建議 — 低重疊](assets/Trait-Recommendations-Low-overlap.png)

### 範例2 — 特徵相似度分數

如果相同特徵A和B有400,000個同時符合兩個特徵的[!UICONTROL UUID]，則[!UICONTROL Trait Similarity Score]會高很多：
400,000 / 1,600,000 = 0.25

![特徵 — 建議 — 高重疊](assets/Trait-Recommendations-High-overlap.png)

### 如何解讀特徵相似度分數

使用下表作為特徵相似度的粗略指南。 本指南根據大多數特徵中觀察到的相似性分數。

| [!UICONTROL Trait Similarity Score] | 重要性 |
|---------|----------|
| 0.1及更高版本 | 特徵之間的高相似性 |
| 0.03 - 0.1 | 特徵之間的Medium相似度 |
| 0.01 - 0.03 | 特徵之間的低相似性 |
| 0 - 0.01 | 特徵之間的相似度很低 |

## 角色型存取控制(RBAC)

對於使用[!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，您必須有建立和編輯區段的許可權，才能檢視建議的特徵。 您看到的特徵建議只是您透過[!UICONTROL RBAC]存取之資料來源的特徵建議。

>[!IMPORTANT]
>
>若要將[!UICONTROL Marketplace Recommendations]新增至區段，使用者必須先訂閱對應的資料摘要。 只有具有管理員許可權的使用者才能訂閱[!UICONTROL Audience Marketplace]資料摘要。

在[此處](../administration/administration-overview.md)閱讀有關[!UICONTROL RBAC]控制項的詳細資訊。

## 限制

* 目前，Audience Manager不會將資料夾特徵顯示為建議的特徵。 在[這裡](../traits/manage-folder-traits.md)閱讀更多有關資料夾特徵的資訊。
* 顯示特徵Recommendations時，Audience Manager未考慮區段規則中的[!DNL Boolean]運運算元([!DNL AND]、[!DNL OR]、[!DNL NOT])。
