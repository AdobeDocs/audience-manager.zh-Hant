---
description: 說明可讓您在模型產生器中建立演演算法模型的必要和選用步驟。
keywords: 演演算法運作方式
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: 建立演演算法模型
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# 建立相似模型 {#create-an-algorithmic-model}

說明讓您建立[!UICONTROL Look-Alike Model]的必要和選用步驟。

## 模型產生器區段

[!UICONTROL Model Builder]包含[!UICONTROL Basic Information]和[!UICONTROL Configuration]區段。 若要建立模型，請完成這兩個區段中的必填欄位。 儲存您的模型以啟動演演算法。 [!DNL Audience Manager]會在第一個資料執行完成後傳送自動通知給您。 收到電子郵件後，您可以前往[特徵產生器](../../features/traits/about-trait-builder.md)建立演演算法特徵。

>[!NOTE]
>
>* 如果您建立模型且沒有用它建立任何特徵，則建模程式只會執行一次。
>* 從包含大量資訊的資料來源建立模型。 資料不足的模型將會執行，但不會傳回結果。
>* *請勿*&#x200B;以其他演演算法特徵或區段建立模型。
>* 自動化電子郵件通知只會傳送一次（在第一次資料執行後）。

## 建立模型

請依照下列步驟建置[!UICONTROL Look-Alike Model]：

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然後按一下[!UICONTROL Look-Alike Modeling]區段中的&#x200B;**[!UICONTROL Add New]**。
   ![相似新增](assets/look-alike-add.png)
1. 在[基本資訊](../../features/algorithmic-models/create-model.md#basic-information)區段中
   * 為模型命名。
   * *（選擇性）*&#x200B;提供模型的簡短說明。
   * 將模型的狀態設定為&#x200B;**[!UICONTROL Active]**&#x200B;或&#x200B;**[!UICONTROL Inactive]**。 非使用中的模型將不會執行，也不會產生任何資料。

     ![相似 — 基本](assets/look-alike-basic.png)
1. 在[組態](../../features/algorithmic-models/create-model.md#configuration)區段中：
   * 按一下「**[!UICONTROL Browse All Traits]**」或「**[!UICONTROL Browse All Segments]**」以選取您要用來建立模型的特徵或區段。 依名稱、ID、說明或資料來源搜尋特徵。 在搜尋時按一下資料夾，將結果限制在該資料夾及其子資料夾中。 您也可以依特徵型別（[!UICONTROL Folder Trait]、[!UICONTROL Rule-based]、[!UICONTROL Onboarded]和[!UICONTROL Algorithmic]）或母體型別（[裝置ID](../../reference/ids-in-aam.md)和[跨裝置ID](../../reference/ids-in-aam.md)）來篩選特徵。

     ![瀏覽特徵](assets/browse-traits.png)
   * 選擇30、60或90天的回顧期間。 這會設定模型的時間範圍。
   * 預設會選取[!UICONTROL TraitWeight]演演算法。
   * 從[!UICONTROL Available Data]清單中選取資料來源。
   * 完成時，按一下&#x200B;**[!UICONTROL Save]**。

     ![相似組態](assets/look-alike-configuration.png)

請觀看下方的影片，詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=zh-Hant)

## 演演算法模型的基本資訊 {#basic-information}

<!-- r_model_basic.xml -->

在[!UICONTROL Model Builder]中，[!UICONTROL Basic Information]設定可讓您建立新模型或編輯現有模型。 若要建立新模型，請提供名稱並移至[!UICONTROL Configuration]設定。 說明欄位是選用欄位。

| 欄位 | 說明 |
|---|---|
| **[!UICONTROL Name]** | 為您的模型提供一個簡短的邏輯名稱，用以描述其功能或用途。 避免使用縮寫、特殊字元和強調符號。 |
| **[!UICONTROL Description]** | 有關模型的其他描述性資訊的欄位。 |
| **[!UICONTROL Status]** | 啟動或停用模型（預設為啟動）。 |

## 設定 {#configuration}

在[!UICONTROL Model Builder]中，[!UICONTROL Configuration]區段可讓您新增特徵或區段至模型。 在此區段中，選取基線特徵或區段、回顧期間以及來自第一方和第三方資料來源的資料。

<!-- r_model_configuration.xml -->

### 必備條件

請先完成[!UICONTROL Basic Information]區段中的必填欄位。

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
   <td colname="col2"> <p>按一下特徵或區段按鈕，即可檢視所有特徵或區段的清單。 您選取的區段或特徵會成為系統演演算法用來建立模型的基準。 </p> <p> <p><b>注意</b>：選取已上線特徵、規則型特徵或區段作為基準。 否則，您的模型將不會執行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選取回顧期間(2)</b> </p> </td> 
   <td colname="col2"> <p>設定模型的時間範圍。 根據您的選擇，演演算法會包含並評估過去30、60或90天的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選取演演算法(3)</b> </p> </td> 
   <td colname="col2"> <p>目前，模型產生器僅能搭配我們專屬的<span class="keyword">特徵權重</span>演演算法使用。 <span class="keyword">Audience Manager</span>可能在後續發行版本中新增其他演演算法函式。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>從Data Source (4)選取模型資料</b> </p> </td> 
   <td colname="col2"> <p>可讓您選取要在模型中使用的第一方和第三方資料來源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除專案(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以從您選取用來建立模型的資料來源中排除特徵。 使用<span class="wintitle">排除專案</span>清單並閱讀<a href="../../features/algorithmic-models/trait-exclusion-algo-models.md">演演算法模型：特徵排除專案</a>以瞭解更多資訊。 </p> </td>
  </tr> 
 </tbody>
</table>

觀看以下影片，瞭解如何建立第一方相似模型，以便找出更多看起來像您轉換器的人造訪客。

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [瞭解TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
