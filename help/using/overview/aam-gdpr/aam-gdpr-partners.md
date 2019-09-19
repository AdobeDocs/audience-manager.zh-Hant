---
description: 本頁概述合作夥伴在提供資訊時直接提供的資訊，以及與您的Audience manager實務相關的任何暗示。 對於進行這些更新的合作夥伴來說，主要影響是GDPR（通用資料保護規則）的結果，該規則於2018年5月25日生效，以及新的IAB GDPR透明度與同意框架（IAB框架）。
seo-description: 本頁概述合作夥伴在提供資訊時直接提供的資訊，以及與您的Audience manager實務相關的任何暗示。 對於進行這些更新的合作夥伴來說，主要影響是GDPR（通用資料保護規則）的結果，該規則於2018年5月25日生效，以及新的IAB GDPR透明度與同意框架（IAB框架）。
seo-title: 目的地的GDPR考量
solution: Audience Manager
title: 目的地的GDPR考量
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

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

除了上述IAB架構的更新外，Yahoo/Auncod/DataX還新增了 **gdpr****和** gdpr_mode，以加入其分類和觀眾API。 其參數會通知Yahoo/Wonds/DataX，他們有權以資料處理者或資料控制者的身分處理特定區段。 因此，將區段傳送至Yahoo/Aundos/DataX目的地的Audience manager客戶必鬚根據與Aund的同意，指定適當的參數（處理者或控制者）。

請洽詢您的顧問或客戶服務，以設定正確的參數。 除非我們收到要求此更新的書面信件，否則Adobe無法代表客戶進行此更新。 請連絡您的Yahoo/Woand/DataX代表，以瞭解這些參數的完整定義。

## Audience manager合作夥伴具備取消細分功能 {#aam-partners-with-unsegmentation}

為協助客戶自動化GDPR要求，Audience manager會傳送取消區隔（或移除區段）資訊，通知啟動合作夥伴有關資料主體的刪除要求。

不過，我們的部分啟動合作夥伴：

1. 無法支援Adobe和／或
1. 無法在30天內以超過一次的頻率收到我們的更新。

在這些情況下，您無法透過Audience manager以自動方式傳送刪除要求給啟動合作夥伴。 下載我們 [的Partner excel表單](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) ，以瞭解哪些Audience manager啟動合作夥伴支援取消細分。
