---
description: 「特徵排除」在模型工作流程中提供其他控制項，可讓您根據您的網域專業知識和法規要求，在模型中新增必要的防護欄。 使用「排除」選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-description: 「特徵排除」在模型工作流程中提供其他控制項，可讓您根據您的網域專業知識和法規要求，在模型中新增必要的防護欄。 使用「排除」選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-title: 演算法模型特徵排除
title: 演算法模型特徵排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: 859e55fa5d93c7c56cef4bf2a112cdd4ff318d97

---


# 相似模型： 特徵排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在模型工作流程中提供額外的控制項，讓您根據您的領域專業知識和法規要求，將必要的防護欄加入模型。 使用選 [!UICONTROL Exclusions] 項，在從一或多個資料來源建立模型時，選取要忽略哪些特徵。

## 使用個案 {#use-cases}

以下是您可處理的一些使用案例 [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 可讓您排除特定的全面性特徵，例如網站訪客特徵，因此您不會偏倚模型，導致平坦結果。
* 您可以從資料來源移除您不知道或不信任的特徵，以便更好地瞭解這些具影響力的特徵。
* 您可以排除某些特徵（例如人口特徵），以協助您履行任何可能的合規義務。

>[!IMPORTANT]
>
>關於第三個使用案例的重要說明。 如果協力廠商資料提供者在您建立模型後，將新的人口統計特徵新 *增至資料饋送*，則模型會自動擷取該特徵。 建立模型後，您無法從模型中排除特徵。 請參 [閱重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 使用此功能時請務必小心，並與資料提供者合作，以確保您得知動態消息結構有任何變更。

![](assets/lam_exclude_traits.png)

## 如何使用特徵排除 {#how-to-use}

使用「建 [立模型」工作流程](../../features/algorithmic-models/create-model.md#build-model) ，建立新的演算模型。

1. 在您 [!UICONTROL Exclusions] 選取一或多個資料來源進行模型建立之前，選取範圍會變灰。
2. 在選取一或多個資料來源進行模型建立後，請按 **[!UICONTROL Browse All Traits]**。
3. 在視窗 **[!UICONTROL Select Traits to Exclude]** 中，您可以看到與先前選取的資料來源相關聯的所有特徵。 選取您要排除的特徵。
4. 您可以依特徵類型、特徵人口族群類型([裝置ID](../../reference/ids-in-aam.md)[和跨裝置ID](../../reference/ids-in-aam.md))篩選特徵，或瀏覽特徵資料夾。 請注意，特徵資料夾只會顯示與您選取資料來源相關的特徵。
5. Press **[!UICONTROL Exclude Selected Traits]**.

![特徵排除](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>您可以逐個排除資料夾特徵，而不是排除資料夾中的特徵，以排除整個資料夾。 例如，在具有20個特徵的資料夾中，您只需要排除資料夾特徵，而不需逐一排除所有特徵。

如果您偏好視訊教學課程，請觀看我們的「特徵排除」視訊示範：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

此外，請觀看以下影片，以詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 重要方面與限制 {#important-aspects-and-limitations}

請注意以下相關方面和限制 [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要檢視中排除的特徵 </p> </td>
   <td colname="col2"> <p>排除的特 <i>徵不會顯示在</i> 「模型摘要」檢視中。 您只能在「編輯模型」工作流程中看到排 <b><span class="uicontrol"> 除的特徵</span></b> 。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>基於角色的訪問控制(RBAC) </p> </td>
   <td colname="col2"> <p>請注意使用 <a href="../../features/administration/administration-overview.md#administration"> RBAC的公司的下列限制</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果您沒有檢視特徵的存取權，則無 <i>法</i> 選取要從模型中排除的特徵。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果您沒有檢視特徵的存取權，則無法 <i>在排除的</i> 特徵清單中檢視該特徵。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>在儲存模型後修改排除的特徵 </p> </td>
   <td colname="col2"> <p>在建立並保存模型後，不能修改排除的特徵。 如果您想要調整結果，可以仿製模型並變更排除的特徵。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的特徵數上限 </p> </td>
   <td colname="col2"> <p>可從模型中排除的特徵數上限為500。 使用資料夾特徵最大化排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基準特徵 </p> </td>
   <td colname="col2"> <p>基線特徵預設會排除，因此在建立模型時不會顯示在 <b><span class="uicontrol"> Exclusions</span></b> 清單中。 </p> </td>
  </tr>
 </tbody>
</table>

觀看以下影片，瞭解從中排除特定特徵的方式及原因 [!UICONTROL Look-Alike Model]。

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相關連結

* [關於演算法特徵](/help/using/features/algorithmic-models/understanding-models.md)
* [特徵排除——教學課程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)