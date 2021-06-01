---
description: 本節概述並說明與開始使用Audience Manager資料管理平台(DMP)相關的程式。 本節旨在協助業務團隊、專案經理和技術經理了解Audience Manager實作流程。 根據您的資料收集需求，開始使用Audience Manager可能需要約6週到3個月。
seo-description: 本節概述並說明與開始使用Audience Manager資料管理平台(DMP)相關的程式。 本節旨在協助業務團隊、專案經理和技術經理了解Audience Manager實作流程。 根據您的資料收集需求，開始使用Audience Manager可能需要約6週到3個月。
seo-title: 實作 Audience Manager
solution: Audience Manager
title: 實作 Audience Manager
uuid: 89369224-3b21-45a9-a4ed-a0a977410520
feature: 協力廠商整合
exl-id: 8f8a6881-d616-4d0e-aeaa-bf3bb3a172f9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 1%

---

# 實作 Audience Manager {#implementing-audience-manager}

本節概述並說明與開始使用Audience Manager資料管理平台([!DNL DMP])相關的程式。 本節旨在協助業務團隊、專案經理和技術經理了解Audience Manager實作流程。 根據您的資料收集需求，開始使用Audience Manager可能需要約6週到3個月。

我們的實施技術有助於與新客戶建立協商式合作關係。 此程式的設計目的為：

* 了解並了解您的業務需求；
* 制定可行的計畫，以滿足這些要求；
* 開發自訂解決方案，以滿足獨特需求或使用案例；
* 請確定您的專有資料已匯入並可在Audience Manager中使用。

我們的合作夥伴解決方案和客戶管理團隊在實施程式之前、期間和之後將與您密切合作。

Audience Manager採用分階段的方式來設定和實作。

## 定義階段{#define-phase}

定義階段將向您介紹我們的合作夥伴解決方案項目主管，並開始項目管理流程。

<!-- c_define.xml -->

此步驟旨在幫助潛在客戶定義並商定項目範圍、了解自訂需求、建立里程碑和設定通信。

下表說明此階段中發生的主要活動：

<table id="table_E6E4DA99B19244FB996CC3AB42CEA5DA"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> 活動 </th> 
   <th colname="col2" class="entry"> 用途/說明 </th> 
   <th colname="col3" class="entry"> 建議的參與者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> 啟動通話/會議 </td> 
   <td colname="col2"> 
    <ul id="ul_E8F427586F14437285ABBF93A15FCBD4"> 
     <li id="li_A1B5F443E5864C4CB7A789D6E0B87DF0">介紹項目線索 </li> 
     <li id="li_7F5C0A277FE346A5BA3BA20B21389076">定義角色和責任 </li> 
     <li id="li_991D2F069B88456CB3942970F4EF0FAF">建立與傳送日期相連的目標和里程碑 </li> 
     <li id="li_4A2CDE7F006A45BDB04585CACF5688CA">確認現場工作計畫 </li> 
     <li id="li_A1BF7C2A34C54387BC945077905C9D04">建立問題和狀態更新的通信 </li> 
    </ul> </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 提供存取權 </td> 
   <td colname="col2"> 建立對共用資源的訪問權限並分發登錄憑據 </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 狀態報表和專案團隊呼叫 </td> 
   <td colname="col2"> 建立並保持關於計畫和進展的明確溝通 </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的交付項可包括以下內容：

* 確定角色和責任的文檔；
* 確定工作範圍的檔案；
* 計畫安排項目會議和呼叫；
* 共用資源和存取的程式。

## 發現階段{#discovery-phase}

發現階段致力於收集需求、進行研究，並致力於加深對業務需求和資料收集策略的了解。

<!-- c_discovery.xml -->

下表說明此階段中發生的主要活動：

<table id="table_89E7CD7832E142519EDC1F285A5BBE79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活動 </th> 
   <th colname="col2" class="entry"> 用途/說明 </th> 
   <th colname="col3" class="entry"> 建議的參與者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> 需求和目標設定 </td> 
   <td colname="col2"> 
    <ul id="ul_CB78589D5906439F8632A0C4B6F4130A"> 
     <li id="li_63D9C730FE5A4A55A76C5967A1EFFB8E">制定標籤管理和資料收集計畫 </li> 
     <li id="li_71AC8F2AB5BA4BD29D98D89D9974EDB2">制定符合客戶需求、目標和期望的計畫 </li> 
    </ul> </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 評估資料 </td> 
   <td colname="col2"> 
    <ul id="ul_B7FBA43F94DE45E29B8CB07ABA1D969D"> 
     <li id="li_48FEE16AA5F44A3D846405DA07C9C255">決定如何收集您的資料及該資料的來源 </li> 
     <li id="li_90D6281EF318401587797013A33B3CBC">探索第一方、第二方和第三方資料的來源 </li> 
    </ul> </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 尋找目的地 </td> 
   <td colname="col2"> 探索用戶端是否將資料傳送至其他廣告伺服器、DSP、網路或交換 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 分組會議 </td> 
   <td colname="col2"> 調整業務需求和需求 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 後續交流 </td> 
   <td colname="col2"> 為後續工作和發展目的定期交流 </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的交付項可包括：

