---
description: Audience Optimization報表中的「跨通道轉換」選項允許您將離線轉換屬性為提供的線上印象或按一下。
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: 跨通道轉換
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# 跨通道轉換{#cross-channel-conversion}

Audience Optimization報表中的「跨通道轉換」選項允許您將離線轉換屬性為提供的線上印象或按一下。

的 [!UICONTROL Cross Channel Conversion] 報告合併來自 [!DNL Google Campaign Manager] 平台 [!DNL Audience Manager] 轉換特性。 這允許您將離線轉換連結到聯機印象或按一下。

您可以使用 [!UICONTROL Cross Channel Conversion] 為 [段效能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 和 [最佳頻率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 報告。

查看 [!UICONTROL Cross Channel Conversion] 報告，選擇 **[!UICONTROL AAM + Ad Server Name]** 項 **[!UICONTROL Platform]** 的子菜單。

下表列出了在設定 [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>必須至少將一個轉換特性分配給資料源，以便 <span class="wintitle"> 跨通道轉換</span> 要運行的報告。 請參閱 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 特徵的基本資訊</a> 更多關於性狀的資訊。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>屬性窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> +AAMGoogle營銷經理</span></b> 歸因窗口為14天，即僅考慮過過去兩週所表現的轉化性狀。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上次接觸方法 </p> </td> 
   <td> <p>用戶在轉換前看到的創意是獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>點擊與印象 </p> </td> 
   <td> <p>在決定是否同時進行歸屬時，按一下優先於印象。 例如，在顯示多個創意的頁面上，將所按一下的一個獲得轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>資料頻率 </p> </td> 
   <td> <p>始終為前一天可用的資料計算報表。 </p> </td> 
  </tr> 
 </tbody> 
</table>
