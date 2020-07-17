---
description: 「區段績效」報表會依印象和轉換率比較映射和未映射的區段。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想傳送至目的地以進行定位的被忽視區段。
seo-description: 「區段績效」報表會依印象和轉換率比較映射和未映射的區段。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想要傳送至目的地以進行定位的被忽視區段。
seo-title: 區段成效報表
solution: Audience Manager
title: 區段成效報表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# 區段成效報表{#segment-performance-report}

報表 [!UICONTROL Segment Performance] 會依印象和轉換率比較映射和未映射的區段。 映射區段是您建立並傳送至目的地以進行定位的區段。 未映射區段是您已建立但尚未傳送至目標的區段。 比較報表內和報表之間的這些不同區段類型，可協助您最佳化現有的促銷活動，並找出您可能想傳送至目的地以進行定位的被忽視區段。

## 如何閱讀您的對應區段結果 {#read-mapped-segment-results}

對應報 [!UICONTROL Segment Performance] 表會顯示您建立並傳送至目的地以進行定位的所有區段。報表中對應區段的位置可告訴您許多區段的效能良好，以及您可能需要在何處進行一些調整。

若要閱讀報表，它可協助將結果分為4個區段，其中包含虛線（以紅色表示）和下方範例報表中顯示的類別。

![](assets/mapped-segment-performance.png)

範例和下表中的標籤可協助您瞭解區段效能以及如何回應這些結果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>良好的轉換率。 </p> <p>您可以透過增加印象，獲得更多轉化率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>低轉換率。 </p> <p>您可能想要避免定位這些區段。 本節中的區段是比較未映射區段結果的最佳候選項目。 部分未映射的區段可能比您已定位的區段效能更好。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上方</b> </p> </td> 
   <td colname="col2"> <p>強大的效能。 不要管這些區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下角</b> </p> </td> 
   <td colname="col2"> <p>低轉換率和高印象。 </p> <p>本節中的區段表現不佳。 您可能想要將預算從這些區段移至報表左上方像限的區段。 這將有助於減少印象，並有助於改善右下角區段的轉換率。 此外，請比較這些映射區段與您未映射的區段。 部分未映射的區段可能比您已定位的區段效能更好。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何閱讀未映射的區段結果 {#read-unmapped-segment-results}

在報表中查看未映射 [!UICONTROL Segment Performance] 的區段是尋找您未考慮定位的新區段的絕佳方式。 事實上，其中某些區段的表現可能會優於您的對應區段。 這是因為未映射的區段必須符合要納入此報表的一組資格標準。 若要納入此報表，未映射的區段必須：

* 轉換率高於所有映射區段的平均值。
* 依轉換率位列前100個未映射區段。

若要閱讀此報告，它可協助將結果分為4個區段，其中虛線（以紅色表示）和類別顯示在下方的範例報告中。

![](assets/unmapped-segment-performance.png)

在此報表中，您只想專注在左上角區段中未映射的區段。 與其他三個區段中的區段相比，這些未映射區段顯示高轉換率，以呈現低印象。

>[!NOTE]
>
>7天和30天回顧期限僅適用於星期日 **[!UICONTROL Date Through]** 。
