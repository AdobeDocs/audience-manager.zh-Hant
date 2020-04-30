---
description: 合併規則選項可讓您控制Audience Manager用於區段的資料類型。 合併規則可包含由Profile Link裝置圖形、Adobe Experience Cloud Device Co-op和／或與Audience Manager整合的其他協力廠商裝置圖形提供者所映射的裝置設定檔。 您最多可以建立4個配置檔案合併規則。
seo-description: 合併規則選項可讓您控制Audience Manager用於區段的資料類型。 合併規則可包含由Profile Link裝置圖形、Adobe Experience Cloud Device Co-op和／或與Audience Manager整合的其他協力廠商裝置圖形提供者所映射的裝置設定檔。 您最多可以建立4個配置檔案合併規則。
seo-title: 定義的配置檔案合併規則選項
solution: Audience Manager
title: 定義的配置檔案合併規則選項
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

合併規則選項可讓您控制Audience Manager用於區段的資料類型。 合併規則可包含由裝置圖形、 [!UICONTROL Profile Link][!UICONTROL Adobe Experience Cloud Device Co-op]和／或與Audience Manager整合的其他協力廠商裝置圖形提供者所映射的裝置設定檔。 最多可建立4個 [!UICONTROL Profile Merge Rules]。 第四個 [!UICONTROL Profile Merge Rule] 方案僅適用於購買附加元件 [!UICONTROL People-Based Destinations] 的客戶。

通過從 [!UICONTROL Profile Merge Rule] 中介紹的選項進行選擇來構建 [!UICONTROL Profile Merge Rule Setup]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

「描述檔合併規則」允許許多規則組合，每個組合都針對特定使用案例。 請參閱下表，以取得有關何時使用每個規則組合的詳細資訊。

