---
description: 本節概述並說明Audience Manager資料管理平台(DMP)快速入門的相關程式。 本節旨在協助業務團隊、專案經理和技術經理瞭解Audience Manager實作程式。 視您的資料收集需求而定，Audience Manager快速入門可能需要約六週至三個月的時間。
seo-description: This section outlines and explains the processes related to getting started with the Audience Manager data management platform (DMP). This section is designed to help business teams, project managers, and technology managers understand the Audience Manager implementation process. Getting started with Audience Manager can take approximately six weeks to three months, depending on your data collection needs.
seo-title: Implementing Audience Manager
solution: Audience Manager
title: 實作Audience Manager
uuid: 89369224-3b21-45a9-a4ed-a0a977410520
feature: Third-party Integration
exl-id: 8f8a6881-d616-4d0e-aeaa-bf3bb3a172f9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 0%

---

# 實作Audience Manager {#implementing-audience-manager}

本節概述並說明與開始使用Audience Manager資料管理平台([!DNL DMP])相關的程式。 本節旨在協助業務團隊、專案經理和技術經理瞭解Audience Manager實作程式。 視您的資料收集需求而定，Audience Manager快速入門可能需要約六週至三個月的時間。

我們的實作技巧有助於建立與新客戶的顧問合作關係。 此程式旨在：

* 探索並瞭解您的業務需求；
* 產生可執行的計畫以解決這些需求；
* 開發自訂解決方案，協助滿足獨特需求或使用案例；
* 確保您的專屬資料已匯入並可在Audience Manager中使用。

我們的合作夥伴解決方案和客戶管理團隊會在實作程式之前、期間和之後與您密切合作。

Audience Manager會分階段進行設定和實施。

## 定義階段 {#define-phase}

定義階段會向您介紹我們的合作夥伴解決方案專案銷售人員，並開始專案管理流程。

<!-- c_define.xml -->

此步驟旨在協助潛在客戶定義並同意專案範圍、瞭解自訂需求、建立里程碑及設定通訊。

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
     <li id="li_A1B5F443E5864C4CB7A789D6E0B87DF0">介紹專案銷售機會 </li> 
     <li id="li_7F5C0A277FE346A5BA3BA20B21389076">定義角色和責任 </li> 
     <li id="li_991D2F069B88456CB3942970F4EF0FAF">建立與傳送日期繫結的目標和里程碑 </li> 
     <li id="li_4A2CDE7F006A45BDB04585CACF5688CA">確認現場工作計畫 </li> 
     <li id="li_A1BF7C2A34C54387BC945077905C9D04">建立問題和狀態更新的通訊 </li> 
    </ul> </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 提供存取權 </td> 
   <td colname="col2"> 建立共用資源的存取權並分配登入認證 </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 狀態報告和專案團隊呼叫 </td> 
   <td colname="col2"> 建立並維護有關計畫和進度的明確溝通 </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的交付專案可包含下列專案：

* 識別角色和職責的檔案；
* 確定工作範圍的檔案；
* 排程專案會議和通話的計畫；
* 共用資源和存取權的程式。

## 探索階段 {#discovery-phase}

探索階段專用於收集需求、進行研究，以及更深入地瞭解您的業務需求和資料收集策略。

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
     <li id="li_63D9C730FE5A4A55A76C5967A1EFFB8E">開發標籤管理和資料收集計畫 </li> 
     <li id="li_71AC8F2AB5BA4BD29D98D89D9974EDB2">制定符合客戶需求、目標和期望的計畫 </li> 
    </ul> </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 評估資料 </td> 
   <td colname="col2"> 
    <ul id="ul_B7FBA43F94DE45E29B8CB07ABA1D969D"> 
     <li id="li_48FEE16AA5F44A3D846405DA07C9C255">決定如何收集您的資料以及該資料的來源 </li> 
     <li id="li_90D6281EF318401587797013A33B3CBC">探索第一方、第二方和第三方資料的來源 </li> 
    </ul> </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 尋找目的地 </td> 
   <td colname="col2"> 探索使用者端是否將資料傳送至其他廣告伺服器、DSP、網路或交換 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 分組工作階段 </td> 
   <td colname="col2"> 精簡業務需求和需求 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 後續通訊 </td> 
   <td colname="col2"> 定期溝通，以供後續和開發使用 </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的交付成果可包括：