* 完整的第一方、第二方和第三方資料收集策略；
* 已完成的[!DNL CRM]或資料倉庫獲取計畫；
* 定義的受眾細分需求；
* 完成資料分類；
* 已開發的協力廠商資料整合計畫。

## 構建、測試和訓練階段{#build-test-train-phase}

在建立、測試和培訓階段，您將與指定的合作夥伴解決方案主管一起審查資料收集策略和原型。

<!-- c_build_test_train.xml -->

您的資料收集策略將進行端對端[!DNL QA]測試。 合作夥伴解決方案將跟蹤發現的錯誤並與我們的系統工程師協調解決問題。 客戶培訓可以與這些其他工作同時開始。

下表說明此階段中發生的主要活動：

| 活動 | 用途/說明 | 參與者 |
|---|---|---|
| 準備資料收集策略 | 與Adobe技術團隊合作，建立符合您業務需求的資料收集計畫 | 商業與技術團隊 |
| 部署和測試程式碼 | 在測試環境中測試建議的解決方案，並執行跨瀏覽器測試 | 技術團隊 |
| 驗證功能並解決錯誤 | 檢查並傳達結果、解決錯誤並重新測試 | 技術團隊 |
| 使用者訓練 | 提供Audience Manager功能、工具和報表的相關教育與了解 | 業務團隊 |

此階段的交付項可包括：

* 完成並接受的資料收集計畫；
* 端對端[!DNL QA]測試；
* Audience Manager用戶介面功能的基本說明；
* 接受和簽核。

## 啟動、支援和優化階段{#launch-support-optimize-phase}

在啟動、支援和最佳化階段，您的資料收集和原型實作會從開發環境移至即時的生產環境。 我們將繼續進行有關產品熟悉和策略的培訓，這些有助於通過資料驅動的優化來提高您的[!DNL ROI]。

<!-- c_launch_support_optimize.xml -->

下表說明此階段中發生的主要活動：

<table id="table_040B9CBED6F04A41B4501DA4B45F5A16"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活動 </th> 
   <th colname="col2" class="entry"> 用途/說明 </th> 
   <th colname="col3" class="entry"> 參與者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> 資料分析和最佳化 </td> 
   <td colname="col2"> 分析資料趨勢並提供最佳化建議 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 建立特徵和區段 </td> 
   <td colname="col2">為資料收集建立真實特徵和區段： 
    <ul id="ul_21C7E86A7AF749CD8ECBE129DE2C641A"> 
     <li id="li_4FCCC879B7A44752A55DEAC2D6434220">建立真實特徵和區段 </li> 
     <li id="li_329BBFEAFC99488798F97111FFD69853">討論區段建立策略 </li> 
     <li id="li_3F1F2EAFBC544E05B07FDDC452F2FB37">考慮和審查使用案例 </li> 
    </ul> </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 進一步培訓 </td> 
   <td colname="col2"> 繼續了解並熟悉產品功能、工具和報表 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 後續溝通 </td> 
   <td colname="col2"> 定期排程通訊，隨時掌握您的使用者Audience Manager體驗 </td> 
   <td colname="col3"> 商業與技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的任務包括：

* 產生和解譯報表資料；
* 了解自訂報表；
* 如何取得產品支援
* 回應或索取功能要求、錯誤和使用者意見；
* 深入了解Audience Manager功能和報表。

## 代碼實施{#code-implementation}

Audience Manager使用Data Integration Library([!DNL DIL])來接收受眾資料。

有關如何使用[!DNL DIL]的詳細說明，請參閱[取得並實作DIL程式碼](../dil/dil-overview.md)。

### 參與者

合作夥伴解決方案可以直接與您的技術團隊合作，協助部署程式碼、解決最終問題，並滿足其他需求。

## 實施後支援{#post-implementation-support}

我們的協作努力不會因最終部署而停止。 實作完成後，我們的帳戶管理團隊將接管。

客戶經理在產品實施過程完成後提供持續的支援和咨詢服務。 您可以期望與客戶經理定期會面。 這些會議確保您從Audience Manager中獲得最大的使用量和價值。

如需詳細資訊，請連絡我們[這裡](https://www.adobe.com/products/audiencemanager.html)以開始使用Audience Manager。
