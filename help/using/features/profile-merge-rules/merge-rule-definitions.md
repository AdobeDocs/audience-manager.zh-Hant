---
description: 合併規則選項允許您控制用於分割的資料Audience Manager的類型。 合併規則可以包括由配置式連結設備圖形、Adobe Experience Cloud設備合作和/或與Audience Manager整合的其他第三方設備圖形提供器映射的設備配置式。 最多可建立4個配置檔案合併規則。
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph, the Adobe Experience Cloud Device Co-op, and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 定義的設定檔合併規則選項
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 5%

---

# [!UICONTROL Profile Merge Rules] 定義的選項 {#profile-merge-rule-options-defined}

的 [!UICONTROL profile merge rule] 選項，您可以控制資料類型 [!DNL Audience Manager] 用於分段。 A [!UICONTROL profile merge rule] 可以包括由映射的設備配置檔案 [!UICONTROL Profile Link] 設備圖， [!UICONTROL Adobe Experience Cloud Device Co-op]和/或其他與之整合的第三方設備圖形提供器 [!DNL Audience Manager]。 最多可建立4個 [!UICONTROL Profile Merge Rules]。 第四 [!UICONTROL Profile Merge Rule] 僅供購買了 [!UICONTROL People-Based Destinations] 附件。

您構建 [!UICONTROL Profile Merge Rule] 通過從下面所述選項中進行選擇，在 [!UICONTROL Profile Merge Rule Setup]。

