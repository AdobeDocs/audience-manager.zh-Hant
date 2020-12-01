---
description: 「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。
seo-description: 「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。
seo-title: 跨通道轉換
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---


# 跨通道轉換{#cross-channel-conversion}

「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。

[!UICONTROL Cross Channel Conversion]報表結合來自[!DNL Google Campaign Manager]平台的結果與[!DNL Audience Manager]轉換特性。 這可讓您將離線轉換連結至線上印象或點按。

您可以對[區段效能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)和[最佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)報表使用[!UICONTROL Cross Channel Conversion]。

若要檢視[!UICONTROL Cross Channel Conversion]報表，請在&#x200B;**[!UICONTROL Platform]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL AAM + Ad Server Name]**&#x200B;項目。

下表列出了在設定[!UICONTROL Cross Channel Conversion]時的重要注意事項：

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 考量事項 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>轉換特徵的最小數目 </p> </td> 
   <td colname="col1"> <p>至少必須將一個轉換特徵指派給資料來源，<span class="wintitle">跨通道轉換</span>報表才能執行。 如需特徵的詳細資訊，請參閱<a href="../../../features/traits/create-onboarded-rule-based-traits.md">特徵的基本資訊</a>。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>歸因視窗 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google Campaign </span></b> Manager歸因視窗為14天，這表示僅會考慮過去兩週所呈現的轉換特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>使用者在轉換前所見的創意素材是授與轉換的。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點按次數與印象 </p> </td> 
   <td> <p>在決定歸因時，點按優先於曝光（如果是同時發生）。 例如，在顯示多個創作元素的頁面上，點按的創作元素會獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料時近 </p> </td> 
   <td> <p>報表一律會針對前一天的可用資料進行計算。 </p> </td> 
  </tr> 
 </tbody> 
</table>
