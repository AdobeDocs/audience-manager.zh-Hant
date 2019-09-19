---
description: 「區段績效」報表會依曝光次數和即時區段獨特值比較已映射和未映射的區段。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以進行定位的被忽視區段。
seo-description: 「區段績效」報表會依曝光次數和即時區段獨特值比較已映射和未映射的區段。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以進行定位的被忽視區段。
seo-title: 區段績效報表
solution: Audience Manager
title: 區段績效報表
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 區段績效報表{#segment-performance-report}

「區段績效」報表會依曝光次數和即時區段獨特值比較已映射和未映射的區段。

映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。

比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以進行定位的被忽視區段。

## 使用個案 {#use-cases}

使用報 [!UICONTROL Segment Performance] 表，您可以：

* 識別推動規模或效能的對應受眾細分。
* 根據受眾對過往表現的貢獻，識別未映射的細分，以便在未來的促銷活動中引入。

## 使用區段績效報表 {#using-segment-performance-report}

在和之 **[!UICONTROL Mapped]** 間切 **[!UICONTROL Unmapped]** 換，以選取映射至或未映射至目標的區段。 選取 **[!UICONTROL All]** 以將您的所有區段納入報表。

使用 **日範圍****和日期穿透控制項** ，調整您的回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日。

使用下 **[!UICONTROL Line Item]** 拉式方塊來選取您要傳回資訊的Web屬性。

在下拉 **[!UICONTROL Segment Data Source]** 式方塊中，選取包含您要在報表中檢視之區段的資料來源。

使用下 **[!UICONTROL Segment]** 拉式方塊，選擇您要在報表中看到的區段。

>[!IMPORTANT]
>
>啟用時， [!UICONTROL Audience Optimization for Publishers]您必須包含描述性中繼資料， [!UICONTROL Line Item IDs]如將DFP資料檔案匯 [入Audience manager的步驟3所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 執行此動作後，您可確保報表會以Web屬性而非 [!UICONTROL Line Item] Web屬性的形式詳細說明 [!UICONTROL Line Item ID]。

## 解讀結果 {#interpreting-results}

您 [!UICONTROL Segment Performance] 的報表看起來可能類似以下。 在報表中，按一下泡泡以檢視基礎資料。 請參閱範例報表下表格中的其他資訊說明。

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>區段 </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數字元名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 區段ID </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行項目 </p> </td> 
   <td colname="col2"> <p>您正看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>點擊次數 </p> </td> 
   <td colname="col2"> <p>此特徵的成員點按您Web屬性中項目的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>曝光數 </p> </td> 
   <td colname="col2"> <p>此特徵的成員接觸庫存的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>點進率. </p> <p>此量度會中繼曝光次數的百分比，接著點按。 將點按次數除以印象以取得此度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>即時段填充 </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的獨特訪客的實際數量，以及 <span class="keyword"> Audience Manager看到這些訪客時符合區段資格的訪客</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何閱讀您的對應區段結果 {#read-mapped-segment}

您在報表中映射的區段位置可讓您瞭解哪些區段表現良好，以及您可能需要在何處進行一些調整。

若要閱讀報表，將結果分為四個區段，其中包含虛線（以紅色表示）和下方範例報表中顯示的類別。 範例中的標籤可協助您瞭解區段效能以及如何回應這些結果。

![](assets/publisher_segment_performance_mapped.png)

## 如何閱讀未映射的區段結果 {#read-unmapped-segment}

在報表中查看未映射 [!UICONTROL Segment Performance] 的區段是尋找您未考慮定位的新區段的絕佳方式。 事實上，其中某些區段的表現可能會優於您的對應區段。

若要閱讀此報表，將結果分成四個區段(虛線（以紅色表示）和類別（如下面範例報表所示）。

![](assets/publisher_segment_performance_unmapped.png)
