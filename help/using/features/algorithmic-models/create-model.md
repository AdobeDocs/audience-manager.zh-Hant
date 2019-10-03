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
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

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
>* 從包含大量資訊的資料來源建立模型。 Models with insufficient data will run, but they will not return results.
>* *Do not create models with other algorithmic traits or segments.*
>* 自動化電子郵件通知只會傳送一次（在第一次資料執行後）。


### Build the Model

To build a model, go to the  section and click  and follow the steps below:[!UICONTROL Models]**[!UICONTROL Add New]**

1. In the Basic Information section[](../../features/algorithmic-models/create-model.md#basic-information)
   * Name the model.
   * *(Optional) Provide a brief description about the model.*
   * Set the status for the model to  or . **[!UICONTROL Active]****[!UICONTROL Inactive]** Inactive models will not run and will not produce any data.
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
| **[!UICONTROL Description]** | A field for additional descriptive information about the model. |
| **[!UICONTROL Status]** | Activates or deactivates the model (active by default). |

## 設定 {#configuration}

In , the  section lets you add traits or segments to the model. [!UICONTROL Model Builder][!UICONTROL Configuration]In this section, select a baseline trait or segment, a look-back period, and data from your first and third-party data sources.

<!-- r_model_configuration.xml -->

### 必備條件

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col1"> <p><b>Select a Baseline Trait or Segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Click the trait or segment button to see a list of all your traits or segments. Your selected segment or trait becomes the baseline that the system algorithms use for modeling. </p> <p> <p><b>注意</b>:選取已登入的特徵、規則型特徵或區段作為基準。 否則，您的模型將不運行。 </p> </p> </td> 
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
   <td colname="col2"> <p>You can exclude traits from the data sources you selected for modeling. 使用「排 <span class="wintitle"> 除」清單</span> ，並閱讀「演算法 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 模型：特徵排除</a> ，瞭解更多資訊。 </p> </td>
  </tr> 
 </tbody>
</table>

Watch the video below to learn how to create a first party look-alike model, so that you can find more of your own visitors who look like your converters.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=chi_hant)

>[!MORE_LIKE_THIS]
>
>* [瞭解特徵權重](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

