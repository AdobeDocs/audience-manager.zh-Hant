---
description: 「區段效能」報表可依曝光次數和即時區段不重複來比較已對應和未對應的區段。 對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。 比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以用於鎖定目標的被忽略區段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 發佈者的區段效能報表
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# 區段績效報表{#segment-performance-report}

「區段效能」報表可依曝光次數和即時區段不重複來比較已對應和未對應的區段。

對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。

比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以用於鎖定目標的被忽略區段。

## 使用個案 {#use-cases}

透過[!UICONTROL Segment Performance]報告，您可以：

* 識別帶動規模或效能的對應受眾區段。
* 根據對象對過去績效的貢獻，識別要在未來行銷活動中引入的未對應區段。

## 使用區段績效報表 {#using-segment-performance-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之間切換以選取是否對應到目的地的區段。 選取「**[!UICONTROL All]**」以在報告中包含您的所有區段。

使用&#x200B;**日期範圍**&#x200B;和&#x200B;**日期到**&#x200B;控制項來調整您的回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉式方塊來選取您要傳回資訊的Web屬性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉式方塊中，選取包含您要在報表中檢視之區段的資料來源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉式方塊來選取您想在報告中檢視哪些區段。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Line Item IDs]的描述性中繼資料，如[將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3中所述。 透過這樣做，您可以確保報告將Web屬性詳細資料顯示為[!UICONTROL Line Item]，而不是[!UICONTROL Line Item ID]。

## 解譯結果 {#interpreting-results}

您的[!UICONTROL Segment Performance]報告可能類似於下面的報告。 在報表中，按一下泡泡圖以檢視基礎資料。 如需範例報表下表中其他資訊的說明，請參閱。

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
   <td colname="col1"> <p>區段ID </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>條列專案 </p> </td> 
   <td colname="col2"> <p>您要檢視此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>點按次數 </p> </td> 
   <td colname="col2"> <p>此特徵的成員已按一下您Web屬性中的專案的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>曝光數 </p> </td> 
   <td colname="col2"> <p>此特徵的成員已向您的詳細目錄公開的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>點進率。 </p> <p>此量度會轉送曝光次數百分比，接著再按一下。 將點按數除以曝光數，即可取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>即時區段人口數 </p> </td> 
   <td colname="col2"> <p>指定時間範圍內即時檢視的實際不重複訪客數量，以及在<span class="keyword"> Audience Manager</span>看到符合區段資格的人數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何讀取對應的區段結果 {#read-mapped-segment}

報表中對應區段的位置可告知您哪些區段表現良好，以及您可能需要在何處做出某些調整。

若要閱讀報表，將結果分成四個區段，並使用虛線（紅色）和下列範例報表中所顯示的類別，這樣會有所幫助。 範例中的標籤可協助您瞭解區段效能，以及如何回應這些結果。

![](assets/publisher_segment_performance_mapped.png)

## 如何讀取未對應的區段結果 {#read-unmapped-segment}

在[!UICONTROL Segment Performance]報表中檢視未對應的區段，是尋找您未考慮用於鎖定目標的新區段的好方法。 事實上，其中一些區段的表現可能會優於對應的區段。

若要閱讀此報表，將結果分成四個區段會有所幫助，其中虛線（紅色）和類別會顯示於以下範例報表中。

![](assets/publisher_segment_performance_unmapped.png)
