---
description: 說明以規則為基礎並已上線的特徵建立程式的特定設定步驟和功能。
keywords: 建立特徵；建立特徵
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: 建立規則型或已上線的特徵
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 2%

---

# 建立[!UICONTROL Rules-Based]或[!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

說明特定於[!UICONTROL rules-based]和[!UICONTROL onboarded]特徵建立程式的設定步驟和功能。

<!-- c_tb_rules_traits.xml -->

## 特徵的基本資訊 {#basics}

在[!UICONTROL Trait Builder]中，[!UICONTROL Basic Information]設定可讓您建立新專案，或編輯現有的[!UICONTROL traits]。 [!UICONTROL Basic Information]、[!UICONTROL rules-based]和[!UICONTROL onboarded]的[!UICONTROL algorithmic traits]設定相同。 若要建立新的[!UICONTROL trait]，請提供名稱（避免特殊字元）、[!UICONTROL data source]並選取[!UICONTROL storage folder]。 其他[!UICONTROL Basic Information]欄位是選用欄位。

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
   <td colname="col1"> <b><span class="uicontrol">名稱</span></b> </td> 
   <td colname="col2"> <p>特徵名稱。 必填。 </p> <p>長度上限： 255個字元。 </p> <p> <p>注意：為特徵命名時，請避免使用下列特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗號 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">破折號 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">連字型大小 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">索引標籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">垂直條或垂直線符號 </li> 
      </ul> </p> </p> <p>當您設定<a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">傳入資料檔案傳輸</a>時，這有助於減少處理錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 說明</span></b> </td> 
   <td colname="col2"> 提供幾個字詞來協助說明特徵的用途或功能。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">資料Source</span></b> </td> 
   <td colname="col2"> 將特徵與特定資料提供者建立關聯。 必填。 <p>使用第一個下拉式功能表，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間篩選。 然後，使用第二個下拉式選單來選擇資料來源。</p><p> 如果您未使用Adobe Analytics報表套裝，資料來源型別選擇器會停用，並僅預設為Audience Manager資料來源。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol">事件型別</span></b> </td> 
   <td colname="col2"> 將特徵指派給型別或類別，通常會根據功能（例如轉換、網站訪客、合作夥伴、頁面檢視等）。 選填。 <p> 若要瞭解如何建立轉換特徵，請參閱<a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html?lang=zh-Hant">在Audience Manager中建立轉換特徵影片</a>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">整合代碼</span></b> </td> 
   <td colname="col2"> 供內部業務流程使用的ID、SKU或其他值的欄位。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">個註解</span></b> </td> 
   <td colname="col2"> 特徵的一般注意事項。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">存放區位於</span></b> </td> 
   <td colname="col2"> 決定特徵所屬的儲存資料夾。 必填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">資料類別</span></b> </td> 
   <td colname="col2"> 根據常見類別來分類特徵。 <p>注意：特徵僅屬於單一類別。 選填。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定[!UICONTROL Trait]過期時間間隔 {#set-expiration-interval}

在[!UICONTROL Trait Builder]中，[!UICONTROL Advanced Options]可讓您設定[!DNL TTL]的存留時間([!UICONTROL trait])間隔。 [!DNL TTL]定義合格訪客在[!UICONTROL trait]內停留的天數（預設為120天）。 設定為0時，[!UICONTROL trait]成員資格永不過期。

<!-- t_tb_ttl.xml -->

### 設定[!UICONTROL trait]的TTL

1. 展開[!UICONTROL Advanced Options]區段並輸入數字以設定[!DNL TTL]的[!UICONTROL trait]值。
1. 按一下 **[!UICONTROL Save]**。

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [區段存留時間說明](../../features/traits/segment-ttl-explained.md)
