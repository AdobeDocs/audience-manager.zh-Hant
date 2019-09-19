---
description: 中繼資料檔案會連結數值ID，其名稱可供您讀取和瞭解。 「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。
seo-description: 中繼資料檔案會連結數值ID，其名稱可供您讀取和瞭解。 「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。
seo-title: 中繼資料檔案的概述與對應
solution: Audience Manager
title: 中繼資料檔案的概述與對應
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 中繼資料檔案的概述與對應{#overview-and-mappings-for-metadata-files}

中繼資料檔案會連結數值ID，其名稱可供您讀取和瞭解。 「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。

## 概述 {#overview}

中繼資料及其使用方式的審查。 中繼資料檔案必須附有資料檔案。 中繼資料檔案內容會比對資料檔案資訊與報表選單中相關、人工可讀的標籤。 如需詳細資訊，請參 [閱讀者最佳化報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)。

### 中繼資料檔案包含其他資料的資料

中繼資料檔案包含其他資料類型的相關資訊。 為協助您瞭解其運作方式，讓我們來檢視資料的 [!DNL Audience Manager] 接收方式。

在曝光或點按事件期間， [!DNL Audience Manager] 會接收URL字串中的資料，稱為事 *件呼叫*。

事件調用將資訊組織成一組定義的鍵值對。 鍵值對中的值包含數值資料。 元資料檔案包含與每個鍵值對中的ID對應的名稱和其它可讀資訊。

### 中繼資料連結ID至可讀名稱

中繼資料檔案必須將數值ID系結至可讀名稱。 例如，假設事件呼叫包含索引鍵值配對中的創作ID，如下所示： `d_creative:1234`。 若沒有中繼資料檔案，此創意素材會在選項選單中顯示為1234。

不過，格式正確的中繼資料檔案可將此創意連結回「廣告商創意A」等實名，而「廣告商創意A」是您可在報表中讀取和辨識的名稱。

### 何時需要中繼資料檔案

首先，當您想要使用對象最佳化報表時，事件呼叫中需要中繼資料檔案及下列所有 [參數](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

其次，如果您要將自己的資料傳送至報表，或是您想在報表中看到未與我們整合的其他供應商的資料，則需要中繼資料檔案。 [!DNL Audience Manager] 例如， [!DNL Audience Manager] 與Google的「連按兩下促銷 [活動管理員](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM)」整合。 由於這種關係， [!DNL Audience Manager] 可將ID與報表選項使用的名稱和說明建立關聯。 如果沒有整合，我們仍可以收錄資料，但報表選項會顯示數值ID，而非描述性名稱。

![](assets/metadata_menu.png)

## 檔案映射 {#file-mappings}

下表列出保存報告所使用資料的鍵值 [!UICONTROL Audience Optimization] 對。 如果您需要使用中繼資料檔案，它會包含與這些索引鍵值配對中的值對應的人類可讀資訊。 這些鍵的值僅接受整數（資料類型INT）。 Note, *italics* indicates a variable placeholder. 其他元素是常數或鍵，不會變更。

>[!IMPORTANT]
>
>如果您使用報表 [!UICONTROL Audience Optimization] ，則 *事件呼叫* 中需要所有這些值。

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報表選項 </th> 
   <th colname="col2" class="entry"> 中繼資料索引鍵值配對 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>廣告商 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc =資 <i>料來源ID或整合代碼</i></code> </p> <p>這是廣告商建立資料來源時提供的資料來源ID或整合代碼。 請參 <a href="../../../features/manage-datasources.md#create-data-source"> 閱建立資料來源</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>業務單位(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu =業 <i>務單元ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促銷活動 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign =促銷 <i>活動ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>創意 </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受2個不同的鍵值對： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange =服 <i>務廣告的交換機ID</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site =服 <i>務於之廣告之網站的ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io =插 <i>入順序ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_src =數 <i>據源ID</i></code> </p> <p>這是提 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 供中繼資料資訊的平台的資料來源</a> ID（例如DFA、Atlas、GBM、MediaMath等）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>戰術 </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直 </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>垂直ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件呼叫ID如何設定檔案名稱、內容和傳送路徑 {#how-ids-shape-file-names}

這些鍵值配對傳遞的ID有助於建立中繼資料檔案名稱及其內容。 以下章節和插圖說明其運作方式。 這些範例會建立包含促銷活動中創意素材名稱的檔案，但可能有其他組合。

### 事件呼叫

在此範例中，我們將建立中繼資料檔案，將創意名稱引入報 [!UICONTROL Audience Optimization] 表。 為此，我們需要從事件呼叫擷取創意、促銷活動和資料來源ID。

![](assets/metadata_file_event.png)

### 檔案名稱

檔案名稱是以創意、促銷活動和資料來源ID為基礎。 在此情況下，請比較事件呼叫中的索引鍵值資料與檔案名稱中使用資料的差異。

在檔案名中：

* 資料來源金鑰會變更為 `dpid` 自 `d_src`。

* 創意和促銷活動ID代表類別，而非實際識別碼。

![](assets/metadata_file_name.png)

請參 [閱中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。

### 檔案內容

在此範例中，檔案內容會反映事件呼叫時傳入的創意和促銷活動ID。 此處的新元素是可讀的名稱。 處理完成後，此檔案中的名稱會顯示為報表的「創意」選單中的選 [!UICONTROL Audience Optimization] 項。

![](assets/metadata_file_contents.png)

請參 [閱中繼資料檔案的內容格式](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)。

### 檔案傳送

在命名並將資料添加到檔案後，將其發送到由提供的Amazon S3儲存目錄 [!DNL Audience Manager]。 請參 [閱中繼資料檔案的傳送方法](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) ，以 [及中繼資料檔案的狀態更新](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md)。

>[!MORE_LIKE_THIS]
>
>* [受眾最佳化報告的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [透過像素呼叫擷取促銷活動點按資料](../../../integration/media-data-integration/click-data-pixels.md)
>* [透過像素呼叫擷取促銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)

