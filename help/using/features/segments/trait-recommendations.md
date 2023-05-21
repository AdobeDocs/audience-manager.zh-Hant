---
description: 有了特徵建議功能，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: 特徵建議
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 8%

---

# 特徵建議

在構建細分市場時，從自己的第一方特徵中獲得即時特徵建議， [!UICONTROL Audience Marketplace] 資料饋送。

## 視頻演示

從監視 [!UICONTROL Trait Recommendations] 下面顯示視頻，然後閱讀以獲取詳細資訊。 視頻演示演示了如何處理來自您自己的第一方特徵的建議，以及來自 [!UICONTROL Audience Marketplace] 資料饋送 *您已訂閱*。

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一個視頻概述了 [!UICONTROL Marketplace Recommendations]，顯示如何根據中的資料源建議向段添加特徵 [!UICONTROL Audience Marketplace]。 這些建議基於資料源 *您未訂閱*。

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations]，由 [!DNL Adobe Sensei]，將資料科學引入您的Audience Manager日常工作流。
與 [!UICONTROL Trait Recommendations]，在 [段生成器](segment-builder.md)，您將獲得有關可包含的其他特性的建議，這些特性與段規則中的特性相似。

Audience Manager顯示，你的建議都來自你的第一黨特徵， **[!UICONTROL Recommendations]** 和 **[!UICONTROL Audience Marketplace]**，也請參見Wiki頁。 **[!UICONTROL Recommendations from Marketplace]** 的子菜單。

將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特性Recommendations概述](assets/trait-recommendations-overview-full.png)

**簡而言之：**

* Audience Manager顯示 [!UICONTROL Recommendations] 的子菜單。 您未訂閱的公共和專用源的市場建議可在 [!UICONTROL Recommendations from Marketplace] 的子菜單。 按一下源名稱以轉到 [!UICONTROL Audience Marketplace] 訂閱。
* Audience Manager最多顯示50個與段規則中類似的特徵。
* 您可以過濾掉不想查看任何建議的資料源。
* 計算相似性時，Audience Manager考慮 [UUID](../../reference/ids-in-aam.md) 在過去30天裡就符合了。
* 如果看到錯誤消息「未找到類似的特徵。 性狀可能太新了。」這意味著，過去30天中，該性狀沒有活動，或者Audience Manager尚未更新有關該性狀的建議。 請在24小時後重試。

## 使用個案

與 [!UICONTROL Trait Recommendations]，您可以根據使用Audience Manager的方式改進工作流：

* 作為營銷人員，你可以借助類似的特點快速找到對互補產品感興趣的受眾，這樣你就可以擴大觸角。
* 如果將Audience Manager用作發佈者， [!UICONTROL Trait Recommendations]您可以瞭解受眾行為，並為廣告銷售或用戶購買構建更好的細分市場。
* 作為 [!UICONTROL Audience Marketplace] 資料購買者，我想在不瀏覽大量源的情況下發現相關的第三方資料。
* 作為 [!UICONTROL Audience Marketplace] 資料提供商，我想向購買者推薦相關資料，以便我能夠從最優且相關的訂閱中獲益。

## 特徵Recommendations與算法模型的差異

### 演算法模型

[!UICONTROL Algorithmic Models] 不僅找到最具影響力的特徵，還根據這些特徵對用戶進行評分，並為每個用戶分配一個個人得分。 接著您可建立演算法特徵，來鎖定您的使用者。在 [!UICONTROL Trait Builder]，您可以指定所有具有您希望針對的影響性特徵的用戶中的哪些用戶。

[!UICONTROL Algorithmic Models] 使您能夠選擇精度級別不同的用戶，並test [!UICONTROL Audience Lab] 哪組用戶轉換得更好。 請參閱[在 Audience Lab 中比較模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)中的詳細使用案例。

在 [!UICONTROL Algorithmic Models]模型每8天運行一次，刷新符合算法特徵的用戶。

### 特徵建議

[!UICONTROL Trait Recommendations] 是一種快速的方法，可以獲得與你在某段中使用的特徵類似的其他特徵。

你應該 [!UICONTROL Trait Recommendations] 時間：

* 您在建立區段時需要快速的深入分析；
* 您正使用區段進行簡短的行銷活動，或想要快速隱藏轉換的受眾；
* 您正嘗試最大程度提高觸及率。

## 工作流程

在中構建或編輯段時 [段生成器](segment-builder.md)，可以探索與分段規則中的特徵相似的特徵。 的 [段生成器](segment-builder.md) 對於新段和現有段，工作流非常相似：

### 新段

1. 轉到 **受眾資料>段**，然後按一下 **添加新**。
1. 在 **性狀** 下拉框，向段規則中添加至少一個特徵。
1. 你可以看到第一方推薦的特徵 [!UICONTROL Audience Marketplace] 訂閱的源的特性建議 **[!UICONTROL Recommendations]** 的子菜單。 的 **[!UICONTROL Recommendations from Marketplace]** 部分顯示您未訂閱的源的特性建議。 所有這些建議都與您添加到段規則中的特徵相似。 向下滾動查看所有推薦的特性。
1. （可選）要從某些資料源中排除建議的第一方特徵，請按一下 **X** 要排除的資料源的符號。

   >[!NOTE]
   >
   >排除的資料源顯示在推薦特性清單的正上方。 按一下 **X** 框中，刪除排除項並再次查看各資料源的結果。
1. 要將推薦的特徵添加到段規則，請按一下 **+** 的雙曲餘切值。

