---
description: 特性排除在建模工作流中提供了其他控制，使您能夠根據您的域專業知識和法規要求向模型添加必要的防護欄。 使用「排除」選項可選擇在從一個或多個資料源建立模型時要忽略哪些特徵。
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: 算法模型特徵排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%

---

# 相似建模：特徵排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在建模工作流中提供了其他控制項，允許您根據您的域專業知識和法規要求將必要的護欄添加到模型中。 使用 [!UICONTROL Exclusions] 選項，以選擇在從一個或多個資料源建立模型時要忽略的特徵。

## 使用個案 {#use-cases}

以下是您可以處理的一些使用案例 [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 使您能夠排除某些「全能」特徵，因此您不會偏倚模型，導致結果扁平。
* 你可以從資料源中去除你不知道或不信任的特質，以便更好地理解這些有影響力的特質。
* 你可以排除某些特徵，如人口特徵，以幫助履行你可能承擔的任何合規義務。

>[!IMPORTANT]
>
>關於第三個使用案例的重要說明。 如果第三方資料提供程式在資料源中添加新的人口特徵 *建立模型後*，模型自動提取特徵。 在建立模型後，不能從建模中排除特徵。 請參閱 [重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 使用此功能時請小心謹慎，並與資料提供程式合作，以確保告知您對源結構的任何更改。

![](assets/lam_exclude_traits.png)

## 如何使用特徵排除 {#how-to-use}

使用 [構建模型](../../features/algorithmic-models/create-model.md#build-model) 構建新的算法模型。

1. 的 [!UICONTROL Exclusions] 在您選擇一個或多個資料源進行建模之前，選擇將呈灰色顯示。
2. 選擇一個或多個資料源進行建模後，按 **[!UICONTROL Browse All Traits]**。
3. 在 **[!UICONTROL Select Traits to Exclude]** 窗口中，您可以查看與先前選擇的資料源關聯的所有特徵。 選擇要排除的特徵。
4. 您可以按特徵類型、特徵群體類型篩選特徵([設備ID](../../reference/ids-in-aam.md) 和 [跨設備ID](../../reference/ids-in-aam.md))，或者可以瀏覽特徵資料夾。 請注意，特性資料夾只顯示與所選資料源關聯的特性。
5. 按 **[!UICONTROL Exclude Selected Traits]**。

![特徵排除](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>您可以排除整個資料夾，方法是逐個排除資料夾特性，而不是排除資料夾中的特性。 例如，在具有20個特徵的資料夾中，您只需排除資料夾特徵，而不是逐個排除所有特徵。

如果您喜歡視頻教程，請觀看我們的視頻演示「特性排除」：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

此外，請觀看下面的視頻，詳細瞭解跨設備指標的工作原理。

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 重要方面和限制 {#important-aspects-and-limitations}

請注意以下與 [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要視圖中的排除特徵 </p> </td>
   <td colname="col2"> <p>排除的特徵 <i>沒來</i> 在「模型摘要」視圖中。 您只能在 <b><span class="uicontrol"> 編輯模型</span></b> 工作流。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>基於角色的訪問控制(RBAC) </p> </td>
   <td colname="col2"> <p>請注意以下公司使用的限制 <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果你無權查看某個特性，你 <i>不能</i> 選擇要從模型中排除的特性。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果你無權查看某個特性，你 <i>不能</i> 查看排除的traits清單中的該特徵。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>保存模型後修改排除的特徵 </p> </td>
   <td colname="col2"> <p>建立並保存模型後，不能修改排除的特徵。 如果要調整結果，可克隆模型並更改排除的特徵。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的最大特徵數 </p> </td>
   <td colname="col2"> <p>可以從模型中排除的最大特徵數為500。 使用資料夾特徵最大化排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基線特性 </p> </td>
   <td colname="col2"> <p>預設情況下，基線特性被排除，因此它不會顯示在 <b><span class="uicontrol"> 排除</span></b> 清單。 </p> </td>
  </tr>
 </tbody>
</table>

觀看以下視頻，瞭解如何以及為什麼從 [!UICONTROL Look-Alike Model]。

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相關連結

* [關於算法特性](/help/using/features/algorithmic-models/understanding-models.md)
* [特性排除 — 教程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
