---
description: 根據特徵類型，Audience Manager中的特徵符合或特徵實現方式不同。請參閱下表以取得特徵資格的詳細資訊。
keywords: 特徵資格；特徵實現；獨特特徵實作；UTR；特徵總人口數；TTP
seo-description: 根據特徵類型，Audience Manager中的特徵符合或特徵實現方式不同。請參閱下表以取得特徵資格的詳細資訊。
seo-title: 特徵資格參考
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d-壞7-10fb46 b08 ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 特徵資格參考 {#trait-qualification-reference}

根據特徵類型，Audience Manager中的特徵符合或特徵實現方式不同。請參閱下表以取得特徵資格的詳細資訊。

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特徵類型 </th> 
   <th colname="col2" class="entry"> 資格標準 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>規則型特徵 </p> </td> 
   <td colname="col2"> <p>當使用者在瀏覽器中符合特徵時，特徵資格就會即時生效。Your users will start qualifying for a rule-based trait approximately 4 hours after you <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> create the trait</a> in the UI. </p> <p>Rule-based traits allow you to use <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> controls for ad frequency capping and other use cases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已登錄的特性 </p> </td> 
   <td colname="col2"> <p>Trait qualification happens after an inbound file is processed, i.e. the inbound file is <a href="../../faq/faq-inbound-data-ingestion.md"> imported into Audience Manager</a> and that is when the trait qualification happens. </p> <p> 對於已登錄的特性，使用者個人檔案的資格上限為1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法特性 </p> </td> 
   <td colname="col2"> <p>對於演算法特徵，使用者個人資料的資格上限為1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料夾特性 </p> </td> 
   <td colname="col2"> <p>資料夾特徵會總結其特徵特徵的特徵資格。 </p> <p>Read <a href="../../features/traits/about-folder-traits.md"> Folder Traits: About</a> for more information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>作用中對象特徵和資料來源同步特徵 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 「活動中對象</span> 」特徵包含 <span class="wintitle"> Audience Manager</span> 帳戶中管理的所有裝置。 </p> <p><span class="wintitle"> 「資料來源同步特性</span> 」會追蹤所有與資料來源關聯的使用者。 </p> <p>Read more about <a href="../../features/traits/client-activity-synced-audience-traits.md"> Active Audience Traits and Data Source Synced Traits</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unique Trait Realizations and Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

**[!UICONTROL Unique Trait Realizations]** 計算訪客在不同時間範圍內將特徵新增至其描述檔的數目。

The **[!UICONTROL Total Trait Population]** represents the number of your visitors that have this trait on their profile.

以這種方式思考數字。In the image above, from the [Trait Details](../../features/traits/trait-details-page.md) view, 181 represents the number of active devices, that visited your properties yesterday. The [!UICONTROL Total Trait Population] of 1,595 represents the amount of users currently qualified for this trait. [!UICONTROL Total Trait Population] 此數字旨在顯示可用於劃分/定位的使用者總數。通常使用者會繼續屬於特徵的一部分120天。

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

To further drive the point home, if you experienced a spike of 10,000 visitors right now, they would show up in tomorrow's [!UICONTROL Unique Trait Realizations], but would only show up 24 hours later in the [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

We enforce a limit of 150,000 trait qualifications for each user profile, whether it is an authenticated profile ( [DPUUID](../../reference/ids-in-aam.md)) or a device ID ( [UUID](../../reference/ids-in-aam.md)). Note that while the DPUUIDs are unique to a specific instance of [!DNL Audience Manager], UUIDs are shared across the [!DNL Audience Manager] platform. For [!UICONTROL UUID]s, we impose a fairness policy when storing trait qualifications. An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
