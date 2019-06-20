---
description: 說明可讓您在Model Builder中建立演算法模型的必要和選擇性步驟。
keywords: algo how work
seo-description: 說明可讓您在Model Builder中建立演算法模型的必要和選擇性步驟。
seo-title: 建立演算法模型
solution: Audience Manager
title: 建立演算法模型
topic: DIL API
uuid: cf4fc4e-cf92-445f-b2 d9-71c3 ca624 e26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### 模型產生器區段

[!UICONTROL Model Builder] 包含 [!UICONTROL Basic Information] 和 [!UICONTROL Configuration] 區段。若要建立模型，請完成這兩個區段中的必填欄位。儲存模型以開始演算法。[!DNL Audience Manager] 在第一個資料執行完成後，會傳送自動通知給您。After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* 模型程序只會在您建立模型且不建立任何特性時執行一次。
>* 從包含有意義資訊的資料來源建立模型。資料不足的模型會執行，但不會傳回結果。
>* *請勿* 使用其他演算法特徵或區段建立模型。
>* 自動電子郵件通知只會傳送一次(在第一次執行資料後)。


### 建立模型

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * 命名模型。
   * *(可選)* 提供關於模型的簡短說明。
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. 非活動中模型不會執行，也不會產生任何資料。
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. 選取已登錄特徵、規則型特徵或區段作為基準。否則，您的模型將無法執行。
   * 選擇30、60或90天回顧期間。這會設定模型的時間範圍。
   * [!UICONTROL TraitWeight] 預設會選取演算法。
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. 描述欄位為選用欄位。

| 欄位 | 說明 |
|---|---|
| **[!UICONTROL Name]** | 為您的模型提供描述其函數或用途的簡短邏輯名稱。避免縮寫、特殊字元和附註標記。 |
| **[!UICONTROL Description]** | 欄位，以取得有關模型的其他描述性資訊。 |
| **[!UICONTROL Status]** | 啓用或停用模型(預設為作用中)。 |

## 設定 {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. 在本節中，選取一個基準特徵或區段、回顧時段以及來自第一方和第三方資料來源的資料。

<!-- r_model_configuration.xml -->

### 必備條件

Complete the required fields in the [!UICONTROL Basic Information] section first.

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
   <td colname="col1"> <p><b>選取基線特徵或區段(1)</b> </p> </td> 
   <td colname="col2"> <p>按一下特徵或群體按鈕，查看您所有特徵或區段的清單。您選取的區段或特徵會變成系統演算法用於模型的基準。 </p> <p> <p><b>注意</b>：選取已登錄特徵、規則型特徵或區段作為基準。否則，您的模型將無法執行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選取回顧時段(2)</b> </p> </td> 
   <td colname="col2"> <p>設定模型的時間範圍。演算法根據您的選擇，包含並評估前30、60或90天的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選擇演算法(3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> 可在後續版本中新增其他演算法函數。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>從資料來源(4)選取模型資料</b> </p> </td> 
   <td colname="col2"> <p>可讓您選取要在模型中使用的第一方和第三方資料來源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以從選擇用於模型的資料來源中排除特徵。Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_贊_ this]
>
>* [瞭解TritWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

