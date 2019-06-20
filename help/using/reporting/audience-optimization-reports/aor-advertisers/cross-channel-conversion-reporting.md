---
description: 「對象最佳化」報表中的「跨頻道轉換」選項可讓您屬性離線轉換，以提供線上印象或點按。
seo-description: 「對象最佳化」報表中的「跨頻道轉換」選項可讓您屬性離線轉換，以提供線上印象或點按。
seo-title: 跨通道轉換
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7 dd-47a3753 a3 f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 跨通道轉換{#cross-channel-conversion}

「對象最佳化」報表中的「跨頻道轉換」選項可讓您屬性離線轉換，以提供線上印象或點按。

[!UICONTROL Cross Channel Conversion] 報表結合了來自 [!DNL DoubleClick Campaign Manager] (DCM)平台與 [!DNL Audience Manager] 轉換特性的結果。這可讓您將離線轉換連結至線上印象或點按。

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 考量事項 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>最低轉換特徵數 </p> </td> 
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>轉換特徵數目上限 </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. 若您達到最大值，報表會以遞增順序使用前50個基於特徵ID的轉換特性。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>歸因視窗 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+ DCM</span></b> 歸因視窗為14天，表示只會考慮最近兩周顯示的轉換特性。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>使用者在轉換之前看過的創意素材就是轉換完成的最後一個。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點按次數與印象次數 </p> </td> 
   <td> <p>在決定屬性時，點按優先於印象。例如，在顯示多個創意素材的頁面上，被點按的一個人獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料最近時 </p> </td> 
   <td> <p>報表一律會計算前一天可用的資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>
