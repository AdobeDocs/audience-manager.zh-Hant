---
description: 特徵排除在模型工作流程中提供其他控制項，允許您根據您的域專業知識和法規要求，將必要的防護欄添加到模型中。 使用排除選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-description: 特徵排除在模型工作流程中提供其他控制項，允許您根據您的域專業知識和法規要求，將必要的防護欄添加到模型中。 使用排除選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-title: 演算法模型特徵排除
title: 演算法模型特徵排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: 演算法模型
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# 相似建模：特徵排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在模型工作流中提供其他控制項，允許您根據您的域專業知識和法規要求將必要的防護欄添加到模型中。使用[!UICONTROL Exclusions]選項，從一或多個資料來源建立模型時，選取要忽略哪些特徵。

## 使用個案 {#use-cases}

以下是您可透過[!UICONTROL Trait Exclusion]處理的一些使用案例：

* [!UICONTROL Trait Exclusion] 可讓您排除某些包羅永珍的特徵，例如網站訪客特徵，因此您不會偏誤模型，導致結果持平。
* 您可以從資料來源移除您不知道或不信任的特徵，以便更清楚了解具影響力的特徵。
* 您可以排除某些特徵（例如人口統計特徵），以協助履行您可能承擔的任何合規義務。

>[!IMPORTANT]
>
>第三個使用案例的重要備注。 如果第三方資料提供者在您建立模型&#x200B;*後，將新的人口統計特徵新增至資料饋送*，則模型會自動擷取該特徵。 建立模型後，您無法排除特徵來建模。 請參閱[重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 使用此功能時請格外小心，並與資料提供者合作，以確保收到摘要結構的任何變更通知。

![](assets/lam_exclude_traits.png)

## 如何使用特徵排除{#how-to-use}

使用[建立模型](../../features/algorithmic-models/create-model.md#build-model)工作流程來建立新的演算法模型。

1. [!UICONTROL Exclusions]選項會呈現灰色，直到您為模型選擇一個或多個資料源為止。
2. 為模型選擇一個或多個資料源後，按&#x200B;**[!UICONTROL Browse All Traits]**&#x200B;鍵。
3. 在&#x200B;**[!UICONTROL Select Traits to Exclude]**&#x200B;視窗中，您可以看到與先前選取的資料來源相關聯的所有特徵。 選取要排除的特徵。
4. 您可以依特徵類型、特徵母體類型（[裝置ID](../../reference/ids-in-aam.md)和[跨裝置ID](../../reference/ids-in-aam.md)）篩選特徵，或瀏覽特徵資料夾。 請注意，特徵資料夾只會顯示與您所選資料來源相關聯的特徵。
5. 按&#x200B;**[!UICONTROL Exclude Selected Traits]**&#x200B;鍵。

![特徵排除](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>您可以逐一排除資料夾特徵，而非排除資料夾中的特徵，以排除整個資料夾。 例如，在具有20個特徵的資料夾中，您只需排除資料夾特徵，而不需逐一排除所有特徵。

如果您偏好使用教學課程影片，請觀看特徵排除的影片示範：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

此外，請觀看下方的影片，深入了解跨裝置量度的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 重要方面和限制{#important-aspects-and-limitations}

請注意與[!UICONTROL Trait Exclusion]相關的以下方面和限制：

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要檢視中的排除特徵 </p> </td>
   <td colname="col2"> <p>排除的特徵<i>不會在「模型摘要」檢視中顯示</i>。 您只能在<b><span class="uicontrol">編輯模型</span></b>工作流程中看到排除的特徵。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>角色型存取控制(RBAC) </p> </td>
   <td colname="col2"> <p>請注意使用<a href="../../features/administration/administration-overview.md#administration"> RBAC</a>的公司的下列限制： </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果您沒有檢視特徵的存取權，您<i>不能</i>選取要從模型中排除的特徵。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果您沒有檢視特徵的存取權，<i>便無法</i>在排除的特徵清單中檢視該特徵。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>在儲存模型後修改排除的特徵 </p> </td>
   <td colname="col2"> <p>建立並儲存模型後，就無法修改排除的特徵。 如果您想要調整結果，可以複製模型並變更排除的特徵。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的特徵數上限 </p> </td>
   <td colname="col2"> <p>您可以從模型中排除的特徵數上限為500。 使用資料夾特徵來最大化排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基線特徵 </p> </td>
   <td colname="col2"> <p>預設會排除基線特徵，因此在建立模型時，它不會顯示在<b><span class="uicontrol">排除</span></b>清單中。 </p> </td>
  </tr>
 </tbody>
</table>

請觀看以下影片，了解從[!UICONTROL Look-Alike Model]排除特定特徵的方式和原因。

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相關連結

* [關於演算法特徵](/help/using/features/algorithmic-models/understanding-models.md)
* [特徵排除 — 教學課程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
