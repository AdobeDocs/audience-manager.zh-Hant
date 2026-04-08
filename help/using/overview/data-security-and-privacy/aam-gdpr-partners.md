---
description: 本頁概述合作夥伴直接提供的資訊 (在可供使用時)，以及與您的 Audience Manager 實務相關的任何含意。對於進行這些更新的合作夥伴來說，主要含意是 2018 年 5 月 25 日生效的 GDPR (一般資料保護規範) 及新推出的 IAB GDPR 透明度與同意框架 (IAB 框架) 的結果。
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: 針對目的地的 GDPR 考量事項
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# 針對目的地的 GDPR 考量事項{#gdpr-considerations-for-destinations}

本頁概述合作夥伴直接提供的資訊 (在可供使用時)，以及與您的 Audience Manager 實務相關的任何含意。對於進行這些更新的合作夥伴來說，主要含意是 2018 年 5 月 25 日生效的 GDPR (一般資料保護規範) 及新推出的 IAB GDPR 透明度與同意框架 (IAB 框架) 的結果。

Adobe 合作夥伴擁有其業務流程，且可決定不定時更新其與 Audience Manager 整合的要求。我們正積極與 Audience Manager 合作夥伴生態系統合作，讓客戶瞭解變動。

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Audience Manager使用者介面更新 — Yahoo/Oath/DataX整合 {#ui-update}

除了上述 IAB 架構的更新外，Yahoo/Oath/DataX 還將 **gdpr** 和 **gdpr_mode** 新增至其分類法和客群 API 中。其參數會通知 Yahoo/Oath/DataX 他們有權以資料處理者或資料控制者的身分處理特定區段。因此，將區段傳送至 Yahoo/Oath/DataX 目的地的 Audience Manager 客戶，必須根據其與 Oath 間的協議指定適當的參數 (處理者或控制者)。

請洽詢您的顧問或客戶服務，設定正確的參數。除非 Adobe 收到請求此更新的書面信函，否則我們無法代表客戶進行此更新。請洽詢您的 Yahoo/Oath/DataX 代表，瞭解這些參數的完整定義。
