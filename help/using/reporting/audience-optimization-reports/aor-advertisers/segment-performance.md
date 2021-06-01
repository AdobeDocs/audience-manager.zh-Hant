---
description: 「區段效能」報表會依曝光次數和轉換率來比較已對應和未對應的區段。 對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。 在報表內和報表之間比較這些不同的區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以鎖定目標的被忽視區段。
seo-description: 「區段效能」報表會依曝光次數和轉換率來比較已對應和未對應的區段。 對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。 在報表內和報表之間比較這些不同的區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以鎖定目標的被忽視區段。
seo-title: 區段成效報表
solution: Audience Manager
title: 區段成效報表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: 受眾最佳化報表
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# 區段成效報表{#segment-performance-report}

[!UICONTROL Segment Performance]報表會依曝光次數和轉換率來比較已對應和未對應的區段。 對應區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地以進行定位的區段。 在報表內和報表之間比較這些不同的區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以鎖定目標的被忽視區段。

## 如何閱讀對應的區段結果{#read-mapped-segment-results}

映射的[!UICONTROL Segment Performance]報告顯示您建立併發送到目標的所有段。在報告中映射段的位置可以告訴您許多關於哪些段表現良好以及可能需要進行一些調整的資訊。

若要閱讀報表，可協助將結果分成4個區段，內含虛線（以紅色表示）和下方範例報表中顯示的類別。

![](assets/mapped-segment-performance.png)

範例和下表中的標籤可協助您了解區段效能，以及如何回應這些結果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>轉換率良好。 </p> <p>您可以增加曝光次數，以獲得更多轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>低轉換率。 </p> <p>您可能不想定位這些區段。 本節中的區段非常適合與未對應區段結果中的區段進行比較。 某些未對應的區段可能會比您已定位的區段執行得更好。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上角</b> </p> </td> 
   <td colname="col2"> <p>表現強勁。 不要管這些區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下角</b> </p> </td> 
   <td colname="col2"> <p>低轉換率和高曝光率。 </p> <p>此區段中的區段表現不佳。 您可能想要將預算從這些區段移至報表左上像限中的區段。 這有助於減少曝光次數，並且有助於改善右下角區段的區段轉換率。 此外，將這些對應區段與您未對應的區段進行比較。 某些未對應的區段可能會比您已定位的區段執行得更好。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何閱讀未映射的段結果{#read-unmapped-segment-results}

在[!UICONTROL Segment Performance]報表中查看未對應的區段，是尋找尚未考慮進行鎖定的新區段的好方法。 事實上，其中某些區段的表現可能會優於對應區段。 這是因為未對應的區段必須符合要納入此報表的一組資格標準。 若要納入此報表，未對應的區段必須：

* 轉換次數大於所有對應區段的平均值。
* 依轉換率位列前100個未對應區段。

若要閱讀此報告，可協助將結果分成4個區段，內含虛線（以紅色表示）和下方範例報告中顯示的類別。

![](assets/unmapped-segment-performance.png)

在此報告中，您只想聚焦在左上方未對應的區段。 與其他三個區段中的區段相比，這些未映射的區段顯示出較高的轉換率，具有低曝光次數。

>[!NOTE]
>
>7天和30天回顧期間僅適用於星期日&#x200B;**[!UICONTROL Date Through]**&#x200B;日期。
