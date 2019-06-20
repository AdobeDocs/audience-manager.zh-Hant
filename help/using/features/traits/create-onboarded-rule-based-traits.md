---
description: 說明設定規則型和已登錄特徵建立程序專屬的步驟和功能。
keywords: 建立特徵；建立特徵
seo-description: 說明設定規則型和已登錄特徵建立程序專屬的步驟和功能。
seo-title: 建立規則型或已登錄的特徵
solution: Audience Manager
title: 建立規則型或已登錄的特徵
uuid: 4243e09f-1f96-443a-864a-d6 e6918079 fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Rules-Based or Onboarded Traits {#create-rules-based-or-onboarded-traits}

Describes set up steps and features specific to the [!UICONTROL rules-based] and [!UICONTROL onboarded] trait creation process.

<!-- c_tb_rules_traits.xml -->

## Basic Information for Traits {#basics}

In [!UICONTROL Trait Builder], the [!UICONTROL Basic Information] settings let you create new, or edit existing traits. The [!UICONTROL Basic Information] settings are the same for rules-based, onboarded and algorithmic traits. 若要建立新特徵，請提供名稱(避免特殊字元)、資料來源，以及選取儲存資料夾。Other [!UICONTROL Basic Information] fields are optional.

<!-- c_tb_basics.xml -->

### 定義的基本資訊欄位

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 介面元素 </th> 
   <th colname="col2" class="entry"> 解釋 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">名稱</span></b> </td> 
   <td colname="col2"> <p>特徵名稱。必填. </p> <p>最大長度：255個字元。 </p> <p> <p>注意：命名特徵時，請避免這些特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Commas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">虛線 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hyphens </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">標籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">垂直列或垂直號符號 </li> 
      </ul> </p> </p> <p>This helps reduce processing errors when you set up an <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inbound data file transfer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 說明</span></b> </td> 
   <td colname="col2"> 說明特徵或函數的一些字詞。選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件類型</span></b> </td> 
   <td colname="col2"> 將特徵指派給類型或類別，通常是根據函數(例如轉換、網站訪客、合作夥伴、頁面檢視等)。選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料來源</span></b> </td> 
   <td colname="col2"> 將特徵與特定資料提供者關聯。必填. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 整合代碼</span></b> </td> 
   <td colname="col2"> 用於ID、SKU或內部業務程序使用之其他值的欄位。選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 注釋</span></b> </td> 
   <td colname="col2"> 特徵的一般附註。選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 儲存於</span></b> </td> 
   <td colname="col2"> 判斷特徵所屬的儲存資料夾。必填. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料類別</span></b> </td> 
   <td colname="col2"> 根據常用類別分類特徵。 <p>注意：特徵僅屬於單一類別。選填。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Set a Trait Expiration Interval {#set-expiration-interval}

In [!UICONTROL Trait Builder], the [!UICONTROL Advanced Options] lets you set a time-to-live ([!DNL TTL]) interval for a trait. [!DNL TTL] 定義合格訪客留在特徵中的天數(預設為120天)。設為0時，特徵會籍永不過期。

<!-- t_tb_ttl.xml -->

### 設定特徵的TTL

1. Expand the [!UICONTROL Advanced Options] section and enter a number to set a [!DNL TTL] value for the trait.
1. Click **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_贊_ this]
>
>* [區段的即時說明](../../features/traits/segment-ttl-explained.md)

