---
description: 合併規則選項可讓您控制Audience Manager用於分段的資料類型。 合併規則可包含由已與Audience Manager整合之設定檔連結裝置圖表、Adobe Experience Cloud Device Co-op和/或其他協力廠商裝置圖表提供者所對應的裝置設定檔。 您最多可以建立4個設定檔合併規則。
seo-description: 合併規則選項可讓您控制Audience Manager用於分段的資料類型。 合併規則可包含由已與Audience Manager整合之設定檔連結裝置圖表、Adobe Experience Cloud Device Co-op和/或其他協力廠商裝置圖表提供者所對應的裝置設定檔。 您最多可以建立4個設定檔合併規則。
seo-title: 定義的設定檔合併規則選項
solution: Audience Manager
title: 定義的設定檔合併規則選項
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: 個人資料合併
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] 定義的選項  {#profile-merge-rule-options-defined}

[!UICONTROL profile merge rule]選項可讓您控制[!DNL Audience Manager]用於分段的資料類型。 [!UICONTROL profile merge rule]可以包括由與[!DNL Audience Manager]整合的[!UICONTROL Profile Link]裝置圖表、[!UICONTROL Adobe Experience Cloud Device Co-op]和/或其他第三方裝置圖表提供者映射的裝置設定檔。 您最多可以建立4 [!UICONTROL Profile Merge Rules]。 第四個[!UICONTROL Profile Merge Rule]僅供購買[!UICONTROL People-Based Destinations]附加元件的客戶使用。

從[!UICONTROL Profile Merge Rule Setup]中的下述選項中進行選取，即可建立[!UICONTROL Profile Merge Rule]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 選項概述 {#overview}

[!UICONTROL Profile Merge Rules] 允許許多規則組合，每個組合都針對特定使用案例。請參閱下表，以了解每個規則組合的使用時機。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 評估類型 | [!UICONTROL Audience Lab] 支援 | 使用個案 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [裝置鎖定](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客戶 | 即時和批次 | 無 | [擴展裝置鎖定目標](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客戶 | 僅即時 | 無 | [共用裝置鎖定](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [線上/離線定位](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客戶 | 即時和批次 | 是 | [跨裝置鎖定](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客戶 | 即時和批次 | 無 | [進階跨裝置鎖定目標](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不適用 | 專屬於[以人物為基礎的目的地](../destinations/people-based-destinations-overview.md)客戶 | 僅批 | 無 | [以人物為基礎的目的地鎖定目標](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 評估  {#segment-evaluation}

根據您的[!UICONTROL Profile Merge Rules]配置，[!DNL Audience Manager]可以即時、批次或同時執行[!UICONTROL segment]評估。

* 即時[!UICONTROL segment]評估需要[!DNL DCS]來即時查看訪客存取您的數位屬性，以符合[!UICONTROL segment]的資格。
* 對先前合格的[!UICONTROL traits]執行批次[!UICONTROL segment]評估。
* [!UICONTROL Profile Merge Rules] 可同時支援即時和批次 [!UICONTROL segment] 評估，結合即時訪客活動與先前的合格 [!UICONTROL traits]。

## [!UICONTROL Profile Merge Rules] 報表延遲  {#reporting-latency}

即時[!UICONTROL segment]評估會立即反映在[!UICONTROL Profile Merge Rules]報表中。

批次[!UICONTROL segment]評估最多需要24小時，才能反映在[設定檔合併規則報表](profile-link-metrics.md)中。

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options]可讓您選取已驗證和未驗證的使用者，並運用其跨裝置設定檔進行細分。 這些選項可協助您識別和觸及共用裝置上的特定使用者。 如需匿名和已驗證使用者的詳細資訊，請參閱Audience Manager](../../reference/visitor-authentication-states.md)中的[訪客驗證狀態。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴<span class="keyword">Audience Manager</span>不要使用從已驗證的使用者收集的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前已驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴<span class="keyword">Audience Manager</span>如果訪客已登入您的網站，請讀取資料並將資料寫入已驗證的訪客資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>從上次登入裝置之使用者的已驗證設定檔讀取資料。 </p> <p>選取時，如果使用者匿名，<span class="keyword">Audience Manager</span>將不會將新特徵資料寫入已驗證的設定檔。 驗證時，新特徵資料會寫入使用者已驗證的設定檔。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知Audience Manager從所有跨裝置設定檔讀取資料，而不論驗證狀態為何。 此選項僅適用於已購買People-Based Destinations附加元件的Audience Manager客戶。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]會列出您的[!UICONTROL cross-device data sources]。 這些選項使用建立[!UICONTROL cross-device] [!UICONTROL data source]時您提供的名稱（請參閱[建立跨裝置資料來源](merge-rules-start.md#create-data-source)）。 您可以選取最多3個[!UICONTROL cross-device data sources]以搭配每個設定檔規則使用。 選擇&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;時，[!UICONTROL Authenticated Profile Options]可用。

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options]可讓您選取[!UICONTROL Profile Merge Rule]所使用的&#x200B;*`device profile`*&#x200B;類型。 從從匿名瀏覽活動收集的[!UICONTROL traits]建立裝置設定檔。 [!UICONTROL profile merge rule]至少包括[!UICONTROL authenticated option]和[!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無設備配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>告訴<span class="keyword">Audience Manager</span>不要使用匿名設定檔中包含的特徵進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用匿名設備配置檔案進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 設定檔連結裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>從當前設備和最多100個用戶已通過身份驗證的其他設備讀取配置檔案。 此裝置圖表是以您在<span class="keyword">Audience Manager</span>中的第一方資料為基礎所建置。 對於在其數位屬性中具有高驗證級別的客戶，此功能非常理想。 即時更新<span class="wintitle">設定檔連結</span>裝置圖表。 當您選取「<b><span class="uicontrol">目前已驗證的設定檔</span></b>」或「<b><span class="uicontrol">最後已驗證的設定檔</span></b>」時，此選項可供使用。 使用此選項時，您只能選擇單一已驗證的設定檔(<span class="keyword">Audience Manager</span>會自動淘汰其他設定檔)。 另請參閱<a href="profile-link-use-case.md">設定檔連結裝置圖表使用案例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用<a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external">Experience CloudDevice Co-op</a>提供的連結從當前設備和多達100個其他設備讀取配置檔案。 </p> <p><span class="keyword"> Device Co-op</span> 是數位合作社，參與客戶在此分享裝置連結資訊。<span class="keyword"> Device Co-op</span>會在<span class="term">裝置圖表</span>中處理此資料。 裝置圖表會將裝置連結在一起，形成裝置叢集。 這些連結是從<a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external">可能性和確定性資料</a>建立。 叢集代表未知人員使用的一組裝置。 <span class="keyword">Device Co-op</span> 會在其成員間分享這些叢集，如此有助於它們為其客戶提供珍貴而一致的跨裝置體驗。 </p> <p> 如需<span class="wintitle"> Device Co-op</span>的詳細資訊，請參閱： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Device Co-op概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> 成員資格需求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 裝置圖表：內部流程和輸出</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>協力廠商裝置圖表選項</b> （個人和家庭） </p> </td>
   <td colname="col2"> <p>這些選項可讓您根據協力廠商提供的裝置圖表技術來建立合併規則。 協力廠商裝置圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 可能性和/或確定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭層級的資料。 </li> 
     </ul> </p> <p>若要使用這些選項，您必須是已與<span class="keyword">Audience Manager</span>整合的裝置圖表的客戶。 如需詳細資訊或快速入門，請連絡您的客戶經理。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

根據在[!DNL Audience Manager]以外定義的合併規則，從其他[!DNL Experience Cloud]解決方案自動建立的對象區段，會使用[!UICONTROL External Merge Policy]標示為。 例如，請參閱[Audience Manager與Adobe Experience Platform之間的受眾共用](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

