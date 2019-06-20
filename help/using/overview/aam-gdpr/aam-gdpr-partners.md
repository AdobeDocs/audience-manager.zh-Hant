---
description: 本頁概述我們的合作夥伴直接提供的資訊，以及與您Audience Manager實務相關的任何暗示。對促成這些更新的合作夥伴而言，主要意義是GDPR(通用資料保護規則)的結果，該法規自2018年月25日生效，以及新的IAB GDPR透明度與同意框架(IAB Framework)生效。
seo-description: 本頁概述我們的合作夥伴直接提供的資訊，以及與您Audience Manager實務相關的任何暗示。對促成這些更新的合作夥伴而言，主要意義是GDPR(通用資料保護規則)的結果，該法規自2018年月25日生效，以及新的IAB GDPR透明度與同意框架(IAB Framework)生效。
seo-title: 目標的GDPR考量
solution: Audience Manager
title: 目標的GDPR考量
uuid: e8a40060-086c-4f03-b48 c-9c9 c903 acb7891
translation-type: tm+mt
source-git-commit: 0ddc86391cbc751dfd4d46946222d555cefbfe38

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

本頁概述我們的合作夥伴直接提供的資訊，以及與您Audience Manager實務相關的任何暗示。對促成這些更新的合作夥伴而言，主要意義是GDPR(通用資料保護規則)的結果，該法規自2018年月25日生效，以及新的IAB GDPR透明度與同意框架(IAB Framework)生效。

Adobe合作夥伴擁有其業務流程，且可能會不時決定與Audience Manager更新其整合需求。我們主動與Audience Manager合作夥伴生態系統合作，讓客戶獲得變更。

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

下表列出一些合作夥伴已變更其整合需求，以納入根據IAB Framework的支援，以符合GDPR標準。

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>合作夥伴名稱 </p> </th> 
   <th colname="col2" class="entry"> <p>預期影響 </p> </th> 
   <th colname="col3" class="entry"> <p>變更狀態 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataXX </p> </td> 
   <td colname="col2"> <p>合作夥伴放棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>自2018年月22日起上線 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>合作夥伴放棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未上線 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>合作夥伴放棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未上線 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiverAp </p> </td> 
   <td colname="col2"> <p>合作夥伴放棄歐盟使用者的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未上線 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. 參數會通知Yahoo/Oat/DataXX他們有權將特定區段處理為資料處理方或資料控制方。因此，將區段傳送至Yahoo/Oat/DataAX目的地的Audience Manager客戶必須指定適當的參數(處理器或控制器)，根據他們與Oath的協議。

請連絡您的顧問或Client Care以設定正確參數。除非我們收到書面信函，否則Adobe不能代表客戶進行此項更新。請聯絡Yahoo/Oath/DataAX代表以瞭解這些參數的完整定義。

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

為協助客戶自動化GDPR要求，Audience Manager會傳送資料主體取消區段(或移除區段)資訊，通知啓動合作夥伴有關刪除要求的通知。

不過，我們的啓動合作夥伴：

1. 無法支援Adobe及/或
1. 30天內無法更頻繁地接收我們的更新。

在這種情況下，您無法透過Audience Manager自動傳送刪除要求給啓動合作夥伴。Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-March2019.xlsx) to see which Audience Manager activation partners support unsegment.
