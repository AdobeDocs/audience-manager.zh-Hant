---
description: 說明規則型和已上線特徵建立程式的專屬設定步驟和功能。
keywords: 建立特徵；建立特徵
seo-description: 說明規則型和已上線特徵建立程式的專屬設定步驟和功能。
seo-title: 建立規則型或已上線的特徵
solution: Audience Manager
title: 建立規則型或已上線的特徵
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: 特徵
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 8%

---

# 建立 [!UICONTROL Rules-Based] 或 [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

說明特徵建立程式[!UICONTROL rules-based]和[!UICONTROL onboarded]的特定步驟和功能設定。

<!-- c_tb_rules_traits.xml -->

## 特徵的基本資訊 {#basics}

在[!UICONTROL Trait Builder]中， [!UICONTROL Basic Information]設定可讓您建立新設定或編輯現有的[!UICONTROL traits]。 [!UICONTROL rules-based]、[!UICONTROL onboarded]和[!UICONTROL algorithmic traits]的[!UICONTROL Basic Information]設定相同。 若要建立新的[!UICONTROL trait]，請提供名稱（避免特殊字元）、[!UICONTROL data source]，然後選取[!UICONTROL storage folder]。 其他[!UICONTROL Basic Information]欄位為選用。

<!-- c_tb_basics.xml -->

![建立特徵](assets/create-trait.png)

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
   <td colname="col2"> <p>特徵名稱。 必填. </p> <p>最大長度：255個字元。 </p> <p> <p>注意：命名特徵時，請避免下列特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗號 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">虛線 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">連字型大小 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">標籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">垂直條或管符號 </li> 
      </ul> </p> </p> <p>這有助於減少設定<a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">傳入資料檔案傳輸</a>時的處理錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 說明</span></b> </td> 
   <td colname="col2"> 幾個字可協助描述特徵的用途或功能。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料來源</span></b> </td> 
   <td colname="col2"> 將特徵與特定資料提供者建立關聯。 必填. <p>使用第一個下拉式功能表，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式功能表來選擇您的資料來源。</p><p> 如果您未使用Adobe Analytics報表套裝，資料來源類型選取器會停用，且預設為僅Audience Manager資料來源。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件類型</span></b> </td> 
   <td colname="col2"> 將特徵指派給類型或類別，通常會根據函式（例如轉換、網站訪客、合作夥伴、頁面檢視等）。 選填。 <p> 若要了解如何建立轉換特徵，請參閱<a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">在Audience Manager影片中建立轉換特徵</a>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 整合程式碼</span></b> </td> 
   <td colname="col2"> 您內部業務流程所使用的ID、SKU或其他值的欄位。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 意見</span></b> </td> 
   <td colname="col2"> 特徵的一般附註。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 儲存於</span></b> </td> 
   <td colname="col2"> 決定特徵屬於哪個儲存資料夾。 必填. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料類別</span></b> </td> 
   <td colname="col2"> 根據常見類別來分類特徵。 <p>注意： 特徵只屬於單一類別。 選填。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定[!UICONTROL Trait]過期間隔{#set-expiration-interval}

在[!UICONTROL Trait Builder]中， [!UICONTROL Advanced Options]可讓您設定[!UICONTROL trait]的存留時間([!DNL TTL])間隔。 [!DNL TTL] 會定義合格訪客在內停留的 [!UICONTROL trait] 天數（120天為預設值）。設為0時，[!UICONTROL trait]成員資格永遠不會過期。

<!-- t_tb_ttl.xml -->

### 設定[!UICONTROL trait]的TTL

1. 展開[!UICONTROL Advanced Options]部分並輸入數字以設定[!UICONTROL trait]的[!DNL TTL]值。
1. 按一下 **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [區段存留時間說明](../../features/traits/segment-ttl-explained.md)