| 跨裝置選項 | 裝置選項 | 可用性 | 評估類型 | Audience Lab支援 | 使用個案 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| 無跨裝置描述檔 | 裝置設定檔 | 所有客戶 | 即時和批次 | 是 | [裝置定位](merge-rule-targeting-options.md#device-personalization) |
| 無跨裝置描述檔 | 外部裝置圖表（包括Co-op裝置圖表） | 所有客戶 | 即時和批次 | 無 | [擴充裝置定位](external-graph-use-cases.md#audience-expansion) |
| 目前已驗證的設定檔 | 無設備配置檔案 | 所有客戶 | 僅即時 | 無 | [共用裝置定位](merge-rule-targeting-options.md#target-shared-devices) |
| 上次驗證的設定檔 | 裝置設定檔 | 所有客戶 | 即時和批次 | 是 | [線上／離線定位](merge-rule-targeting-options.md#device-household-targeting) |
| 上次驗證的設定檔 | 描述檔連結裝置圖表 | 所有客戶 | 即時和批次 | 是 | [跨裝置定位](profile-link-use-case.md#cross-device-personalization) |
| 上次驗證的設定檔 | 外部裝置圖表（包括Co-op裝置圖表） | 所有客戶 | 即時和批次 | 無 | [進階跨裝置定位](external-graph-use-cases.md#advanced-graph-expansion) |
| 所有跨裝置描述檔 | 不適用 | 個人型 [目標客戶獨享](../destinations/people-based-destinations-overview.md) | 僅批 | 無 | [以人為本的目標鎖定](merge-rule-targeting-options.md#all-cross-device) |

## 配置檔案合併規則段評估 {#segment-evaluation}

視您的 [!UICONTROL Profile Merge Rules] 設定而定，Audience Manager可以即時、批次或同時執行區段評估。

* 即時區段評估需要 [!DNL DCS] 讓訪客即時存取您的數位屬性，以符合區段資格。
* 批次區段評估是針對先前的合格特徵執行。
* [!UICONTROL Profile Merge Rules] 同時支援即時和批次區段評估的即時訪客活動與先前的合格特徵相結合。

## 描述檔合併規則報告延遲 {#reporting-latency}

即時區段評估會立即反映在報表 [!UICONTROL Profile Merge Rules] 中。

批次區段評估最多需要24小時，才能反映在「描述檔合 [並規則」報表中](profile-link-metrics.md)。

## 跨裝置選項 {#auth-options}

您可 [!UICONTROL Cross-Device Options] 以選擇已驗證和未驗證的使用者，並運用其跨裝置設定檔進行分段。 這些選項可協助您識別並觸及共用裝置上的特定使用者。 如需匿名和已驗證使用者的詳細資訊，請參 [閱Audience Manager中的訪客驗證狀態](../../reference/visitor-authentication-states.md)。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨裝置選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無跨裝置描述檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> ，請勿使用從已驗證使用者收集到的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前已驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，如果訪客已登入您的網站，請將資料讀取並寫入已驗證的描述檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> ，從上次登入裝置之使用者的已驗證設定檔讀取資料。 </p> <p>選取後， <span class="keyword"> Audience Manager</span> 將不會將新特徵資料寫入已驗證的設定檔（如果使用者是匿名的）。 在驗證時，新特徵資料會寫入使用者的驗證設定檔。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨裝置描述檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴Audience Manager從所有跨裝置設定檔讀取資料，不論驗證狀態為何。 此選項僅適用於已購買「人員型目標」附加元件的Audience Manager客戶。</p> </td>
  </tr>
 </tbody>
</table>

## 跨裝置設定檔選項 {#profile-options}

列出 [!UICONTROL Cross-Device Profile Options] 您的跨裝置資料來源。 這些選項會使用您建立跨裝置資料來源時提供的名稱(請參 [閱建立跨裝置資料來源](merge-rules-start.md#create-data-source))。 您最多可以選取3個跨裝置資料來源，以搭配每個描述檔規則使用。 當您 [!UICONTROL Authenticated Profile Options] 選擇或時，即可 **[!UICONTROL Current Authenticated Profiles]** 使用 **[!UICONTROL Last Authenticated Profiles]**。

## 裝置選項 {#device-options}

您 [!UICONTROL Device Options] 可以選取使用 *`device profile`* 的類型 [!UICONTROL Profile Merge Rule]。 裝置設定檔是根據從匿名瀏覽活動收集到的特性來建立。 至少，配置檔案合併規則包括已驗證的選項和設備選項。

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
   <td colname="col2"> <p>告 <span class="keyword"> 訴Audience Manager</span> ，請勿使用匿名設定檔中包含的特徵進行區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> ，使用匿名裝置設定檔進行區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 描述檔連結裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告訴 <span class="keyword"> Audience Manager</span> ，從目前裝置和使用者已驗證的其他多達100部裝置讀取個人檔案。 此裝置圖表是以您在 <span class="keyword"> Audience Manager中的第一方資料為基礎</span>。 它最適合在數位資產中擁有高等級驗證的客戶。 「描 <span class="wintitle"> 述檔連結</span> 」裝置圖表會即時更新。 當您選取「目前已驗證的設定檔」或「上 <b><span class="uicontrol"> 次已驗證的設定檔</span></b> 」時 <b><span class="uicontrol"> ，此選項即可使用</span></b>。 使用此選項時，您只能選擇單一已驗證的個人檔案(<span class="keyword"> Audience Manager</span> 會自動讓其他人昏倒)。 另請參閱描述 <a href="profile-link-use-case.md"> 檔連結裝置圖表使用案例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 合作裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告 <span class="keyword"> 訴Audience Manager</span> ，使用 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op提供的連結，從目前裝置和多達100台其他裝置讀取個人檔案</a>。 </p> <p><span class="keyword"> Device Co-op</span> 是數位合作社，參與客戶在此分享裝置連結資訊。Device <span class="keyword"> Co-op</span> ，會在裝置圖表中處理 <span class="term"> 此資料</span>。 裝置圖形將裝置連結在一起，形成裝置叢集。 這些連結是以概率和 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> 確定性資料建立</a>。 群集表示未知人員使用的一組設備。 <span class="keyword">Device Co-op</span> 會在其成員間分享這些叢集，如此有助於它們為其客戶提供珍貴而一致的跨裝置體驗。 </p> <p> 如需Device Co-op的詳 <span class="wintitle"> 細資訊</span>，請參閱： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Device Co-op概觀</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> 成員資格需求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 裝置圖表： 內部流程和輸出</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager和外部裝置圖形</a> （PDF下載）。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>協力廠商裝置圖形選項</b> （人員與家庭） </p> </td>
   <td colname="col2"> <p>這些選項可讓您根據協力廠商提供的裝置圖形技術，建立合併規則。 協力廠商裝置圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和／或確定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭層級的資料。 </li> 
     </ul> </p> <p>若要使用這些選項，您必須是已與 <span class="keyword"> Audience Manager整合之裝置圖形的客戶</span>。 如需詳細資訊或快速入門，請連絡您的客戶經理。 </p> </td>
  </tr>
 </tbody>
</table>

<!--Victor/Vlad: In the above table, you link to a .pdf file on marketing.adobe.com. Can you move that PDF into Git and link to it? This pdf might get blown away with the marketing.adobe.com decommission. -Bob-->

## 外部合併策略 {#external-merge-policies}

根據Audience Manager以外定義的合併規則，從其他Experience Cloud解決方案自動建立的受眾細分會標籤為使用 [!UICONTROL External Merge Policy]。 例如，請參 [閱「Audience Manager與Adobe Experience Platform之間的觀眾共用」](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

