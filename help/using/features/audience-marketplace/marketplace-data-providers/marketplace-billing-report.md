---
description: 生成Audience Marketplace開單報告，以查看上個月每個訂閱者的資料饋送使用情況。 您可以隨時為上個月建立報告。 但是，在當月第10天或之後生成報告時，報告更準確。
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: 資料摘要提供者的計費方式
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 5%

---

# 資料摘要提供者的計費方式 {#billing-for-data-feed-providers}

生成 [!DNL Audience Marketplace] 開單報告，以查看每個訂閱者上個月的資料饋送使用情況。 您可以隨時為上個月建立報告。 但是，在當月第10天或之後生成報告時，報告更準確。

## 下載計費報告 {#download-billing-report}

要下載報告，請執行以下操作：

1. 轉到 **[!UICONTROL Audience Marketplace > Receivables]**。
1. 按一下 **[!UICONTROL Generate Billing Report]**.

## 已定義報表欄位 {#report-fields-defined}

開單報表包含以下資訊。

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報表欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供程式PID</span></b> </p> </td> 
   <td colname="col2"> <p>您 <span class="keyword"> Audience Manager</span> 資料提供程式ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供程式名稱</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 採購員PID</span></b> </p> </td> 
   <td colname="col2"> <p>採購員（訂閱者）ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 採購員姓名</span></b> </p> </td> 
   <td colname="col2"> <p>採購員的公司或組織名稱。 </p> </td> 
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
   <td colname="col1"> <p><b><span class="uicontrol"> 計畫使用案例</span></b> </p> </td> 
   <td colname="col2"> <p>使用案例讓銷售商能夠控制買家使用資料的方式。 選項包括: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">段和重疊 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">建模 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">啟用 </li> 
    </ul> <p>請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> 資料源的規劃類型</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 單位</span></b> </p> </td> 
   <td colname="col2"> <p>指示CPM或統一費用計費。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 標價</span></b> </p> </td> 
   <td colname="col2"> <p>每個資料饋送的訂閱費。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣價</span></b> </p> </td> 
   <td colname="col2"> <p>折扣資料饋送的訂閱費。 請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> 資料提供程式折扣</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件數</span></b> </p> </td> 
   <td colname="col2"> <p>因供應價格類型而異： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">統一費用資料源：僅返回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM資料饋送：返回CPM資料饋送的實際使用量。 如果用戶沒有為CPM饋送提供印象資料，則「單位」單元為空，並且「標誌」單元設定為1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 總成本</span></b> </p> </td> 
   <td colname="col2"> <p>金額 <span class="keyword"> Audience Manager</span> 給買家開單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 開單期間</span></b> </p> </td> 
   <td colname="col2"> <p> 在報告中，這是上個月的最後一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 進入日期</span></b> </p> </td> 
   <td colname="col2"> <p>採購員輸入訂閱/使用資訊的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱開始日期</span></b> </p> </td> 
   <td colname="col2"> <p>採購員啟動其資料源訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱結束日期</span></b> </p> </td> 
   <td colname="col2"> <p>採購員結束其資料源訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 標誌</span></b> </p> </td> 
   <td colname="col2"> <p> <i>僅用於CPM饋送</i>。 標誌選項包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0:指示訂閱者已將使用資訊報告給 <span class="keyword"> Audience Manager</span>。 </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1:指示訂閱者未向報告使用資訊 <span class="keyword"> Audience Manager</span>。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM資料源的計費和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [統一費用資料源的計費和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何報告CPM使用情況](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

