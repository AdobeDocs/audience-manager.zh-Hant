---
description: 說明針對規則型和已登入特徵建立程式設定特定步驟和功能。
keywords: create trait;create traits
seo-description: 說明針對規則型和已登入特徵建立程式設定特定步驟和功能。
seo-title: 建立規則型或已上線的特徵
solution: Audience Manager
title: 建立規則型或已上線的特徵
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# 建立 [!UICONTROL Rules-Based] 或 [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

說明建立步驟和特徵的特 [!UICONTROL rules-based] 定 [!UICONTROL onboarded] 功能。

<!-- c_tb_rules_traits.xml -->

## 特徵的基本資訊 {#basics}

在中 [!UICONTROL Trait Builder]，設 [!UICONTROL Basic Information] 定可讓您建立新檔案或編輯現有 [!UICONTROL traits]檔案。 和 [!UICONTROL Basic Information] 的設定 [!UICONTROL rules-based]相 [!UICONTROL onboarded] 同 [!UICONTROL algorithmic traits]。 若要建立新 [!UICONTROL trait]字元，請提供名稱（避免特殊字元）、 [!UICONTROL data source]並選取 [!UICONTROL storage folder]。 其他 [!UICONTROL Basic Information] 欄位為選填欄位。

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

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
   <td colname="col1"> <b><span class="uicontrol"> 名稱</span></b> </td> 
   <td colname="col2"> <p>特徵名稱。 必填. </p> <p>最大長度： 255個字元。 </p> <p> <p>注意： 在命名特徵時，請避免下列特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗號 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">破折號 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">連字型大小 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">標籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">垂直條或管道符號 </li> 
      </ul> </p> </p> <p>這有助於減少設定傳入資料檔案傳輸時 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 的處理錯誤</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 說明</span></b> </td> 
   <td colname="col2"> 用幾個字來說明特徵的目的或功能。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料來源</span></b> </td> 
   <td colname="col2"> 將特徵與特定資料提供者關聯。 必填. <p>使用第一個下拉式選單，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式選單來選擇您的資料來源。</p><p> 如果您未使用Adobe Analytics報表套裝，資料來源類型選擇器會停用，並預設為僅限Audience Manager資料來源。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件類型</span></b> </td> 
   <td colname="col2"> 將特徵指派給類型或類別，通常根據函式（例如轉換、網站訪客、合作夥伴、頁面檢視等）。 選填。 <p> 若要瞭解如何建立轉換特徵，請參閱「在Audience Manager中 <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">建立轉換特徵」影片</a>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 整合程式碼</span></b> </td> 
   <td colname="col2"> ID、SKU或內部業務流程所使用之其他值的欄位。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 意見</span></b> </td> 
   <td colname="col2"> 特徵的一般說明。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 儲存於</span></b> </td> 
   <td colname="col2"> 確定特徵所屬的儲存資料夾。 必填. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料類別</span></b> </td> 
   <td colname="col2"> 根據常見類別對特徵進行分類。 <p>注意：  特徵只屬於單一類別。 選填。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定過 [!UICONTROL Trait] 期間隔 {#set-expiration-interval}

在 [!UICONTROL Trait Builder]中， [!UICONTROL Advanced Options] 可讓您設定的上線時間([!DNL TTL])間隔 [!UICONTROL trait]。 [!DNL TTL] 定義合格訪客在一個時間內的停留 [!UICONTROL trait] 天數（預設為120天）。 設為0時，會籍 [!UICONTROL trait] 永不過期。

<!-- t_tb_ttl.xml -->

### 為 [!UICONTROL trait]

1. 展開 [!UICONTROL Advanced Options] 該部分並輸入數字以設 [!DNL TTL] 置值 [!UICONTROL trait]。
1. 按一下 **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [區段的存留時間說明](../../features/traits/segment-ttl-explained.md)

