---
description: 特徵資格或特徵實現在Audience manager中會根據特徵類型有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
keywords: 特徵限定；特徵實現；獨特特徵實現； UTR；特徵總量； TTP
seo-description: 特徵資格或特徵實現在Audience manager中會根據特徵類型有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。
seo-title: 特徵資格參考
solution: Audience Manager
title: 特徵資格參考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 特徵資格參考 {#trait-qualification-reference}

特徵資格或特徵實現在Audience manager中會根據特徵類型有不同的處理方式。 請參閱下表以取得特徵資格的詳細資訊。

## 依特徵類型區分特徵限定 {#trait-type}

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
   <td colname="col2"> <p>特徵資格會即時發生，因為使用者在瀏覽器中符合特徵資格。 在您在UI中建立特徵後大約4小時，您的使用者就 <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> 會開始符合規則</a> 。 </p> <p>規則型特徵可讓您使用時近 <a href="../../features/segments/recency-and-frequency.md"> 和頻率控制項</a> ，來設定廣告頻率上限和其他使用案例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已登錄特徵 </p> </td> 
   <td colname="col2"> <p>特徵限定會在處理傳入檔案後發生，例如傳入檔案會匯入 <a href="../../faq/faq-inbound-data-ingestion.md"> Audience Manager</a> ，也就是特徵限定發生時。 </p> <p> 對於已登入的特徵，使用者設定檔的資格上限為1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演算法特徵 </p> </td> 
   <td colname="col2"> <p>對於演算法特徵，使用者設定檔的最大資格數為1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料夾特徵 </p> </td> 
   <td colname="col2"> <p>資料夾特徵會匯總其所含特徵的特徵資格。 </p> <p>閱讀資 <a href="../../features/traits/about-folder-traits.md"> 料夾特徵：關於</a> ，以取得詳細資訊。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>作用中受眾特徵與資料來源同步特徵 </p> </td> 
   <td colname="col2"> <p>「活 <span class="wintitle"> 動中的觀眾</span> 」特徵包含Audience manager帳戶中管理的所有 <span class="wintitle"> 裝置</span> 。 </p> <p><span class="wintitle"> 「資料來源同步特徵</span> 」會追蹤與資料來源關聯的所有使用者。 </p> <p>閱讀更多有關「 <a href="../../features/traits/client-activity-synced-audience-traits.md"> 作用中受眾特徵」和「資料來源同步特徵」的資訊</a>。 </p> </td>
  </tr>
 </tbody>
</table>

## 獨特性實現與特性總量 {#unique-trait-realizations}

![](assets/utr-ttp1.png)

計 **[!UICONTROL Unique Trait Realizations]** 算在不同時間範圍內將特徵新增至其描述檔的訪客數。

代 **[!UICONTROL Total Trait Population]** 表訪客在其描述檔中具有此特徵的訪客數。

用這種方式來考慮數字。 在上述影像中，從「特 [徵詳細資料](../../features/traits/trait-details-page.md) 」檢視中，181代表昨天瀏覽您屬性的作用中裝置數。 1,595 [!UICONTROL Total Trait Population] 表示目前符合此特徵資格的使用者數量。 此 [!UICONTROL Total Trait Population] 圖旨在顯示可用於分段／定位的使用者總數。 通常，使用者會在120天內保留某個特徵的一部分。

因為我們運行兩個不同的計算工作來計算這兩個人口族群， [!UICONTROL Total Trait Population] 因此總是落後 [!UICONTROL Unique Trait Realizations] 24小時。 在上圖中，2月11日的 [!UICONTROL Unique Trait Realizations] 175 [!UICONTROL Total Trait Population] 和6。 175個描述檔會在下 [!UICONTROL Total Trait Population] 一天新增至。

為了進一步推動重點，如果您目前體驗到10,000名訪客的尖峰，他們會出現在明天的 [!UICONTROL Unique Trait Realizations]，但只會在24小時後出現在 [!UICONTROL Total Trait Population]。

## 特徵資格限制 {#trait-qualification-limit}

我們會針對每個使用者描述檔強制實施150,000個特徵資格限制，不論是已驗證的描述檔( [DPUUID](../../reference/ids-in-aam.md))或裝置ID( [UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對於特定例項是唯一的， [!DNL Audience Manager]但UUID會在平台間共 [!DNL Audience Manager] 用。 因 [!UICONTROL UUID]此，我們在儲存特徵資格時，實行公平政策。 演算法可確保每個例項 [!UICONTROL UUID] 都能有相同的描述檔份額 [!DNL Audience Manager]。