![配置檔案合併規則設定](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 選項概述 {#overview}

[!UICONTROL Profile Merge Rules] 允許多個規則組合，每個組合都針對特定的使用情形。 有關何時使用每個規則組合的詳細資訊，請參閱下表。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 評估類型 | [!UICONTROL Audience Lab] 支援 | 使用個案 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批處理 | 是 | [設備目標](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] 包括 [!UICONTROL Co-op Device Graph]) | 所有客戶 | 即時和批處理 | 無 | [擴展設備目標](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客戶 | 僅即時 | 無 | [共用設備目標](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批處理 | 是 | [聯機/離線目標](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客戶 | 即時和批處理 | 是 | [跨設備目標](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] 包括 [!UICONTROL Co-op Device Graph]) | 所有客戶 | 即時和批處理 | 無 | [高級跨設備目標](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不適用 | 獨佔 [基於人的目的地](../destinations/people-based-destinations-overview.md) 客戶 | 僅批 | 無 | [針對基於人的目標](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 評估 {#segment-evaluation}

取決於您 [!UICONTROL Profile Merge Rules] 配置， [!DNL Audience Manager] 可以執行 [!UICONTROL segment] 即時評估、批處理評估或兩者。

* 即時 [!UICONTROL segment] 評估需要 [!DNL DCS] 讓訪問者即時訪問您的數字屬性，以符合 [!UICONTROL segment]。
* 批 [!UICONTROL segment] 根據先前的合格評估執行評估 [!UICONTROL traits]。
* [!UICONTROL Profile Merge Rules] 支援即時和批處理 [!UICONTROL segment] 評估將即時訪問者活動與先前合格的活動結合起來 [!UICONTROL traits]。

## [!UICONTROL Profile Merge Rules] 報告延遲 {#reporting-latency}

即時 [!UICONTROL segment] 評估反映於 [!UICONTROL Profile Merge Rules] 報告。

批 [!UICONTROL segment] 評估可能需要24小時才能反映 [配置檔案合併規則報表](profile-link-metrics.md)。

## [!UICONTROL Cross-Device Options] {#auth-options}

的 [!UICONTROL Cross-Device Options] 允許您選擇經過驗證和未經驗證的用戶，並利用其跨設備配置檔案進行分段。 這些選項可幫助您識別和聯繫共用設備上的特定用戶。 有關匿名用戶和已驗證用戶的詳細資訊，請參見 [訪問者身份驗證狀態在Audience Manager](../../reference/visitor-authentication-states.md)。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨設備選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無跨設備配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 不使用從經過身份驗證的用戶收集的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 當前已驗證的配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 如果訪問者已登錄到您的站點，則將資料讀取並寫入經過驗證的配置檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次驗證的配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 從上次登錄到設備的用戶的經過驗證的配置檔案中讀取資料。 </p> <p>選中後， <span class="keyword"> Audience Manager</span> 如果用戶是匿名的，則不會將新特性資料寫入經過身份驗證的配置檔案。 在驗證時，新特性資料被寫入用戶的已驗證配置檔案。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨設備配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>指示Audience Manager從所有跨設備配置檔案中讀取資料，而不考慮身份驗證狀態。 此選項僅適用於已購買「基於人員的目標」附加項的Audience Manager客戶。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

的 [!UICONTROL Cross-Device Profile Options] 列出 [!UICONTROL cross-device data sources]。 這些選項使用建立 [!UICONTROL cross-device] [!UICONTROL data source] （請參見） [建立跨設備資料源](merge-rules-start.md#create-data-source))。 最多可選擇3個 [!UICONTROL cross-device data sources] 與每個配置檔案規則一起使用。 的 [!UICONTROL Authenticated Profile Options] 當您選擇時可用 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]**。

## [!UICONTROL Device Options] {#device-options}

的 [!UICONTROL Device Options] 允許您選擇 *`device profile`* 由 [!UICONTROL Profile Merge Rule]。 設備配置檔案由 [!UICONTROL traits] 從匿名瀏覽活動中收集。 至少， [!UICONTROL profile merge rule] 包括 [!UICONTROL authenticated option] 和 [!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設備選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無設備配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 不要使用匿名配置檔案中包含的特徵進行分割。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 設備配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 使用匿名設備配置檔案進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 配置檔案連結設備圖</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 從當前設備和用戶已通過身份驗證的多達100個其他設備中讀取配置檔案。 此設備圖是基於您自己的第一方資料 <span class="keyword"> Audience Manager</span>。 它非常適合於那些通過其數字屬性進行高級別身份驗證的客戶。 的 <span class="wintitle"> 配置檔案連結</span> 設備圖形被即時更新。 當您選擇 <b><span class="uicontrol"> 當前已驗證的配置檔案</span></b> 或 <b><span class="uicontrol"> 上次驗證的配置檔案</span></b>。 使用此選項時，只能選擇一個經過身份驗證的配置檔案(<span class="keyword"> Audience Manager</span> 自動將其他的灰燼)。 另請參見 <a href="profile-link-use-case.md"> 配置檔案連結設備圖形使用案例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 合作設備圖</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> 從當前設備和多達100個其他設備中讀取配置式，使用由 <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud設備合作</a>。 </p> <p><span class="keyword"> Device Co-op</span> 是數位合作社，參與客戶在此分享裝置連結資訊。的 <span class="keyword"> 設備合作</span> 在 <span class="term"> 設備圖</span>。 設備圖形將設備連接在一起，形成設備群集。 這些連結是從 <a href="https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/links.html" format="https" scope="external"> 概率和確定性資料</a>。 群集表示由未知人使用的一組設備。 <span class="keyword">Device Co-op</span> 會在其成員間分享這些叢集，如此有助於它們為其客戶提供珍貴而一致的跨裝置體驗。 </p> <p> 有關 <span class="wintitle"> 設備合作</span>，請參閱： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/home.html" format="https" scope="external"> 設備合作概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/requirements.html" format="https" scope="external"> 成員資格需求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 設備圖形：內部流程和輸出</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方設備圖形選項</b> （人家） </p> </td>
   <td colname="col2"> <p>這些選項使您能夠基於第三方供應商提供的設備圖形技術構建合併規則。 第三方設備圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和/或確定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭級資料。 </li> 
     </ul> </p> <p>要使用這些選項，您必須是設備圖表的客戶，該圖表提供了已與 <span class="keyword"> Audience Manager</span>。 請聯繫您的客戶經理以瞭解更多資訊或開始。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

自動從其他 [!DNL Experience Cloud] 解決方案，基於在 [!DNL Audience Manager]，標籤為使用 [!UICONTROL External Merge Policy]。 例如，請參見 [Audience Manager與Adobe Experience Platform的受眾共用](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [配置檔案合併規則常見問題](../../faq/faq-profile-merge.md)

