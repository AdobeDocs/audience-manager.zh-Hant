---
description: 有了特徵建議功能，您在區段產生器中建立或編輯區段時，系統會根據區段規則中的特徵，提供您其他類似特徵的相關建議，您可考慮納入。將建議的特徵加入區段，有助於擴大您的目標對象範圍。
seo-description: 建立區段時，獲取即時特徵建議。
seo-title: 特徵建議
solution: Audience Manager
title: 特徵建議
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 特徵建議

建立區段時，獲取即時特徵建議。

## 影片展示

首先觀看特徵Recommendations視訊，然後閱讀詳細資訊以瞭解詳細資訊。

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=chi_hant)

## 概述

[!UICONTROL Trait Recommendations]為您的Audience [!DNL Adobe Sensei]Manager提供資料科學。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 將建議的特徵加入區段，有助於擴大您的目標對象範圍。

![特徵建議概述](assets/trait-recommendations-overview.png)

**在nutshell中：**

* Audience Manager會將目前訂閱資料饋送中的第一方特徵和第三方特徵顯示為建議特徵。
* Audience Manager最多顯示50個類似於區段規則中的特徵。
* 您可以篩選不想查看任何建議的資料來源。
* 計算相似時，Audience Manager會將 [過去](../../reference/ids-in-aam.md) 30天內符合特徵的UUID視為合格。
* 如果您看到錯誤訊息，「找不到類似的特性」。特徵可能過於新。「這表示過去30天內，該特徵沒有任何活動，而Audience Manager尚未更新該特徵的建議。請在24小時後再試一次。

## 使用個案

透過 [!UICONTROL Trait Recommendations]使用Audience Manager，您可以改善工作流程：

* 身為行銷人員，您可以透過類似的特性快速找到對互補性產品感興趣的受眾，從而提高您的觸及面。
* 如果您使用Audience Manager做為發佈商，您 [!UICONTROL Trait Recommendations]可以瞭解受眾行為，並建立更好的細分來進行廣告銷售或使用者獲取。

## 特徵建議與演算法模型之間的差異

### 演算法模型

[!UICONTROL Algorithmic Models] 不僅找到最具影響力的特徵，還能根據這些特性向使用者評分，並為每位使用者指派個別分數。然後，您可以建立演算法特徵來定位您的使用者。您可以在這些 [!UICONTROL Trait Builder]控制項中準確控制和觸及控制，以便指定哪些使用者擁有您想要定位的具影響力特徵。

[!UICONTROL Algorithmic Models] 可讓您在不同的準確度層級選擇使用者，並在 [!UICONTROL Audience Lab] 哪個使用者群組中進行更好的轉換。請參閱Audience Lab [中比較模型的詳細使用案例](../../features/audience-lab/audience-lab-use-cases.md#compare-models)。

In [!UICONTROL Algorithmic Models]，the model run each days and installshes the users regited for演算法fures.

### 特徵建議

[!UICONTROL Trait Recommendations] 這是一種快速獲取其他特性的深入資訊，這些特性與您在區段中使用的其他特性類似。

您應在下列情況下使用 [!UICONTROL Trait Recommendations] ：

* 建立區段時需要快速深入解析；
* 您使用群體來簡短促銷活動或想要快速抑制轉換的對象；
* 您正在嘗試最大化觸及面。

## 工作流程

在 [「區段產生器](segment-builder.md)」中建立或編輯區段時，您可以探索類似區段規則中特徵的特性。新和現有區段的區段產生器工作流程非常類似：

### 新區段

1. 在 **「對象資料&gt;區段**」中，選取 **「新增」**。
2. 在 **「特徵」** 下拉式方塊中，新增至少一個特徵至區段規則。
3. 您現在可以看到類似於新增至區段規則之特性的建議特性。向下捲動以查看所有建議的特性。
4. (選擇性)若要排除某些資料來源的建議特性，請按一下 **您要排除之資料來源的X** 符號。
   > [!NOTE]
   > 
   >排除的資料來源會顯示在建議特性清單上方。按灰色方塊中 **的X** ，移除排除，然後再次查看個別資料來源的結果。
5. 若要新增建議特徵至區段規則，請按一下 **+** 符號。

### 現有區段

1. 前往 **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**，選取您要編輯的區段，然後按 ![編輯](assets/edit-button.png)。
1. 向下捲動至 [!UICONTROL Traits] 下拉式方塊。
1. 您可以看見建議特徵，類似於區段規則中已有的特徵。向下捲動以查看所有建議的特性。
1. (選擇性)若要排除某些資料來源的建議特性，請按一下 **您要排除之資料來源的X** 符號。
   > [!NOTE]
   > 
   >排除的資料來源會顯示在建議特性清單上方。按灰色方塊中 **的X** ，移除排除，然後再次查看個別資料來源的結果。
1. 若要新增建議特徵至區段規則，請按一下 **+** 符號。

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

按一下特徵會開啓快顯視窗，如下圖所示。如果建議的特徵不屬於區段的一部分，您可以按一下 **+**&#x200B;將其新增至區段。

![](assets/add_to_segments.png)

> [!TIP]
>
>在特徵資訊彈出式視窗中產生建議時，會考慮主頁面中排除的資料來源。此外，如果您在此檢視中排除資料來源，排除會套用至主頁面。

> [!NOTE]
>
> 建議的特徵可以是您訂閱的動態消息中的第一方特徵或第三方特徵。

## 運作方式

若要產生特徵建議，Audience Manager會模擬目標特徵與您帳戶存取(包括第三方資料)的每個其他特徵 [之間的Jacard相似度](https://en.wikipedia.org/wiki/Jaccard_index) 。Audience Manager接著會顯示最多50個具有最高相似性的特徵。

## 特徵相似性分數

Audience [!UICONTROL Trait Similarity Score] Manager會根據 [!UICONTROL UUID]s的數目計算相交和聯合，計算兩個特性之間的差異，然後除以兩者。對於兩個特徵A和B，計算結果看起來如下：

![](assets/jaccard_similarity.png)

請參閱下列兩個範例。

### 範例-低特徵相似性分數

假設有兩個特性A和B，假設每個特徵的人口為1,000， [!UICONTROL UUID]000，25,000 [!UICONTROL UUID]，其中有兩個特徵符合這兩個特性。
使用上述公式，將會產生：25,000/1,975,000=0.012。這很低 [!UICONTROL Trait Similarity Score]，這兩個特性很不相同。

![](assets/Trait-Recommendations-Low-overlap.png)

### 範例-特徵相似性分數

如果相同特徵A和B有400,000 [!UICONTRL 個UUID]符合兩個特性，則更 [!UICONTROL Trait Similarity Score] 高：
400,000/1,600,000=0.25

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

對於使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，您必須擁有建立和編輯區段的權限，才能查看建議的特性。而且，您所看到的建議特徵僅來自您可透過存取權存取的資料來源 [!UICONTROL RBAC]。請參閱此處的 [!UICONTROL RBAC] 更多控制 [](../administration/administration-overview.md)項。

## 限制

* Audience Manager目前不會將資料夾特性顯示為建議特性。請在此處閱讀有關資料夾特性 [的更多](../traits/manage-folder-traits.md)資訊。
* 顯示特徵Recommendations時，Audience Manager不會在區段規則中進入 [!DNL Boolean] 運算元([!DNL AND]， [!DNL OR]， [!DNL NOT])。