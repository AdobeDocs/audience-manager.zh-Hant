---
description: 描述設定特定於基於規則和已載入特徵建立流程的步驟和特徵。
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
source-wordcount: '360'
ht-degree: 7%

---

# 建立 [!UICONTROL Rules-Based] 或 [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

描述特定於 [!UICONTROL rules-based] 和 [!UICONTROL onboarded] 特徵創造過程。

<!-- c_tb_rules_traits.xml -->

## 特徵的基本資訊 {#basics}

在 [!UICONTROL Trait Builder]，也請參見Wiki頁。 [!UICONTROL Basic Information] 設定，您可以新建或編輯現有 [!UICONTROL traits]。 的 [!UICONTROL Basic Information] 設定與 [!UICONTROL rules-based]。 [!UICONTROL onboarded] 和 [!UICONTROL algorithmic traits]。 建立新 [!UICONTROL trait]，提供名稱（避免特殊字元）, [!UICONTROL data source]，然後選擇 [!UICONTROL storage folder]。 其他 [!UICONTROL Basic Information] 欄位是可選的。

<!-- c_tb_basics.xml -->

![特質](assets/create-trait.png)

### 已定義基本資訊欄位

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
   <td colname="col2"> <p>特徵名。 必填. </p> <p>最大長度：255個字元。 </p> <p> <p>注：在命名特徵時，請避免這些特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗號 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">短划線 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">連字元 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">頁籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">竪條或管符號 </li> 
      </ul> </p> </p> <p>這有助於減少在設定 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站資料檔案傳輸</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 說明</span></b> </td> 
   <td colname="col2"> 用幾個詞來描述特質的目的或功能。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料來源</span></b> </td> 
   <td colname="col2"> 將特性與特定資料提供程式關聯。 必填. <p>使用第一個下拉菜單在Audience Manager資料源、Adobe Analytics報告套件或兩者之間進行篩選。 然後，使用第二個下拉菜單選擇資料源。</p><p> 如果未使用Adobe Analytics報表套件，則資料源類型選擇器將被禁用，並且預設為僅Audience Manager資料源。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件類型</span></b> </td> 
   <td colname="col2"> 將特性指定給類型或類別，通常根據函式（如轉換、站點訪問者、合作夥伴、頁面視圖等）。 選填。 <p> 要瞭解如何建立轉換特性，請參閱 <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">在Audience Manager視頻中建立轉換特徵</a>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 整合程式碼</span></b> </td> 
   <td colname="col2"> 內部業務流程使用的ID、SKU或其他值的欄位。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 意見</span></b> </td> 
   <td colname="col2"> 關於一個特質的一般說明。 選填。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 儲存於</span></b> </td> 
   <td colname="col2"> 確定特性屬於哪個儲存資料夾。 必填. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料類別</span></b> </td> 
   <td colname="col2"> 將特徵按照通常理解的類別分類。 <p>注：特徵只屬於單個類別。 選填。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定 [!UICONTROL Trait] 到期間隔 {#set-expiration-interval}

在 [!UICONTROL Trait Builder]，也請參見Wiki頁。 [!UICONTROL Advanced Options] 讓您設定生命週期([!DNL TTL])間隔 [!UICONTROL trait]。 [!DNL TTL] 定義合格訪問者在 [!UICONTROL trait] （預設為120天）。 設定為0時， [!UICONTROL trait] 成員資格永遠不會過期。

<!-- t_tb_ttl.xml -->

### 為 [!UICONTROL trait]

1. 展開 [!UICONTROL Advanced Options] 並輸入數字以設定 [!DNL TTL] 值 [!UICONTROL trait]。
1. 按一下 **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [已解釋段的生存時間](../../features/traits/segment-ttl-explained.md)

