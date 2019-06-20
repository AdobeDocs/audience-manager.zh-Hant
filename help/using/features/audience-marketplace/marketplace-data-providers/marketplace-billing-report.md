---
description: 產生Audience Marketplace帳單報表，以檢視每位訂戶的前一個月份資料饋送使用情形。您可以隨時建立上個月的報表。不過，當您在當月的10天後或之後產生報表時，會比較準確。
seo-description: 產生Audience Marketplace帳單報表，以檢視每位訂戶的前一個月份資料饋送使用情形。您可以隨時建立上個月的報表。不過，當您在當月的10天後或之後產生報表時，會比較準確。
seo-title: 資料饋送供應商帳單
solution: Audience Manager
title: 資料饋送供應商帳單
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66 d-86a92 e0 de655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Billing for Data Feed Providers {#billing-for-data-feed-providers}

Generate an [!DNL Audience Marketplace] billing report to view data feed usage for the previous month for each of your subscribers. 您可以隨時建立上個月的報表。不過，當您在當月的10天後或之後產生報表時，會比較準確。

## Download a Billing Report {#download-billing-report}

若要下載報表：

1. **[!UICONTROL Audience Marketplace > Receivables]** 前往。
1. Click **[!UICONTROL Generate Billing Report]**.

## Report Fields Defined {#report-fields-defined}

帳單報表包含下列資訊。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報表欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料供應商PID</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購買者PID</span></b> </p> </td> 
   <td colname="col2"> <p>購買者(訂閱者) ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購買者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>購買者的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 摘要 ID</span></b> </p> </td> 
   <td colname="col2"> <p>資料饋送的ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 摘要名稱</span></b> </p> </td> 
   <td colname="col2"> <p>資料饋送的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 計劃使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用個案可讓賣家控制買家使用資料的方式。選項包括: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">區段與重疊 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">模型化 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">啟用 </li> 
    </ul> <p>See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plan Types for Data Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 度量單位</span></b> </p> </td> 
   <td colname="col2"> <p>表示CPM或固定費用計費。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 價目表價格</span></b> </p> </td> 
   <td colname="col2"> <p>每個資料饋送的訂閱費用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣價格</span></b> </p> </td> 
   <td colname="col2"> <p>折扣資料饋送的訂閱費用。See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Discounts for Data Providers</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件數</span></b> </p> </td> 
   <td colname="col2"> <p>依摘要價格類型而異： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">固定費用資料饋送：僅傳回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM資料饋送：傳回CPM資料饋送的實際使用量。如果訂戶未提供CPM饋送的曝光資料，則「件數」儲存格為空，而「旗標」儲存格則設為1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 總成本</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 帳單的金額。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 計費期間</span></b> </p> </td> 
   <td colname="col2"> <p> 在報表中，這是上個月的最後一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 進入日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者輸入訂閱/使用資訊的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱開始日期</span></b> </p> </td> 
   <td colname="col2"> <p>買家開始其資料饋送訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱結束日期</span></b> </p> </td> 
   <td colname="col2"> <p>買家結束資料饋送訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 旗標</span></b> </p> </td> 
   <td colname="col2"> <p> <i>僅限CPM餵送</i>。標記選項包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indicates a subscriber has reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indicates a subscriber has not reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [CPM資料饋送的帳單和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [持平費用資料饋送的計費和曝光分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何報告CPM使用情形](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