>[!IMPORTANT]
>
>添加時 [!UICONTROL Marketplace] traits到一個段，這些traits僅用於段估計，直到您訂閱相應的資料饋送。 來自您未訂閱的資料源的特徵在特性清單中用購物車表徵圖標籤。 按一下特性名稱可轉到資料饋送頁並訂閱該頁。
>
>![市場未訂閱](assets/trait-recommendations-marketplace.png)
>
>只有在對相應的資料源進行訂閱後，才能保存具有第三方特徵的段。

### 現有段

1. 轉到 **[!UICONTROL Audience Data]>[!UICONTROL Segments]**，選擇要編輯的段並按一下 ![編輯](assets/edit-button.png)。
1. 向下滾動到 [!UICONTROL Traits] 下拉框。
1. 您可以看到推薦的特徵，這些特徵與分段規則中已有的特徵相似。 向下滾動查看所有推薦的特性。
1. （可選）要從某些資料源中排除建議的特徵，請按一下 **X** 要排除的資料源的符號。

   >[!NOTE]
   >
   >排除的資料源顯示在推薦特性清單的正上方。 按一下 **X** 框中，刪除排除項並再次查看各資料源的結果。
1. 要將推薦的特徵添加到段規則，請按一下 **+** 的雙曲餘切值。

當您建立或編輯段並向段規則添加特徵時，您最多會看到50個建議的特徵，與您添加的特徵類似。 如果分段規則包含多個特徵，則在分段規則中，Audience Manager使用循環方法顯示每個特徵的最佳匹配，然後每個特徵的次佳匹配，等等，顯示按種群數量排列的最大50個特徵。

![三大基本特徵](assets/three-base-traits.png)

例如，當段規則中有三個特徵時，建議的特徵是：

1. 性狀3（人數最多的性狀）最佳匹配；
1. 性狀1最佳匹配；
1. 性狀2最佳匹配；
1. 性狀3次最佳匹配；
1. 第二個最適合性狀1，等等，直到你達到50個性狀。

要獲取針對特定特徵的建議，可以按一下段規則(1)或建議特徵視圖(2)中的特徵。

![基特徵示例](assets/three-base-traits-numbered.png)

按一下第一方特性會開啟一個彈出窗口，如下圖所示。 如果建議的特徵不是段的一部分，可通過按將它們添加到段 **+**。

![添加到段](assets/add_to_segments.png)

>[!TIP]
>
>在特徵資訊彈出窗口內生成建議時，考慮首頁中排除的資料源。 而且，如果在此視圖中排除資料源，則排除將應用於首頁。

>[!NOTE]
>
>建議的特徵可以是您訂閱的資料源中的第一方特徵或第三方特徵 [!UICONTROL Audience Marketplace]。

## 運作方式

要生成特徵推薦，Audience Manager計算 [雅卡德相似性](https://en.wikipedia.org/wiki/Jaccard_index) 在目標特性和您的帳戶可以訪問的所有其它特性之間，包括第三方資料。 Audience Manager顯示最多50個相似性最高的特徵。

## 特質相似性分數 {#trait-similarity-score}

Audience Manager計算 [!UICONTROL Trait Similarity Score] 通過求交和並數計算兩個特徵之間 [!UICONTROL UUID]s，然後把兩者分開。 對於A和B兩種特徵，計算結果如下：

![Jaccard相似度](assets/jaccard_similarity.png)

另請參見以下兩個示例。

### 示例1 — 低特徵相似性得分

給出A和B兩個特徵，假設每個特徵都有100萬人 [!UICONTROL UUID]s,25,000 [!UICONTROL UUID]其中兩個特徵都符合。
使用上述公式，將導致：25,000 / 1,975,000 = 0.012。這是個低點 [!UICONTROL Trait Similarity Score]這兩個特徵是非常不同的。

![特徵 — 推薦 — 低重疊](assets/Trait-Recommendations-Low-overlap.png)

### 示例2 — 特性相似性得分

如果A和B的相同性狀有40萬 [!UICONTROL UUID]符合這兩種特質的 [!UICONTROL Trait Similarity Score] 要高得多：400,000 / 1,600,000 = 0.25

![特徵 — 推薦 — 高重疊](assets/Trait-Recommendations-High-overlap.png)

### 如何解讀特質相似性評分

使用下表作為特徵相似性的粗略指南。 本指南基於在大多數特徵上觀察到的相似性得分。

| [!UICONTROL Trait Similarity Score] | 意義 |
|---------|----------|
| 0.1及以上 | 性狀之間的高度相似性 |
| 0.03 - 0.1 | 性狀之間的中等相似性 |
| 0.01 - 0.03 | 性狀之間的低相似性 |
| 0 - 0.01 | 特徵之間的相似性很低 |

## 基於角色的訪問控制(RBAC)

對於使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])，您需要具有建立和編輯段的權限才能查看推薦的特徵。 您看到的特性建議僅是您通過訪問的資料源 [!UICONTROL RBAC]。

>[!IMPORTANT]
>
>添加 [!UICONTROL Marketplace Recommendations] 對於一個段，用戶必須首先訂閱相應的資料源。 只有具有管理員權限的用戶才能訂閱 [!UICONTROL Audience Marketplace] 資料饋送。

閱讀有關 [!UICONTROL RBAC] 控制項 [這裡](../administration/administration-overview.md)。

## 限制

* 目前，Audience Manager不將資料夾特徵顯示為推薦特徵。 閱讀有關資料夾特徵的詳細資訊 [這裡](../traits/manage-folder-traits.md)。
* 在展示特質Recommendations時，Audience Manager [!DNL Boolean] 運算子([!DNL AND]。 [!DNL OR]。 [!DNL NOT])。
