---
description: 產生Audience Marketplace計費報告，以檢視每個訂閱者上個月的資料摘要使用量。 您可以隨時建立上個月的報表。 不過，如果您在當月的第10天或之後產生報表，報表會更準確。
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: 資料摘要提供者的計費方式
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# 資料摘要提供者的計費方式 {#billing-for-data-feed-providers}

產生[!DNL Audience Marketplace]計費報告，以檢視每個訂閱者上個月的資料摘要使用量。 您可以隨時建立上個月的報表。 不過，如果您在當月的第10天或之後產生報表，報表會更準確。

## 下載計費報告 {#download-billing-report}

若要下載報表：

1. 移至&#x200B;**[!UICONTROL Audience Marketplace > Receivables]**。
1. 按一下 **[!UICONTROL Generate Billing Report]**。

## 已定義的報表欄位 {#report-fields-defined}

帳單報告包含下列資訊。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">資料提供者PID</span></b> </p> </td> 
   <td colname="col2"> <p>您的<span class="keyword">Audience Manager</span>資料提供者識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">資料提供者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">購買者PID</span></b> </p> </td> 
   <td colname="col2"> <p>購買者（訂閱者）識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">購買者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>採購員的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">摘要識別碼</span></b> </p> </td> 
   <td colname="col2"> <p>資料摘要的ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">摘要名稱</span></b> </p> </td> 
   <td colname="col2"> <p>資料摘要的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">個計畫使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用案例可讓賣家控制買家如何使用資料。 選項包括: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">區段和重疊 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">模型 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">啟用 </li> 
    </ul> <p>檢視資料摘要</a>的<a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types">計畫型別。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">量值單位</span></b> </p> </td> 
   <td colname="col2"> <p>表示CPM或固定費用帳單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">定價</span></b> </p> </td> 
   <td colname="col2"> <p>每個資料摘要的訂閱費用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">折扣價</span></b> </p> </td> 
   <td colname="col2"> <p>折扣資料摘要的訂閱費用。 檢視資料提供者</a>的<a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts">折扣。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">單位</span></b> </p> </td> 
   <td colname="col2"> <p>依摘要價格型別而異： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">固定費用資料摘要：僅傳回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM資料摘要：傳回CPM資料摘要的實際使用量。 如果訂閱者未提供CPM饋送的曝光資料，單位儲存格會是空的，且旗標儲存格會設為1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總成本<b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>金額<span class="keyword">Audience Manager</span>為買家記帳。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">記帳期間</span></b> </p> </td> 
   <td colname="col2"> <p> 在報表中，這是上個月的最後一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">專案日期</span></b> </p> </td> 
   <td colname="col2"> <p>採購員輸入訂閱/使用量資訊的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">訂閱開始日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者開始訂閱資料摘要的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">訂閱結束日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者結束其資料摘要訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">旗標</span></b> </p> </td> 
   <td colname="col2"> <p> <i>僅適用於CPM摘要</i>。 標幟選項包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0：表示訂閱者已向<span class="keyword">Audience Manager</span>回報使用資訊。 </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1：表示訂閱者尚未向<span class="keyword">Audience Manager</span>回報使用資訊。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM資料摘要的計費和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [固定費用資料摘要的帳單和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何報告CPM使用量](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
