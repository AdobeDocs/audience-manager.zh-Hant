---
description: 合併規則選項可讓您控制Audience Manager用於分段的資料類型。合併規則可以包含由描述檔連結裝置圖表、Adobe Experience Cloud Device Co-op及/或其他與Audience Manager整合的第三方裝置圖形提供者所對應的裝置設定檔。您最多可以建立個描述檔合併規則。
seo-description: 合併規則選項可讓您控制Audience Manager用於分段的資料類型。合併規則可以包含由描述檔連結裝置圖表、Adobe Experience Cloud Device Co-op及/或其他與Audience Manager整合的第三方裝置圖形提供者所對應的裝置設定檔。您最多可以建立個描述檔合併規則。
seo-title: 定義的設定檔合併規則選項
solution: Audience Manager
title: 定義的設定檔合併規則選項
uuid: 225eef7-45e9-4f21-9360-d80 a9 f90520 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

合併規則選項可讓您控制Audience Manager用於分段的資料類型。A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> 已驗證的選項</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> 驗證的描述檔選項</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 裝置選項</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. 這些選項可協助您識別和觸及共用裝置上的特定使用者。For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 已驗證選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. 在驗證時，新特徵資料會寫入使用者已驗證的個人檔案。 </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

The [!UICONTROL Authenticated Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). 您最多可以選取個跨裝置資料來源，用於每個描述檔規則。[!UICONTROL Authenticated Profile Options] 您可以選擇 **[!UICONTROL Current Authenticated Profile]** 或 **[!UICONTROL Last Authenticated Profile]**&#x200B;選擇。

## Device Options {#device-options}

The [!UICONTROL Device Options] let you select the type of *`device profile`* used by a [!UICONTROL Profile Merge Rule]. 裝置設定檔是由使用者匿名瀏覽Web時收集的特性組成。描述檔合併規則至少包含已驗證的選項和裝置選項。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無裝置描述檔</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前的裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 描述檔連結裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and the last 3 devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. 最適合在數位資產中擁有高驗證層級的客戶。<span class="wintitle"> 描述檔連結</span> 裝置圖表會即時更新。This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to merge device profiles using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> 是數位合作社，參與客戶在此分享裝置連結資訊。<span class="keyword"> Device Co-op</span> 會在 <span class="term"> 裝置圖表中處理此資料</span>。裝置圖表將裝置叢集連結在一起。These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. 叢集代表未知人員使用的一組裝置。<span class="keyword">Device Co-op</span> 會在其成員間分享這些叢集，如此有助於它們為其客戶提供珍貴而一致的跨裝置體驗。 </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op概觀</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> 成員資格需求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> 裝置圖表：內部流程與輸出</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager和外部裝置圖形</a> (PDF下載)。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方裝置圖表選項(</b> 人員和家庭) </p> </td>
   <td colname="col2"> <p>這些選項可讓您根據第三方廠商提供的裝置圖形技術建立合併規則。協力廠商裝置圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 可能性和/或決定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭層級的資料。 </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. 請連絡您的帳戶管理員以瞭解更多資訊或開始使用。 </p> <p>另請參閱&lt; a href=」.././ features/profile-beath-rules/external-graph-use-cases. md)。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_贊_ this]
>
>* [個人檔案合併規則常見問答集](../../faq/faq-profile-merge.md)

