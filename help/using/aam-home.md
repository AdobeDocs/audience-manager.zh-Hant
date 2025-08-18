---
description: Audience Manager 提供領先業界的線上受眾資料管理服務。我們的產品和服務提供數位廣告商和發佈商所需的工具，可用來控制並運用其資料資產以協助推動銷售佳績。
seo-description: Technical documentation and self help for Audience Manager (AAM). AAM provides industry-leading services for online audience data management, and give digital advertisers and publishers the tools they need to control and leverage their data assets to help drive sales success.
seo-title: Adobe Audience Manager Product Technical Documentation
solution: Audience Manager
title: Audience Manager 指南
uuid: 48267e3b-70e6-42ae-99b1-884f4d0916be
feature: Overview
exl-id: a47bf8ba-4ec0-4b3b-ad20-4afb7c9f924b
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 92%

---

# Audience Manager 指南 {#audience-manager-product-documentation}

Audience Manager 為領先業界的線上受眾資料管理服務，本技術文件指南針對 Audience Manager 提供自助協助。我們的產品和服務提供數位廣告商和發佈商所需的工具，可用來控制並運用其資料資產以協助推動銷售佳績。

## 使用本指南

* 在&#x200B;**左側導覽**&#x200B;中依主題和子主題探索內容。
* 如果您知道要尋找什麼，請使用頁面頂端的&#x200B;**搜尋**&#x200B;欄位。
* 使用頁面右上角的&#x200B;**記錄問題**&#x200B;按鈕，指出任何不正確或過時的文件。請參閱[共同作業指南](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=zh-Hant)概述，瞭解如何開始貢獻內容。

## 如何閱讀本頁面

* 首先，請探索 **Audience Manager 主要功能**&#x200B;區段以取得問題快照，方便 Audience Manager 協助您解決問題。也請閱讀 [Audience Manager 概述](/help/using/overview/aam-overview.md)，然後再返回本頁。
* 接下來，請閱讀 **Audience Manager 快速入門**，熟悉 Audience Manager 概念。另外請務必檢閱商業與技術實作指南。
* 請參閱最新的 Audience Manager 發行說明，並閱讀&#x200B;**發行說明和最新功能**&#x200B;區段中的最新功能相關內容。
* 最後，您可以在&#x200B;**學習中心 - 建議的 Audience Manager 和 Experience Cloud 資源**&#x200B;區段中，探索更多 Experience Cloud 資源，例如論壇、影片教學課程、面對面和線上培訓課程。

## Audience Manager 主要功能

<table style="table-layout:fixed">
   <td>
      <img alt="資料輸入" src="/help/using/overview/assets/data-in.png"/>
      <div>
         <b>匯入資料</b>
      </div>
      <p>
         <em><ul><li><a href="/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md">資料收集伺服器</a></li><li><a href="/help/using/integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md">批次資料擷取</a></li><li><a href="/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md">記錄擷取</a></li><li><a href="/help/using/integration/integration-other-solutions/audience-management-module.md">將 Adobe Analytics 資料轉送至 Audience Manager</a></li></ul></em>
      <p>
   </td>
   <td>
      <img alt="豐富和區段" src="/help/using/overview/assets/enrich-segment.png"/>
      <div>
         <b>豐富和區段</b>
      </div>
      <p>
       <em><ul><li><a href="/help/using/features/segments/segments-purpose.md">細分</a></li><li><a href="/help/using/features/profile-merge-rules/merge-rules-overview.md">設定檔合併規則</a></li><li><a href="/help/using/features/algorithmic-models/understanding-models.md">演算法建模</a></li><li><a href="/help/using/overview/data-types-collected.md">第二方和第三方資料</a></li></ul></em>
      <p>
   </td>
   <td>
      <img alt="資料輸出" src="/help/using/overview/assets/data-out.png"/>
      </a>
      <div>
         <b>匯出資料</b>
      </div>
      <p>
      <p>
         <em><ul><li><a href="/help/using/integration/receiving-audience-data/receiving-audience-data-overview.md">批次與即時資料匯出</a></li><li><a href="/help/using/features/destinations/destinations.md">目的地概述</a></li><li><a href="/help/using/features/destinations/device-based-destinations-list.md">以裝置為基礎的目的地清單</a></li><li><a href="/help/using/features/destinations/people-based-destinations-overview.md">以人物為基礎的目的地</a></li></ul></em> 
      <p>
      <p>
   </td>
</table>


