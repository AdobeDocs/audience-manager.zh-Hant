---
description: 本頁概述合作夥伴在提供資訊時直接提供的資訊，以及與您的Audience manager實務相關的任何暗示。 對於進行這些更新的合作夥伴來說，主要影響是GDPR（通用資料保護規則）的結果，該規則於2018年5月25日生效，以及新的IAB GDPR透明度與同意框架（IAB框架）。
seo-description: 本頁概述合作夥伴在提供資訊時直接提供的資訊，以及與您的Audience manager實務相關的任何暗示。 對於進行這些更新的合作夥伴來說，主要影響是GDPR（通用資料保護規則）的結果，該規則於2018年5月25日生效，以及新的IAB GDPR透明度與同意框架（IAB框架）。
seo-title: 目的地的GDPR考量
solution: Audience Manager
title: 目的地的GDPR考量
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# 目的地的GDPR考量{#gdpr-considerations-for-destinations}

本頁概述合作夥伴在提供資訊時直接提供的資訊，以及與您的Audience manager實務相關的任何暗示。 對於進行這些更新的合作夥伴來說，主要影響是GDPR（通用資料保護規則）的結果，該規則於2018年5月25日生效，以及新的IAB GDPR透明度與同意框架（IAB框架）。

Adobe合作夥伴擁有其商業程式，並可能會決定不時更新其與Audience manager的整合需求。 我們正積極與Audience manager合作夥伴生態系統合作，讓客戶瞭解變化。

## Audience manager合作夥伴更新- ID同步 {#partner-updates-id-syncs}

下表所列的部分合作夥伴已變更與Audience manager的整合要求，加入以IAB架構為基礎的支援，以符合GDPR標準。

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>合作夥伴名稱 </p> </th> 
   <th colname="col2" class="entry"> <p>預期影響 </p> </th> 
   <th colname="col3" class="entry"> <p>更改狀態 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Wonds/DataX </p> </td> 
   <td colname="col2"> <p>合作夥伴會捨棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>自2018年5月22日起生效 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貿易台 </p> </td> 
   <td colname="col2"> <p>合作夥伴會捨棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生存 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>合作夥伴會捨棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生存 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>合作夥伴會捨棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生存 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI更新- Yahoo/Found/DataX整合 {#ui-update}

除了上述IAB架構的更新外，Yahoo/Auncod/DataX還新增了 **gdpr****和** gdpr_mode，以加入其分類和觀眾API。 Their parameters inform Yahoo/Oath/DataX that they have the rights to process a certain segment as a Data Processor or as a Data Controller. 因此，將區段傳送至Yahoo/Aundos/DataX目的地的Audience manager客戶必鬚根據與Aund的同意，指定適當的參數（處理者或控制者）。

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
