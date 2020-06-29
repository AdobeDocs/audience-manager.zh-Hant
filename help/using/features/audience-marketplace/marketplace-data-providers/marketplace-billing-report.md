---
description: 產生Audience Marketplace帳單報表，以檢視每個訂閱者上個月的資料饋送使用情形。 您可以隨時建立上個月的報表。 不過，當您在當月的10天或之後產生報表時，報表會更精確。
seo-description: 產生Audience Marketplace帳單報表，以檢視每個訂閱者上個月的資料饋送使用情形。 您可以隨時建立上個月的報表。 不過，當您在當月的10天或之後產生報表時，報表會更精確。
seo-title: 資料摘要提供者的計費方式
solution: Audience Manager
title: 資料摘要提供者的計費方式
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 5%

---


# 資料摘要提供者的計費方式 {#billing-for-data-feed-providers}

產生帳 [!DNL Audience Marketplace] 單報表，以檢視每個訂閱者上個月的資料饋送使用情形。 您可以隨時建立上個月的報表。 不過，當您在當月的10天或之後產生報表時，報表會更精確。

## 下載帳單報表 {#download-billing-report}

若要下載報表：

1. 前往 **[!UICONTROL Audience Marketplace > Receivables]**。
1. 按一下 **[!UICONTROL Generate Billing Report]**.

## 已定義報表欄位 {#report-fields-defined}

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
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供者PID</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 資料提供者名稱</span></b> </p> </td> 
   <td colname="col2"> <p>您的公司或組織名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 購買者PID</span></b> </p> </td> 
   <td colname="col2"> <p>購買者（訂閱者）ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 採購員姓名</span></b> </p> </td> 
   <td colname="col2"> <p>買方的公司或組織名稱。 </p> </td> 
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
   <td colname="col2"> <p>使用案例可讓銷售者控制購買者使用資料的方式。 選項包括: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">區段和重疊 </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">模型 </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">啟用 </li> 
    </ul> <p>請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> 資料饋送的計畫類型</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 單位</span></b> </p> </td> 
   <td colname="col2"> <p>表示CPM或固定費用計費。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 標價</span></b> </p> </td> 
   <td colname="col2"> <p>每個資料饋送的訂閱費用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 折扣價格</span></b> </p> </td> 
   <td colname="col2"> <p>折扣資料饋送的訂閱費用。 請參閱 <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> 資料提供者的折扣</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 件數</span></b> </p> </td> 
   <td colname="col2"> <p>視動態消息價格類型而定： </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">固定費用資料饋送： 僅返回1。 </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM資料饋送： 傳回CPM資料饋送的實際使用量。 如果訂閱者未提供CPM饋送的曝光資料，「單位」儲存格是空的，而「標幟」儲存格設定為1。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 總成本</span></b> </p> </td> 
   <td colname="col2"> <p>Audience Manager向採購 <span class="keyword"> 員收取的金額</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 帳單期間</span></b> </p> </td> 
   <td colname="col2"> <p> 在報表中，這是上個月的最後一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 進入日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者輸入訂閱／使用資訊的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱開始日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者開始其資料饋送訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 訂閱結束日期</span></b> </p> </td> 
   <td colname="col2"> <p>購買者結束其資料饋送訂閱的日期。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 旗標</span></b> </p> </td> 
   <td colname="col2"> <p> <i>僅限CPM摘要</i>。 標籤選項包括： </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: 指出訂閱者已向 <span class="keyword"> Audience Manager報告使用資訊</span>。 </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: 指出訂閱者未向 <span class="keyword"> Audience Manager報告使用資訊</span>。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [CPM資料饋送的帳單和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [固定費用資料饋送的計費和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何報告CPM使用情形](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