## Audience Manager 快速入門

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>重要概念文件</b></p>
   <p>請閱讀下列頁面，進一步瞭解 Audience Manager 概念： 
   <ul><li><a href="/help/using/overview/aam-overview.md"> Audience Manager 概述</a></li><li><a href="/help/using/reference/signal-trait-segment.md">訊號、特徵和區段</a></li><li><a href="/help/using/reference/aam-glossary.md"> 字彙表</a> </li><li><a href="/help/using/reference/ids-in-aam.md">ID 索引</a></li></ul></p>

<p><b>實作 Audience Manager</b></p>
   <p> 閱讀以下頁面，開始實作 Audience Manager：
     <ul>
     <li><a href="/help/using/integration/data-integration-methods.md">資料整合方法</a></li>
     <li><a href="/help/using/integration/implement-audience-manager.md">實作指南</a></li>
     </ul> </p>

<p> <b>技術實作指南</b> </p> <p>開始使用 Audience Manager API，並在您的應用程式中設定 Audience Manager：</p> <p> 
     <ul id="ul_47C012F6AB3E4B73BA357027F4D15369">
     <li><a href="/help/using/api/rest-api-main/aam-api-getting-started.md">REST API 快速入門</a></li>
     <li><a href="/help/using/api/dcs-intro/dcs-event-calls/dcs-event-calls.md">開始使用 DCS API</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=zh-Hant">在Adobe Experience Platform標籤中新增Audience Manager擴充功能</a></li>
    <li><a href="https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/data-management/aam-dil-extension.html?lang=zh-Hant">將 Audience Manager 新增至您的應用程式</a></li>
     </ul> </p>
    </td>

</tr> 
 </tbody> 
</table>

<!--

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Important Conceptual Documentation</b></p>
   <p>Read the pages below for a deeper understanding of Audience Manager concepts: 
   <ul><li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/aam-overview.html?lang=zh-Hant"> Audience Manager Overview</a></li><li><a href="https://docs.adobe.com/help/en/audience-manager/user-guide/reference/aam-glossary.html"> Glossary</a> </li><li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/ids-in-aam.html?lang=zh-Hant">Index of IDs</a></li><li><a href="https://docs.adobe.com/help/en/audience-manager/user-guide/reference/signal-trait-segment.html">Signals, Traits, and Segments</a></li></ul></p>
   <br>&nbsp;
   <p><b>Implement Audience Manager</b></p>
   <p> Get started with implementing Audience Manager by reading the pages below:
     <ul>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/data-integration-methods.html?lang=zh-Hant">Data Integration Methods</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/implement-audience-manager.html?lang=zh-Hant">Implementation Guide</a></li>
     </ul> </p>
     <br>&nbsp;
   <p> <b>Technical Implementation Guides</b> </p> <p>Get started with Audience Manager APIs and set up Audience Manager in your app:</p> <p> 
     <ul id="ul_47C012F6AB3E4B73BA357027F4D15369">
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/rest-apis/aam-api-getting-started.html?lang=zh-Hant">Getting Started with REST APIs</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-event-calls/dcs-event-calls.html?lang=zh-Hant">Get started with the DCS API</a></li>
     <li><a href="https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html?lang=zh-Hant">Add the Audience Manager extension to Adobe Experience Platform Launch</a></li>
    <li><a href="https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/data-management/aam-dil-extension.html?lang=zh-Hant">Add Audience Manager to your app</a></li>
     </ul> </p>
    </td>
   <td colname="col2">  <p> <b>Collaborative Documentation</b> </p>
     <p>We welcome contributions to our documentation from all our readers. See the <a href="https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=zh-Hant">Collaboration Guide Overview</a> to learn how to start contributing.</p>
   <br>&nbsp;
   <p> <b>Release Notes</b> </p> <p> 
     See the latest <a href="https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant" format="https" scope="external"> Experience Cloud Release Notes</a> for new features and fixes.</p> <br>&nbsp;
     <p> <b>Experience Cloud Resources</b> </p> <p> 
     <ul id="ul_E30EC96BDC624B5591F0470D430B7F41"> 
      <li id="li_F3A5CCFAE0F247CEB41A03CA8E03106B"><a href="https://forums.adobe.com/community/experience-cloud/analytics-cloud/audience-manager" format="https" scope="external"> Audience Manager Community Forums</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/overview.html?lang=zh-Hant" format="http" scope="external"> Audience Manager Tutorials</a> </li> 
      <li id="li_1737D63307024F26B1F967621613A5AC"><a href="https://www.adobe.com/privacy.html" format="http" scope="external"> Adobe Privacy Center</a> </li>  
      <li id="li_1938F7044F544481A6CC0F45CC22B80A"> <a href="https://helpx.adobe.com/tw/learning.html?promoid=KAUDK" scope="external" format="http"> Adobe Training and Certifications</a> </li> 
      <li id="li_C71459E0D1464C05B8B9387C43541F17"> <a href="https://helpx.adobe.com/tw/support/experience-cloud.html" scope="external" format="https">Experience Cloud Product Documentation Home</a> </li> 
      <li id="li_0DB1997FEB87484EBC07E03FD40AA39F"><a href="https://helpx.adobe.com/tw/support/audience-manager.html" format="https" scope="external"> Audience Manager Learn &amp; Support</a> </li> 
     </ul> </p> 
     <br>&nbsp;
     <p>See also, <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/documentation-updates/docs-2020.html?lang=zh-Hant"> 2020 Documentation Updates</a>. </p> </td>
  </tr> 
 </tbody> 
