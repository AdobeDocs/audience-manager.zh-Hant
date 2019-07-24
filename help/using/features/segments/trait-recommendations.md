---
description: 有了特徵建議功能，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: 建立區段時，獲取即時特徵建議。
seo-title: 特徵建議
solution: Audience Manager
title: 特徵建議
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# 特徵建議

建立區段時，獲取即時特徵建議。

## 概述

[!UICONTROL Trait Recommendations]為您的Audience [!DNL Adobe Sensei]Manager提供資料科學。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特徵建議概述](assets/trait-recommendations-overview.png)

**在nutshell中：**

* Audience Manager會將目前訂閱資料饋送中的第一方特徵和第三方特徵顯示為建議特徵。
* Audience Manager最多顯示50個類似於區段規則中的特徵。
* 您可以篩選不想查看任何建議的資料來源。
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* 如果您看到錯誤訊息，「找不到類似的特性」。特徵可能過於新。「這表示過去30天內，該特徵沒有任何活動，而Audience Manager尚未更新該特徵的建議。請在24小時後再試一次。

## 使用個案

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* 身為行銷人員，您可以透過類似的特性快速找到對互補性產品感興趣的受眾，從而提高您的觸及面。
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## 特徵建議與演算法模型之間的差異

### 演算法模型

[!UICONTROL Algorithmic Models] 不僅找到最具影響力的特徵，還能根據這些特性向使用者評分，並為每位使用者指派個別分數。然後，您可以建立演算法特徵來定位您的使用者。With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] 可讓您在不同的準確度層級選擇使用者，並在 [!UICONTROL Audience Lab] 哪個使用者群組中進行更好的轉換。See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### 特徵建議

[!UICONTROL Trait Recommendations] 這是一種快速獲取其他特性的深入資訊，這些特性與您在區段中使用的其他特性類似。

You should use [!UICONTROL Trait Recommendations] when:

* 建立區段時需要快速深入解析；
* 您使用群體來簡短促銷活動或想要快速抑制轉換的對象；
* 您正在嘗試最大化觸及面。

## 工作流程

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. 新和現有區段的區段產生器工作流程非常類似：

### 新區段

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. 您現在可以看到類似於新增至區段規則之特性的建議特性。向下捲動以查看所有建議的特性。
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >排除的資料來源會顯示在建議特性清單上方。Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### 現有區段

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. 您可以看見建議特徵，類似於區段規則中已有的特徵。向下捲動以查看所有建議的特性。
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >排除的資料來源會顯示在建議特性清單上方。Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

當您建立或編輯區段並新增特徵至區段規則時，最多可看見50個建議特徵，類似於您新增的特性。如果區段規則包含多個特徵，Audience Manager會使用四捨五入的robin方法來顯示每個特徵最適合的比對，然後在區段規則中，對每個特徵的最大50個特徵進行第二個最佳比對。

![三個基本特徵](assets/three-base-traits.png)

例如，當區段規則中有三個特徵時，建議的特徵為：

1. 特徵3(特徵與最大人口族群的特徵)；
2. 特徵的最佳比對1；
3. 特徵的最佳比對2；
4. 特徵的第二個最佳比對；
5. 針對特徵的第二個最佳比對，等到您獲得50個特徵為止。

若要針對特定特徵取得建議，您可以按一下區段規則(1)中的特性或建議的特徵檢視(2)。

![](assets/three-base-traits-numbered.png)

按一下特徵會開啓快顯視窗，如下圖所示。If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>在特徵資訊彈出式視窗中產生建議時，會考慮主頁面中排除的資料來源。此外，如果您在此檢視中排除資料來源，排除會套用至主頁面。

> [!NOTE]
>
> 建議的特徵可以是您訂閱的動態消息中的第一方特徵或第三方特徵。

## 運作方式

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager接著會顯示最多50個具有最高相似性的特徵。

## 特徵相似性分數

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. 對於兩個特徵A和B，計算結果看起來如下：

![](assets/jaccard_similarity.png)

請參閱下列兩個範例。

### 範例-低特徵相似性分數

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### 範例-特徵相似性分數

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### 如何解譯特徵相似性分數

使用下表作為特徵相似性的粗略指南。本指南是根據大部分特性所觀察到的相似性分數。

| [!UICONTROL Trait Similarity Score] | 重要性 |
---------|----------|
| 0.1及以上版本 | 特性之間相似 |
| 0.03 - 0.1 | 特徵之間的適中相似性 |
| 0.01 - 0.03 | 特徵之間的相似性低 |
| 0 - 0.01 | 特性之間非常相似 |

## 角色存取控制(RBAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## 限制

* Audience Manager目前不會將資料夾特性顯示為建議特性。Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.