---
description: 透過描述檔合併規則，您可以控制用於劃分的資料集，並可跨多種裝置精確定位人員。
seo-description: 透過描述檔合併規則，您可以控制用於劃分的資料集，並可跨多種裝置精確定位人員。
seo-title: 描述檔合併規則概觀
solution: Audience Manager
title: 描述檔合併規則概觀
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# 描述檔合併規則概觀 {#profile-merge-rules-overview}

您 [!UICONTROL Profile Merge Rules] 可以控制用於細分的資料集，並可以跨多種裝置精確定位人員。

## 使用匿名和已驗證的設定檔來收集和定位資料 {#data-collection-targeting}

通常，受眾細分和定位依賴於從裝置上所有使用者收集到的資料。 基於裝置層級資料的資料收集和定位有一些缺點。 例如，您無法區分共用裝置的多個使用者，或是跨多個裝置精確定位使用者。 以裝置為中心的資料收集已不足以用於數位行銷宣傳或跨裝置定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 從根本上改變 [!DNL Audience Manager] 了收集資料和群體使用者以進行定位的方式。 它可讓您使用2種不同的描述檔類型、裝置描述檔和已驗證的描述檔。

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
   <td colname="col2"> <p>裝置描述檔會系結至指定裝置的ID，例如Cookie ID或行動裝置ID。 其功能包括: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">當使用者未經驗證時，可實現以規則為基礎的特性。 </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">系結至裝置ID（例如以Cookie為基礎的第三方資料）的已登入特徵。 </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 已驗證的設定檔 </td> 
   <td colname="col2"> <p>已驗證的描述檔會系結至某人登入您的網站時傳入的使用者ID。 其功能包括 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">當使用者經過驗證時，會跨裝置收集到以規則為基礎的特徵。 </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">連結至相同使用者ID的離線檔案中已登入特徵。 </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

這些不同的描述檔可控制您用於區段的資料。 例如，透過驗證的設定檔，您可以根據來自單一人員多個裝置的資料，建立精確的區段。 這表示您可以跨多種裝置為客戶提供一致的品牌體驗。 此外，跨裝置驗證可 [!DNL Audience Manager] 讓使用者對應其線上活動所使用的不同平台。 這叫做 [!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 優勢 {#advantages}

您 [!UICONTROL Profile Merge Rules] 可以：

* 根據已驗證的個人檔案、匿名個人檔案或兩者的組合來定位使用者。
* 跨裝置鎖定特定客戶。
* 根據確定性資料建立裝置圖表。
* 根據不同的描述檔，微調區段中的資料。
* 進一步瞭解您的受眾。

## 入門 {#getting-started}

如需詳細資訊，請參 [閱下列章節](../../faq/faq-profile-merge.md) 和常見問答 [!UICONTROL Profile Merge Rules]集。

* [描述檔合併規則快速入門](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [描述檔合併規則控制面板](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [定義的配置檔案合併規則選項](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [描述檔合併規則的一般使用案例](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [描述檔連結裝置圖表使用案例](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [外接式裝置圖表使用案例](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [描述檔合併規則的報表量度](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [描述檔合併規則與裝置取消區段程式](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [即時跨裝置隱藏功能](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [配置式合併規則與設備圖形的重要注意事項](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
