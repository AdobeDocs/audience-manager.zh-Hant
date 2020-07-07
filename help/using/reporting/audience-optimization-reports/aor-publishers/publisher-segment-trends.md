---
description: 「區段趨勢」報表會傳回一段時間內已映射和未映射區段的曝光次數和點進率資料。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較所選量度的趨勢和數量，以更清楚地瞭解受眾隨時間的行為。
seo-description: 「區段趨勢」報表會傳回一段時間內已映射和未映射區段的曝光次數和點進率資料。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較所選量度的趨勢和數量，以更清楚地瞭解受眾隨時間的行為。
seo-title: 區段區段報表
solution: Audience Manager
title: 區段區段報表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---


# 區段區段報表{#segment-trend-report}

「區段趨勢」報表會傳回一段時間內已映射和未映射區段的曝光次數和點進率資料。

映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。

比較所選量度的趨勢和數量，以更清楚地瞭解受眾隨時間的行為。

## 使用案例 {#use-cases}

使用報 [!UICONTROL Segment Trend] 表來驗證區段隨時間的效能，並根據強大的效能或規模找出趨勢。

透過此報告，您可以瞭解哪些Web屬性顯示下降或錯誤增加，並視需要進行疑難排解。 此報告是您識別對報表感興趣的受眾後的下一步 [!UICONTROL Segment Performance] ，以確保您在標籤中看到的強弱 [!UICONTROL Segment Performance] 績效隨時間而一致。

## 使用區段趨勢報表 {#using-the-report}

在和之 **[!UICONTROL Mapped]** 間切 **[!UICONTROL Unmapped]** 換，以選取映射至或未映射至目標的區段。 選取 **[!UICONTROL All]** 以將您的所有區段納入報表。

使用滑桿調整回顧視 **[!UICONTROL Date Through]** 窗。

按一下滑桿下方的任 **[!UICONTROL Date Through]** 一區段，即可顯示選項，僅保留該區段在報表中或排除它。

使用下 **[!UICONTROL Line Item]** 拉式方塊，選取您要傳回資訊的作品集中的屬性。

在下拉 **[!UICONTROL Segment Data Source]** 式方塊中，選取包含您要在報表中檢視之區段的資料來源。

使用下 **[!UICONTROL Segment]** 拉式方塊，選擇您要在報表中看到的區段。

>[!IMPORTANT]
>
>啟用時， [!UICONTROL Audience Optimization for Publishers]您必須包含ID的描述性中繼資料，如 [!UICONTROL Line Item] Import Google Ad Manager（舊稱DFP）Data Files Into Audience Manager的步驟3所述 [](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 執行此動作後，您可確保報表會以ID而非ID的形式詳細 [!UICONTROL Line Item] 說明Web屬 [!UICONTROL Line Item] 性。

## 解讀結果 {#interpreting-results}

報 [!UICONTROL Segment Trend] 表僅會在14天間隔內以折線圖傳回資料。 在此範例中，報表會顯示一組映射和未映射區段的曝光和點進趨勢。

將滑鼠指標暫留在任何線條上，以取得該特定區段趨勢的詳細資訊。 請參閱範例報表下表格中的其他資訊說明。

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段</span> </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數字元名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段ID</span> </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 行項目</span> </p> </td> 
   <td colname="col2"> <p>您正看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 點擊次數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員點按您Web屬性中項目的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員接觸庫存的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>點進率. 此量度會中繼曝光次數的百分比，接著點按。 將點按次數除以曝光次數，以取得此度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段唯一客戶</span> </p> </td> 
   <td colname="col2"> <p>最近30天內的區段成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
