---
description: 說明可讓您在Model Builder中建立演算法模型的必要和可選步驟。
keywords: algo how works
seo-description: 說明可讓您在Model Builder中建立演算法模型的必要和可選步驟。
seo-title: 建立演算法模型
solution: Audience Manager
title: 建立演算法模型
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 建立演算法模型 {#create-an-algorithmic-model}

說明可讓您在中建立演算模型的必要和選用步驟 [!UICONTROL Model Builder]。

## 建立模型 {#build-model}

<!-- t_model_build.xml -->

### 模型產生器區段

[!UICONTROL Model Builder] 包含和 [!UICONTROL Basic Information] 節 [!UICONTROL Configuration] 。 要建立模型，請完成這兩個節中的必需欄位。 儲存模型以啟動演算法。 [!DNL Audience Manager] 在第一次資料執行完成後傳送自動通知給您。 收到電子郵件後，您可以前往「特徵產生器」 [並建立演算法特徵](../../features/traits/about-trait-builder.md) 。

>[!NOTE]
>
>* 如果您建立模型且不使用模型建立任何特徵，則模型程式只會執行一次。
>* 從包含大量資訊的資料來源建立模型。 資料不足的模型會執行，但不會傳回結果。
>* *請勿使用* 其他演算法特徵或區段建立模型。
>* 自動化電子郵件通知只會傳送一次（在第一次資料執行後）。


### 建立模型

若要建立模型，請前往區段， [!UICONTROL Models] 然後按一 **[!UICONTROL Add New]** 下並遵循下列步驟：

1. 在「基 [本資訊」部分](../../features/algorithmic-models/create-model.md#basic-information)
   * 命名模型。
   * *（可選）* ，提供模型的簡要說明。
   * 將模型的狀態設定為 **[!UICONTROL Active]** 或 **[!UICONTROL Inactive]**。 非活動模型將不運行，也不會生成任何資料。
1. 在「配 [置](../../features/algorithmic-models/create-model.md#configuration) 」部分：
   * 按一 **[!UICONTROL Browse All Traits]** 下或 **[!UICONTROL Browse All Segments]** 以選取您要建立模型的特徵或區段。 選取已登入的特徵、規則型特徵或區段作為基準。 否則，您的模型將不運行。
   * 選擇30、60或90天回顧時段。 這會設定模型的時間範圍。
   * 預設 [!UICONTROL TraitWeight] 會選取演算法。
   * 從清單中選取資料 [!UICONTROL Available Data] 來源。
   * Click **[!UICONTROL Save]** when done.

## 演算模型的基本資訊 {#basic-information}

<!-- r_model_basic.xml -->

在中 [!UICONTROL Model Builder]，設 [!UICONTROL Basic Information] 定可讓您建立新模型或編輯現有模型。 要建立新模型，請提供名稱並移至設 [!UICONTROL Configuration] 置。 說明欄位為選用。

| 欄位 | 說明 |
|---|---|
| **[!UICONTROL Name]** | 為模型提供簡短的邏輯名稱，以說明其功能或用途。 避免縮寫、特殊字元和重音符號。 |
| **[!UICONTROL Description]** | 一個欄位，用於有關模型的其他描述性資訊。 |
| **[!UICONTROL Status]** | 激活或停用模型（預設情況下為活動）。 |

## 設定 {#configuration}

在中 [!UICONTROL Model Builder]，區 [!UICONTROL Configuration] 段可讓您新增特徵或區段至模型。 在本節中，選取基準特徵或區段、回顧期間，以及來自您第一方與第三方資料來源的資料。

<!-- r_model_configuration.xml -->

### 必備條件

請先填妥章節中的 [!UICONTROL Basic Information] 必填欄位。

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>選取基準特徵或區段(1)</b> </p> </td> 
   <td colname="col2"> <p>按一下特徵或區段按鈕，即可查看您所有特徵或區段的清單。 您選取的區段或特徵會成為系統演算法用於建模的基準。 </p> <p> <p><b>注意</b>: 選取已登入的特徵、規則型特徵或區段作為基準。 否則，您的模型將不運行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選擇回顧期間(2)</b> </p> </td> 
   <td colname="col2"> <p>設定模型的時間範圍。 根據您的選擇，演算法會包含並評估前30、60或90天的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選擇演算法(3)</b> </p> </td> 
   <td colname="col2"> <p>目前，Model Builder僅能與我們專屬的「特徵 <span class="keyword"> 加權</span> 」演算法搭配使用。 <span class="keyword"> Audience Manager</span> 可能會在後續版本中新增其他演算功能。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>從資料源中選擇模型資料(4)</b> </p> </td> 
   <td colname="col2"> <p>可讓您選取想要在模型中使用的第一方和第三方資料來源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以從選取的模型資料來源中排除特徵。 使用「排 <span class="wintitle"> 除」清單</span> ，並閱讀「演算法 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 模型：特徵排除</a> ，瞭解更多資訊。 </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [瞭解特徵權重](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

