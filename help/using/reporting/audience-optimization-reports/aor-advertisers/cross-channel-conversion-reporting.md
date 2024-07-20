---
description: 「Audience Optimization」報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---

# 跨通道轉換{#cross-channel-conversion}

「Audience Optimization」報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。

[!UICONTROL Cross Channel Conversion]報告結合來自[!DNL Google Campaign Manager]平台的結果與[!DNL Audience Manager]轉換特徵。 這可讓您將離線轉換連結至線上曝光數或點按數。

您可以將[!UICONTROL Cross Channel Conversion]用於[區段效能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)和[最佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)報告。

若要檢視[!UICONTROL Cross Channel Conversion]報告，請在&#x200B;**[!UICONTROL Platform]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL AAM + Ad Server Name]**&#x200B;專案。

下表列出設定[!UICONTROL Cross Channel Conversion]時的重要考量：

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 考量事項 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>轉換特徵的最小數量 </p> </td> 
   <td colname="col1"> <p>必須至少將一個轉換特徵指派給資料來源，才能執行<span class="wintitle">跨管道轉換</span>報告。 如需特徵的詳細資訊，請參閱特徵</a>的<a href="../../../features/traits/create-onboarded-rule-based-traits.md">基本資訊。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>歸因期間 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google促銷活動管理員</span></b>歸因期間為14天，這表示系統只會考量過去兩週展示的轉換特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>使用者在轉換前最後看到的創意是獲得轉換的創意。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點按次數與曝光數 </p> </td> 
   <td> <p>如果歸因同時發生，在決定歸因時，點按優先於曝光。 例如，在顯示多個創意的頁面上，被點按的創意會獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料時近 </p> </td> 
   <td> <p>系統一律會根據前一天的可用資料計算報表。 </p> </td> 
  </tr> 
 </tbody> 
</table>