</table>

-->

## 發行說明和最新功能

<table> 
 <tbody> 
  <tr> 
   <td> <p> <b>發行說明</b> </p> <p> 
     請參閱最新的 <a href="https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant" format="https" scope="external">Experience Cloud 發行說明</a>，瞭解全新功能和修正內容。</p> 
     <p> <b>最新功能</b> </p> <p> 
     閱讀有關最新 Audience Manager 功能的資訊：</p>
     <p><ul><li><a href="/help/using/docs-updates/docs-2021.md">Audience Manager使用者移轉至Admin Console</a></li><li><a href="/help/using/features/destinations/people-based-destinations-prerequisites.md">以人物為基礎的目的地的Google Customer Match</a></li><li><a href="/help/using/overview/data-security-and-privacy/aam-iab-plugin.md">適用於IAB TCF v2.2的Audience Manager外掛程式</a></li><li><a href="/help/using/features/algorithmic-models/predictive-audiences.md">預測客群</a></li><li><a href="/help/using/features/administration/activity-usage-reporting.md">活動使用情況報表</a></li>
     </ul></p>
    </td>
  </tr> 
 </tbody> 
</table>

<!--

**Release Notes**

See the latest [Experience Cloud Release Notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant) for new features and fixes.

<br>&nbsp;

**Latest features**

Read about the latest Audience Manager features:
* [Activity Usage Reporting](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/activity-usage-reporting.html?lang=zh-Hant)
* [California Consumer Privacy Act (CCPA) Support and Privacy Documentation Overhaul](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=zh-Hant)
* [Intelligent Recommendations for Audience Marketplace Data, powered by Adobe Sensei](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/trait-recommendations.html?lang=zh-Hant)
* [Profile Merge Rules Enhancements](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html?lang=zh-Hant)
* [Bulk Management Tools Update](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/bulk-management-tools/bulk-management-intro.html?lang=zh-Hant)

-->


## 學習中心 - 建議的 Audience Manager 和 Experience Cloud 資源


<table> 
 <tbody> 
  <tr> 
   <td colname="col2"> 
     <p> <b>Experience Cloud 資源</b> </p>
     <p>請造訪以下連結，與社群論壇中的其他 Audience Manager 客戶交流，觀看各種功能的教學課程影片，或在學習與支援中心排解疑難問題。</p>
     <p> 
     <ul id="ul_E30EC96BDC624B5591F0470D430B7F41"> 
      <li id="li_F3A5CCFAE0F247CEB41A03CA8E03106B"><a href="https://forums.adobe.com/community/experience-cloud/analytics-cloud/audience-manager" format="https" scope="external"> Audience Manager 社群論壇</a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/overview.html?lang=zh-Hant" format="http" scope="external"> Audience Manager 教學課程</a> </li> 
      <li id="li_1737D63307024F26B1F967621613A5AC"><a href="https://www.adobe.com/tw/privacy.html" format="http" scope="external"> Adobe 隱私權中心</a> </li>  
      <li id="li_1938F7044F544481A6CC0F45CC22B80A"> <a href="https://helpx.adobe.com/tw/learning.html?promoid=KAUDK" scope="external" format="http"> Adobe 培訓和認證</a> </li> 
      <li id="li_C71459E0D1464C05B8B9387C43541F17"> <a href="https://helpx.adobe.com/tw/support/experience-cloud.html" scope="external" format="https">Experience Cloud 產品文件首頁</a> </li> 
      <li id="li_0DB1997FEB87484EBC07E03FD40AA39F"><a href="https://helpx.adobe.com/tw/support/audience-manager.html" format="https" scope="external"> Audience Manager 學習與支援</a> </li> 
     </ul> </p> 
     <p>另請參閱 <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/documentation-updates/docs-2021.html?lang=zh-Hant">2021 年文件更新</a>。 </p> </td>
  </tr> 
 </tbody> 
</table>
