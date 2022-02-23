---
description: 描述在模型生成器中建立算法模型所需的和可選的步驟。
keywords: 阿爾戈如何工作
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: 建立算法模型
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 1%

---

# 建立相似模型 {#create-an-algorithmic-model}

介紹建立 [!UICONTROL Look-Alike Model]。

## 模型生成器部分

[!UICONTROL Model Builder] 由 [!UICONTROL Basic Information] 和 [!UICONTROL Configuration] 的下界。 要建立模型，請完成這兩個部分中的必填欄位。 保存模型以啟動算法。 [!DNL Audience Manager] 在第一次資料運行完成後向您發送自動通知。 收到電子郵件後，您可以 [特性生成器](../../features/traits/about-trait-builder.md) 創造算法特徵。

>[!NOTE]
>
>* 如果建立模型且不使用該模型構建任何特徵，則建模過程只運行一次。
>* 從包含大量資訊的資料源構建模型。 資料不足的模型將運行，但不會返回結果。
>* *不要* 建立具有其他算法特徵或片段的模型。
>* 自動電子郵件通知僅發送一次（在第一次資料運行後）。


## 構建模型

按照以下步驟構建 [!UICONTROL Look-Alike Model]:

1. 轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** 按一下 **[!UICONTROL Add New]** 的 [!UICONTROL Look-Alike Modeling] 的子菜單。
   ![外觀相似](assets/look-alike-add.png)
1. 在 [基本資訊](../../features/algorithmic-models/create-model.md#basic-information) 節
   * 命名模型。
   * *（可選）* 提供有關模型的簡要說明。
   * 將模型的狀態設定為 **[!UICONTROL Active]** 或 **[!UICONTROL Inactive]**。 非活動模型將不運行，不會生成任何資料。
      ![長相相似](assets/look-alike-basic.png)
1. 在 [配置](../../features/algorithmic-models/create-model.md#configuration) 部分：
   * 按一下 **[!UICONTROL Browse All Traits]** 或 **[!UICONTROL Browse All Segments]** 選擇要建模的特性或段。 按名稱、ID、說明或資料源搜索特徵。 在搜索時按一下資料夾，將結果限制到該資料夾及其子資料夾。 您還可以按特徵類型篩選特徵([!UICONTROL Folder Trait]。 [!UICONTROL Rule-based]。 [!UICONTROL Onboarded], [!UICONTROL Algorithmic])或人口類型([設備ID](../../reference/ids-in-aam.md) 和 [跨設備ID](../../reference/ids-in-aam.md))。
      ![瀏覽特徵](assets/browse-traits.png)
   * 選擇30、60或90天回顧期。 這為模型設定時間範圍。
   * 的 [!UICONTROL TraitWeight] 算法是預設選擇的。
   * 從 [!UICONTROL Available Data] 清單框。
   * 按一下 **[!UICONTROL Save]** 完成。
      ![外觀相似的配置](assets/look-alike-configuration.png)

觀看下面的視頻，詳細瞭解跨設備指標的工作原理。

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 算法模型的基本資訊 {#basic-information}

<!-- r_model_basic.xml -->

在 [!UICONTROL Model Builder]，也請參見Wiki頁。 [!UICONTROL Basic Information] 設定允許您建立新模型或編輯現有模型。 要建立新模型，請提供名稱並轉到 [!UICONTROL Configuration] 的子菜單。 說明欄位為可選欄位。

| 欄位 | 說明 |
|---|---|
| **[!UICONTROL Name]** | 為模型提供一個描述其功能或用途的簡短邏輯名稱。 避免縮寫、特殊字元和重音標籤。 |
| **[!UICONTROL Description]** | 有關模型的附加說明性資訊的欄位。 |
| **[!UICONTROL Status]** | 激活或停用模型（預設情況下為活動）。 |

## 設定 {#configuration}

在 [!UICONTROL Model Builder]，也請參見Wiki頁。 [!UICONTROL Configuration] 部分，用於向模型添加特徵或段。 在本節中，選擇基線特性或段、回溯期間以及來自第一和第三方資料源的資料。

<!-- r_model_configuration.xml -->

### 必要條件

完成 [!UICONTROL Basic Information] 的雙曲餘切值。

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
   <td colname="col1"> <p><b>選擇基線特性或段(1)</b> </p> </td> 
   <td colname="col2"> <p>按一下特徵或段按鈕可查看所有特徵或段的清單。 所選段或特徵將成為系統算法用於建模的基線。 </p> <p> <p><b>注釋</b>:選擇帶掛的特性、基於規則的特性或段作為基線。 否則，您的模型將不運行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選擇回溯期間(2)</b> </p> </td> 
   <td colname="col2"> <p>設定模型的時間範圍。 根據您的選擇，算法將包括並評估前30、60或90天的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>選擇算法(3)</b> </p> </td> 
   <td colname="col2"> <p>此時， Model Builder與我們的專有 <span class="keyword"> 特質權重</span> 僅限算法。 <span class="keyword"> Audience Manager</span> 可以在後續版本中添加其他算法函式。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>從資料源中選擇模型資料(4)</b> </p> </td> 
   <td colname="col2"> <p>用於選擇要在模型中使用的第一和第三方資料源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除(5)</b> </p> </td> 
   <td colname="col2"> <p>可以從為建模選擇的資料源中排除特徵。 使用 <span class="wintitle"> 排除</span> 清單和讀取 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 算法模型：特性排除</a> 來瞭解更多資訊。 </p> </td>
  </tr> 
 </tbody>
</table>

觀看下面的視頻，瞭解如何建立第一個與派對外觀相似的模型，以便您能夠找到更多與轉換器外觀相似的訪客。

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [瞭解特質權重](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

