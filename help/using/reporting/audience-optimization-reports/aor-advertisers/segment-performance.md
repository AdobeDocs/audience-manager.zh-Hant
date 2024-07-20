---
description: 「區段效能」報表可依曝光次數和轉換率，比較已對應和未對應的區段。 對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。 比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以用於鎖定目標的被忽略區段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 區段績效報表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# 區段績效報表{#segment-performance-report}

[!UICONTROL Segment Performance]報表會依據曝光次數和轉換率，比較對應和未對應的區段。 對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。 比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以用於鎖定目標的被忽略區段。

## 如何讀取對應的區段結果 {#read-mapped-segment-results}

對應[!UICONTROL Segment Performance]報表會顯示您建立並傳送至目標目的地的所有區段。您對映區段在報表中的位置可以告知您哪些區段表現良好，以及您可能需要在何處做出一些調整。

若要閱讀報表，它有助於將結果分成4個區段，其虛線（紅色）與下列範例報表中顯示的類別。

![](assets/mapped-segment-performance.png)

範例和下表中的標籤可協助您瞭解區段效能，以及如何回應這些結果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上方</b> </p> </td> 
   <td colname="col2"> <p>良好的轉換率。 </p> <p>您可以透過增加曝光次數來取得更多轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下方</b> </p> </td> 
   <td colname="col2"> <p>低轉換率。 </p> <p>您可能會想要避免鎖定這些區段。 本節中的區段是用來與未對應區段結果中區段進行比較的絕佳候選區段。 您的部分未對應區段可能會比已鎖定的區段表現更好。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上方</b> </p> </td> 
   <td colname="col2"> <p>強大的效能。 請保留這些區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下方</b> </p> </td> 
   <td colname="col2"> <p>低轉換率和高曝光率。 </p> <p>此區段中的區段表現不佳。 您可能會想要將預算從這些區段移開，並移至報表左上象限中的區段。 這有助於減少曝光數，也有助於改善此右下角區段中區段的轉換率。 此外，將這些對應的區段與未對應的區段進行比較。 您的部分未對應區段可能會比已鎖定的區段表現更好。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何讀取未對應的區段結果 {#read-unmapped-segment-results}

在[!UICONTROL Segment Performance]報表中檢視未對應的區段，是尋找您未考慮用於鎖定目標的新區段的好方法。 事實上，其中一些區段的表現可能會優於對應的區段。 這是因為未對應的區段必須符合要納入此報表的一組資格條件。 若要納入此報表，未對應的區段必須：

* 轉換次數大於所有對應區段的平均數。
* 依轉換率排列在前100個未對應區段中。

若要閱讀此報表，它有助於將結果分成4個區段，其虛線（紅色）和類別如下面的範例報表所示。

![](assets/unmapped-segment-performance.png)

在此報表中，您只需將焦點置於左上角那些未對應的區段。 相較於其他三個區段中的區段，這些未對應的區段在低曝光次數下顯示高轉換率。

>[!NOTE]
>
>7天和30天回顧期間僅適用於星期日&#x200B;**[!UICONTROL Date Through]**&#x200B;日期。
