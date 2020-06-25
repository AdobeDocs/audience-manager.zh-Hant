---
description: 「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。
seo-description: 「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。
seo-title: 跨通道轉換
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 4%

---


# 跨通道轉換{#cross-channel-conversion}

「對象最佳化」報表中的「跨通道轉換」選項可讓您將離線轉換歸因於提供的線上印象或點按。

報 [!UICONTROL Cross Channel Conversion] 表會結合來自(DCM)平台 [!DNL DoubleClick Campaign Manager] 的結果與轉換 [!DNL Audience Manager] 特性。 這可讓您將離線轉換連結至線上印象或點按。

您可使用「區 [!UICONTROL Cross Channel Conversion] 段效 [能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 」和「最 [佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 」報表。

若要檢視 [!UICONTROL Cross Channel Conversion] 報表，請選取下 **[!UICONTROL AAM+DCM]** 拉式清單 **[!UICONTROL Platform]** 中的項目。

下表列出了設定時的重要注意事項 [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>至少必須將一個轉換特徵指派給資料來源，才能執行「跨通 <span class="wintitle"> 道轉換</span> 」報表。 如需 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 特徵的詳細資訊</a> ，請參閱特徵的基本資訊。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>歸因視窗 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+DCM歸因視窗為</span></b> 14天，這表示僅會考慮過去兩週所呈現的轉換特性。 </p> </td> 
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
