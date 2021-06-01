---
description: 「區段趨勢」報表會傳回一段時間中，已對應和未對應區段的曝光次數和點進率資料。 對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。 比較所選量度的趨勢和數量，以更清楚掌握受眾隨時間的行為。
seo-description: 「區段趨勢」報表會傳回一段時間中，已對應和未對應區段的曝光次數和點進率資料。 對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。 比較所選量度的趨勢和數量，以更清楚掌握受眾隨時間的行為。
seo-title: 區段區段報表
solution: Audience Manager
title: 區段區段報表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: 受眾最佳化報表
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# 區段區段報表{#segment-trend-report}

「區段趨勢」報表會傳回一段時間中，已對應和未對應區段的曝光次數和點進率資料。

對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。

比較所選量度的趨勢和數量，以更清楚掌握受眾隨時間的行為。

## 使用案例 {#use-cases}

使用[!UICONTROL Segment Trend]報表來驗證區段在一段時間內的效能，並根據強效能或規模來找出趨勢。

透過此報表，您可以了解哪些Web屬性顯示下降或錯誤增加，並視需要進行疑難排解。 此報表是您在[!UICONTROL Segment Performance]報表中識別感興趣對象後的下一步，以確保您在[!UICONTROL Segment Performance]標籤中看到的強或弱績效隨著時間而一致。

## 使用區段趨勢報表{#using-the-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之間切換，以選取已對應或未對應至目的地的區段。 選取&#x200B;**[!UICONTROL All]**&#x200B;以在報表中包含您的所有區段。

使用&#x200B;**[!UICONTROL Date Through]**&#x200B;滑桿調整回顧視窗。

按一下&#x200B;**[!UICONTROL Date Through]**&#x200B;滑桿下方的任何區段，即可開啟選項以僅保留報表中的該區段或將其排除。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉框選擇要返回資訊的產品組合中的屬性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉式方塊中，選取包含您要在報表中查看之區段的資料來源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉式方塊，選取您要在報表中查看的區段。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Line Item] ID的描述性中繼資料，如[將Google Ad Manager（前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3所述。 通過執行此操作，您可以確保報告將Web屬性詳細資訊為[!UICONTROL Line Item]，而不是[!UICONTROL Line Item] ID。

## 解釋結果{#interpreting-results}

[!UICONTROL Segment Trend]報表只會在14天間隔內傳回折線圖中的資料。 在此範例中，報表會顯示一組已對應和未對應區段的曝光數和點進趨勢。

將滑鼠指標暫留在任何線條上，以取得該特定區段趨勢的詳細資訊。 如需詳細資訊，請參閱範例報表下表的說明。

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
   <td colname="col2"> <p>您指派給此區段的字母數字名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段ID</span> </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 行項目</span> </p> </td> 
   <td colname="col2"> <p>您看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 點擊次數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員點按Web屬性中項目的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員接觸到您詳細目錄的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>點進率. 此量度會中繼曝光次數的百分比，接著點按。 將點按次數除以曝光數來取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段不重複值</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的區段成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
