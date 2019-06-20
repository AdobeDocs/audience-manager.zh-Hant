---
description: 透過設定檔合併規則，您可以控制用於劃分的資料集，並可在多個裝置上準確定位人員。
seo-description: 透過設定檔合併規則，您可以控制用於劃分的資料集，並可在多個裝置上準確定位人員。
seo-title: 描述檔合併規則概述
solution: Audience Manager
title: 描述檔合併規則概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules] 您可以控制用於劃分的資料集，並可在多個裝置上準確定位個人。

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

通常，觀眾分段和定位需仰賴裝置上所有使用者收集到的資料。根據裝置層級資料收集和定位資料有一些缺點。例如，您無法區分多個使用者共用裝置，或精確定位跨多個裝置的使用者。以裝置為中心的資料收集不再足夠用於數位行銷宣傳或跨裝置目標鎖定。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 從根本上改變 [!DNL Audience Manager] 了收集資料和區段使用者的方式。它可讓您使用個不同類型的描述檔、裝置描述檔和已驗證的描述檔。

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 描述檔類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 裝置 描述檔 </td> 
   <td colname="col2"> <p>裝置描述檔會系結至特定裝置的ID，例如Cookie ID或行動裝置ID。其功能包括: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">規則型特徵會在使用者未驗證時實現。 </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">系結至裝置ID的已登錄特徵，例如以Cookie為基礎的第三方資料。 </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 驗證的個人檔案 </td> 
   <td colname="col2"> <p>驗證的描述檔會系結至使用者登入您網站時傳入的使用者ID。其功能包括 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">當使用者驗證時，跨裝置收集的規則特徵。 </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">離線檔案中連結到相同使用者ID的已登錄特性。 </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

這些不同的設定檔可控制您可用於劃分的資料。例如，透過已驗證的個人檔案，您可以根據單一人員來自多種裝置的資料建立精確區段。這表示您可以跨多種裝置向客戶提供一致的品牌體驗。Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. [!UICONTROL Profile Link Device Graph]這稱為。

![](assets/authenticated2.png)

## 優勢 {#advantages}

[!UICONTROL Profile Merge Rules] 您可以使用：

* 根據已驗證的個人檔案、匿名個人檔案或兩者組合來定位使用者。
* 跨裝置鎖定特定客戶。
* 根據決定性資料建立裝置圖表。
* 根據不同的描述檔微調區段中的資料。
* 深入瞭解受眾。

## 入門 {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [設定檔合併規則快速入門](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [描述檔合併規則控制面板](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [定義的設定檔合併規則選項](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [描述檔合併規則的一般使用案例](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [描述檔連結裝置圖表使用案例](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [外接式裝置圖表使用案例](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [設定檔合併規則的報表量度](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [描述檔合併規則與裝置取消分段程序](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [即時跨裝置隱藏功能](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [設定檔合併規則與裝置圖表的重要考量](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
