---
description: Audience Optimization報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。
seo-description: Audience Optimization報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。
seo-title: 跨通道轉換
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: 受眾最佳化報表
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 5%

---

# 跨通道轉換{#cross-channel-conversion}

Audience Optimization報表中的「跨管道轉換」選項可讓您將離線轉換數歸因為已提供的線上曝光數或點按次數。

[!UICONTROL Cross Channel Conversion]報表會結合來自[!DNL Google Campaign Manager]平台的結果與[!DNL Audience Manager]轉換特徵。 這可讓您將離線轉換連結至線上曝光次數或點按次數。

您可以對[區段效能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)和[最佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)報表使用[!UICONTROL Cross Channel Conversion]。

若要檢視[!UICONTROL Cross Channel Conversion]報表，請在&#x200B;**[!UICONTROL Platform]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL AAM + Ad Server Name]**&#x200B;項目。

下表列出了設定[!UICONTROL Cross Channel Conversion]時的重要考量：

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
   <td colname="col1"> <p>必須至少將一個轉換特徵指派給資料源，<span class="wintitle">跨通道轉換</span>報表才能運行。 如需特徵的詳細資訊，請參閱<a href="../../../features/traits/create-onboarded-rule-based-traits.md">特徵的基本資訊</a> 。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>歸因視窗 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google Campaign Manager</span></b> 歸因視窗為14天，這表示只會考慮過去兩週所展現的轉換特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>使用者在轉換前最後看到的創意內容，即為獲得轉換的創意。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點按次數與曝光次數 </p> </td> 
   <td> <p>決定歸因時，點按優先於曝光次數（若是同時發生）。 例如，在顯示多個創作的頁面上，被點按的創作會獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料時近 </p> </td> 
   <td> <p>報表一律會針對前一天的可用資料進行計算。 </p> </td> 
  </tr> 
 </tbody> 
</table>
