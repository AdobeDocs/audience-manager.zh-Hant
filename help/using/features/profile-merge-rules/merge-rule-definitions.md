---
description: 合併規則選項可讓您控制Audience Manager用於細分的資料型別。 合併規則可包含由設定檔連結裝置圖表和/或與Audience Manager整合的其他協力廠商裝置圖表提供者對應的裝置設定檔。 您最多可以建立4個設定檔合併規則。
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 定義的設定檔合併規則選項
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# 已定義[!UICONTROL Profile Merge Rules]選項 {#profile-merge-rule-options-defined}

[!UICONTROL profile merge rule]選項可讓您控制[!DNL Audience Manager]用於細分的資料型別。 [!UICONTROL profile merge rule]可以包含由[!UICONTROL Profile Link]裝置圖表和/或與[!DNL Audience Manager]整合的其他協力廠商裝置圖表提供者對應的裝置設定檔。 您最多可以建立4個[!UICONTROL Profile Merge Rules]。 第四個[!UICONTROL Profile Merge Rule]僅供購買[!UICONTROL People-Based Destinations]附加元件的客戶使用。

您透過在[!UICONTROL Profile Merge Rule Setup]中選取下述選項來建置[!UICONTROL Profile Merge Rule]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule]選項總覽 {#overview}

[!UICONTROL Profile Merge Rules]允許許多規則組合，每個都適合特定使用案例。 請參閱下表以瞭解何時使用每個規則組合的詳細資訊。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 評估型別 | [!UICONTROL Audience Lab]支援 | 使用個案 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [裝置鎖定目標](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | 所有客戶 | 即時和批次 | 無 | [展開裝置鎖定目標](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客戶 | 僅限即時 | 無 | [共用裝置鎖定目標](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [線上/離線鎖定目標](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客戶 | 即時和批次 | 是 | [跨裝置目標定位](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | 所有客戶 | 即時和批次 | 無 | [進階跨裝置目標定位](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不適用 | 專屬於[以人物為基礎的目的地](../destinations/people-based-destinations-overview.md)客戶 | 僅限批次 | 無 | [以人物為基礎的目的地目標定位](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment]評估 {#segment-evaluation}

根據您的[!UICONTROL Profile Merge Rules]設定，[!DNL Audience Manager]可以即時、批次或兩者同時執行[!UICONTROL segment]評估。

* 即時[!UICONTROL segment]評估需要[!DNL DCS]才能看到訪客即時存取您的數位內容，以符合[!UICONTROL segment]的資格。
* 已針對先前符合資格的[!UICONTROL traits]執行批次[!UICONTROL segment]評估。
* 同時支援即時和批次[!UICONTROL segment]評估的[!UICONTROL Profile Merge Rules]將即時訪客活動與先前限定的[!UICONTROL traits]結合在一起。

## [!UICONTROL Profile Merge Rules]報告延遲 {#reporting-latency}

即時[!UICONTROL segment]評估會立即反映在[!UICONTROL Profile Merge Rules]報表中。

批次[!UICONTROL segment]評估最多可能需要24小時的時間，才能反映在[設定檔合併規則報表](profile-link-metrics.md)中。

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options]可讓您選取已驗證和未驗證的使用者，並將其跨裝置設定檔用於分段。 這些選項可協助您識別並觸及共用裝置上的特定使用者。 如需匿名與已驗證使用者的詳細資訊，請參閱Audience Manager[&#128279;](../../reference/visitor-authentication-states.md)中的訪客驗證狀態。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">沒有跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不要使用從已驗證的使用者收集的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">個目前驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>在訪客已登入您的網站時，讀取及寫入資料至已驗證的設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">上次驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>從上次登入裝置之使用者的已驗證設定檔讀取資料。 </p> <p>選取後，如果使用者為匿名，<span class="keyword">Audience Manager</span>將不會將新特徵資料寫入已驗證的設定檔。 驗證後，新特徵資料會寫入使用者的已驗證設定檔中。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">所有跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴Audience Manager從所有跨裝置設定檔讀取資料，無論驗證狀態為何。 此選項僅適用於已購買People-Based Destinations附加元件的Audience Manager客戶。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]列出您的[!UICONTROL cross-device data sources]。 這些選項會使用您建立[!UICONTROL cross-device] [!UICONTROL data source]時提供的名稱(請參閱[建立跨裝置資料Source](merge-rules-start.md#create-data-source))。 您最多可以選取3個[!UICONTROL cross-device data sources]以用於每個設定檔規則。 當您選擇&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;時，[!UICONTROL Authenticated Profile Options]可供使用。

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options]可讓您選取[!UICONTROL Profile Merge Rule]所使用的&#x200B;*`device profile`*&#x200B;型別。 裝置設定檔是從匿名瀏覽活動所收集的[!UICONTROL traits]所建置。 [!UICONTROL profile merge rule]至少包含[!UICONTROL authenticated option]和[!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">沒有裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不要使用匿名設定檔中包含的特徵進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用匿名裝置設定檔進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">設定檔連結裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>從目前裝置和最多100個使用者已驗證的其他裝置讀取設定檔。 此裝置圖表是以<span class="keyword">Audience Manager</span>中您自己的第一方資料建置。 如果您的數位財產具有高度驗證等級，非常適合使用此功能。 <span class="wintitle">設定檔連結</span>裝置圖表已即時更新。 當您選取<b><span class="uicontrol">目前驗證的設定檔</span></b>或<b><span class="uicontrol">上次驗證的設定檔</span></b>時，此選項可供使用。 使用此選項時，您只能選擇單一已驗證的設定檔(<span class="keyword">個Audience Manager</span>會自動將其他設定檔變灰)。 另請參閱<a href="profile-link-use-case.md">個人資料連結裝置圖表使用案例</a>。 </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>協力廠商裝置圖表選項</b> （個人和家庭） </p> </td>
   <td colname="col2"> <p>這些選項可讓您根據協力廠商提供的裝置圖表技術建立合併規則。 協力廠商裝置圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 機率和/或確定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭的資料。 </li> 
     </ul> </p> <p>若要使用這些選項，您必須是已與<span class="keyword">Audience Manager</span>整合之裝置圖表提供的客戶。 請聯絡您的客戶經理，以取得詳細資訊或開始使用。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

根據在[!DNL Audience Manager]外部定義的合併規則，從其他[!DNL Experience Cloud]解決方案自動建立的對象區段會使用[!UICONTROL External Merge Policy]標示為。 例如，請參閱[Audience Manager與Adobe Experience Platform之間的受眾共用](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)