* 已完成的第一方、第二方和第三方資料收集策略；
* 已完成的[!DNL CRM]或資料倉儲擷取計畫；
* 已定義的對象細分需求；
* 完整的資料分類法；
* 已開發的協力廠商資料整合計畫。

## 建置、測試和訓練階段 {#build-test-train-phase}

在建置、測試和訓練階段，您將與指定的合作夥伴解決方案負責人一起檢閱資料收集策略和原型。

<!-- c_build_test_train.xml -->

您的資料收集策略將進行端對端[!DNL QA]測試。 合作夥伴解決方案將追蹤發現的錯誤，並與我們的系統工程師協調問題解決方案。 客戶培訓可以與其他工作同時開始。

下表說明此階段中發生的主要活動：

| 活動 | 用途/說明 | 參與者 |
|---|---|---|
| 準備資料收集策略 | 與Adobe技術團隊合作，建立符合您業務需求的資料收集計畫 | 業務和技術團隊 |
| 部署和測試程式碼 | 在中繼環境中測試建議的解決方案，並執行跨瀏覽器測試 | 技術團隊 |
| 驗證功能並解決錯誤 | 檢查並傳達結果、解決錯誤並重新測試 | 技術團隊 |
| 使用者培訓 | 提供有關Audience Manager功能、工具和報表的教育和瞭解 | 業務團隊 |

此階段的交付成果可包括：

* 已完成且接受的資料收集計畫；
* 端對端[!DNL QA]測試；
* Audience Manager使用者介面功能的基本指示；
* 接受和簽核。

## 啟動、支援和最佳化階段 {#launch-support-optimize-phase}

在啟動、支援和最佳化階段中，您的資料收集和原型實作會從開發移至即時生產環境。 我們將持續進行產品熟悉度與策略的訓練，透過資料導向最佳化協助增加[!DNL ROI]。

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
   <td colname="col2">建立資料收集的真實特徵和區段： 
    <ul id="ul_21C7E86A7AF749CD8ECBE129DE2C641A"> 
     <li id="li_4FCCC879B7A44752A55DEAC2D6434220">建立真實的特徵和區段 </li> 
     <li id="li_329BBFEAFC99488798F97111FFD69853">討論區段建立策略 </li> 
     <li id="li_3F1F2EAFBC544E05B07FDDC452F2FB37">考慮並檢閱使用案例 </li> 
    </ul> </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 進一步培訓 </td> 
   <td colname="col2"> 繼續加深對產品功能、工具和報告的瞭解和熟悉 </td> 
   <td colname="col3"> 業務團隊 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> 後續通訊 </td> 
   <td colname="col2"> 定期排程通訊，以掌握您使用Audience Manager的最新體驗 </td> 
   <td colname="col3"> 業務和技術團隊 </td> 
  </tr> 
 </tbody> 
</table>

此階段的工作可能包括：

* 產生並解譯報表資料；
* 瞭解自訂報表；
* 如何取得產品支援
* 回應或請求功能要求、錯誤和使用者意見回饋；
* 加深對Audience Manager功能和報告的熟悉。

## 程式碼實施 {#code-implementation}

Audience Manager使用Data Integration Library ([!DNL DIL])接收對象資料。

如需如何使用[!DNL DIL]的詳細指示，請參閱[取得及實作DIL程式碼](../dil/dil-overview.md)。

### 參與者

合作夥伴解決方案可直接與您的技術團隊合作，協助部署程式碼、解決最終問題並履行其他需求。

## 實作後支援 {#post-implementation-support}

我們的共同努力不會止步於最終部署。 實施完成後，我們的客戶管理團隊會接管。

產品實作程式完成後，客戶經理會提供持續支援和諮詢服務。 您可以預期定期與客戶經理開會。 這些會議可確保您從Audience Manager中獲得最大的使用量和價值。

請連絡我們[這裡](https://www.adobe.com/products/audiencemanager.html)以取得詳細資訊，並開始使用Audience Manager。
