---
description: 「特徵排除」在模型工作流程中提供其他控制項，可讓您根據您的網域專業知識和法規要求，在模型中新增必要的防護欄。 使用「排除」選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-description: 「特徵排除」在模型工作流程中提供其他控制項，可讓您根據您的網域專業知識和法規要求，在模型中新增必要的防護欄。 使用「排除」選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-title: 演算法模型特徵排除
title: 演算法模型特徵排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 演算法模型：特徵排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在模型工作流程中提供額外的控制項，讓您根據您的領域專業知識和法規要求，將必要的防護欄加入模型。 使用選 [!UICONTROL Exclusions] 項，在從一或多個資料來源建立模型時，選取要忽略哪些特徵。

## 使用個案 {#use-cases}

以下是您可處理的一些使用案例 [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] enables you to exclude certain catch-all traits, such as site visitor traits, so you don't bias the model, leading to flat results.
* You can remove traits that you don't know about or you don't trust from a data source, to better understand the influential traits.
* 您可以排除某些特徵（例如人口特徵），以協助您履行任何可能的合規義務。

>[!IMPORTANT]
>
>關於第三個使用案例的重要說明。 如果協力廠商資料提供者在您建立模型後，將新的人口統計特徵新 *增至資料饋送*，則模型會自動擷取該特徵。 建立模型後，您無法從模型中排除特徵。 請參 [閱重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 使用此功能時請務必小心，並與資料提供者合作，以確保您得知動態消息結構有任何變更。

![](assets/lam_exclude_traits.png)

## 如何使用特徵排除 {#how-to-use}

Use the Build a model workflow to build new algorithmic models.[](../../features/algorithmic-models/create-model.md#build-model)

1. 在您 [!UICONTROL Exclusions] 選取一或多個資料來源進行模型建立之前，選取範圍會變灰。
2. After selecting one or more data sources for modeling, press .**[!UICONTROL Browse All Traits]**
3. 在視窗 **[!UICONTROL Select Traits to Exclude]** 中，您可以看到與先前選取的資料來源相關聯的所有特徵。 選取您要排除的特徵。
4. You can filter the traits by trait type, or you can browse the trait folders. Note that trait folders only display the traits associated with your selected data sources.
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>You can exclude entire folders by excluding the folder trait instead of excluding the traits in the folder, one by one. For example, in a folder with 20 traits, you would only need to exclude the folder trait instead of excluding all the traits one by one.

If you prefer video tutorials, watch our video demonstration for Trait Exclusion:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=chi_hant)

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
   <td colname="col1"> <p>Excluded Traits in Models Summary View </p> </td>
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
   <td colname="col2"> <p>可從模型中排除的特徵數上限為500。 使用資料夾特徵來最大化排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基準特徵 </p> </td>
   <td colname="col2"> <p>基線特徵預設會排除，因此在建立模型時不會顯示在 <b><span class="uicontrol"> Exclusions</span></b> 清單中。 </p> </td>
  </tr>
 </tbody>
</table>

觀看以下影片，瞭解從中排除特定特徵的方式及原因 [!UICONTROL Look-Alike Model]。

>[!VIDEO](https://video.tv.adobe.com/v/25569/?captions=chi_hant)

## 相關連結

* [關於演算法特徵](/help/using/features/algorithmic-models/understanding-models.md)
* [特徵排除——教學課程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)