---
description: 特徵排除在模型工作流程中提供額外的控制項，讓您根據網域專業知識和法規要求，新增必要的防護罩邊欄至模型。使用排除選項，選取從一或多個資料來源建立模型時忽略哪些特性。
seo-description: 特徵排除在模型工作流程中提供額外的控制項，讓您根據網域專業知識和法規要求，新增必要的防護罩邊欄至模型。使用排除選項，選取從一或多個資料來源建立模型時忽略哪些特性。
seo-title: 演算法模型特徵排除
title: 演算法模型特徵排除
uuid: 1359800b-6e6c-41b4-28b4-23d31952abb3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在模型工作流程中提供額外的控制項，讓您根據網域專業知識和法規需求，新增必要的防護罩至模型。Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## 使用個案 {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 可讓您排除某些特定的特徵(例如網站訪客特徵)，因此不會對模型造成偏差，導致結果持平。
* 您可以移除不知道或不信任資料來源的特性，從而更好地理解有影響力的特徵。
* 您可以排除特定特徵(如人口統計特徵)，以協助您承擔任何符合規範的義務。

>[!IMPORTANT]
>
>第三個使用案例的重要附註。If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. 建立模型後，無法排除模型中的特徵。See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). 請小心使用此功能，並與資料供應商合作，以確認動態消息結構有任何變更。

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. [!UICONTROL Exclusions] 選取一或多個用於模型的資料來源後，選取範圍就會變灰。
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. **[!UICONTROL Select Traits to Exclude]** 在視窗中，您可以查看與先前所選資料來源相關的所有特性。選取要排除的特徵。
4. 您可以依特徵類型來篩選特徵，也可以瀏覽特徵資料夾。請注意，特徵資料夾只會顯示與您所選資料來源相關聯的特性。
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>您可以排除資料夾特徵來排除整個資料夾，而不是逐一排除資料夾中的特徵。例如，在具有20個特徵的檔案夾中，您只需要排除資料夾特徵，而不會逐一排除所有特徵。

如果您偏好教學課程影片，請觀看我們的「特徵排除」影片展示：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=chi_hant)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要檢視中排除的特性 </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>角色存取控制(RBAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>在儲存模型後修改排除的特性 </p> </td>
   <td colname="col2"> <p>建立並儲存模型後，無法修改排除的特性。如果您想要調整結果，可以複製模型並變更排除的特性。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的最大特徵數 </p> </td>
   <td colname="col2"> <p>可從模型排除的特性上限為500。使用資料夾特性以最大化您的排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基準特徵 </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## 相關連結

* [關於演算法特徵](/help/using/features/algorithmic-models/understanding-models.md)
* [特徵排除-教學課程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)