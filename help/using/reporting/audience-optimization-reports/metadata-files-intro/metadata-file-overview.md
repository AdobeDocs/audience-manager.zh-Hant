---
description: 元資料檔案將數字ID與可讀取和理解的名稱連結起來。 Audience Optimization報告在各種報告選項菜單中顯示可讀名稱。
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: 中繼資料檔案的概述與對應
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 4%

---

# 中繼資料檔案的概述與對應{#overview-and-mappings-for-metadata-files}

元資料檔案將數字ID與可讀取和理解的名稱連結起來。 Audience Optimization報告在各種報告選項菜單中顯示可讀名稱。

## 概述 {#overview}

對元資料及其使用方式的回顧。 元資料檔案必須伴有資料檔案。 元資料檔案內容將資料檔案資訊與報告菜單中的相關、可人讀標籤匹配。 有關詳細資訊，請參見 [用於Audience Optimization報告的資料檔案和可操作的日誌檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)。

### 元資料檔案包含有關其他資料的資料

元資料檔案包含有關其他類型資料的資訊。 為幫助您瞭解此操作的工作原理，讓我們回顧一下 [!DNL Audience Manager] 接收資料。

在印象或按一下事件期間， [!DNL Audience Manager] 接收URL字串中的資料，該字串稱為 *事件調用*。

事件調用將資訊組織成一組定義的鍵值對。 鍵值對中的值包含數字資料。 元資料檔案包含與每個鍵值對中的ID對應的名稱和其他可讀資訊。

### 元資料將ID連結到可讀名稱

元資料檔案需要將數字ID與可讀名稱綁定。 例如，如果事件調用包含按鍵值對中的創造性ID，如下所示： `d_creative:1234`。 如果沒有元資料檔案，此創作將在選項菜單中顯示為1234。

但是，格式正確的元資料檔案可以將這種創意與「廣告商創意A」等實名聯繫起來，「廣告商創意A」是您可以在報告中閱讀和識別的名稱。

### 何時需要元資料檔案

首先，在事件調用中，當您要使用 [Audience Optimization報告](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

其次，如果要將自己的資料發送給 [!DNL Audience Manager] 或者，如果您希望查看來自其他提供商的報告中的資料，則我們未與之整合。 比如說， [!DNL Audience Manager] 與Google [按兩下「市場活動經理」](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM)。 因為這種關係， [!DNL Audience Manager] 可以將ID與報告選項使用的名稱和說明關聯。 如果沒有整合，我們仍可以接收資料，但報告選項將顯示數字ID而不是描述性名稱。

![元資料菜單影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 檔案映射 {#file-mappings}

下表列出了保存由 [!UICONTROL Audience Optimization] 報告。 如果需要使用元資料檔案，則該檔案將包含與這些鍵值對中的值相對應的人可讀資訊。 這些鍵的值只接受整數（資料類型INT）。 注意， *斜體* 指示變數佔位符。 其他元素是常數或鍵，不更改。

>[!IMPORTANT]
>
>如果你用的 [!UICONTROL Audience Optimization] 報告， *全部* 事件調用中需要這些值。

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告選項 </th> 
   <th colname="col2" class="entry"> 元資料鍵值對 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>廣告商 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>這是建立資料源時提供的廣告商的資料源ID或整合代碼。 請參閱 <a href="../../../features/manage-datasources.md#create-data-source"> 建立資料源</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>業務單元(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促銷活動 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>創意 </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受2個不同的鍵值對： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>這是 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料源</a> 用於提供元資料資訊的平台的ID（例如，DFA、Atlas、GBM、MediaMath等）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>戰術 </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直 </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件調用ID的形狀檔案名、內容和傳遞路徑 {#how-ids-shape-file-names}

這些鍵值對傳入的ID有助於建立元資料檔案名及其內容。 以下各節和圖例演示了此操作的原理。 這些示例生成一個檔案，其中包含市場活動中創作者的名稱，但可能有其他組合。

### 事件調用

在本示例中，我們將建立一個元資料檔案，將創作名稱 [!UICONTROL Audience Optimization] 報告。 為此，我們需要從事件呼叫中提取創意、活動和資料源ID。

![事件調用影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 檔案名稱

檔案名基於創意、活動和資料源ID。 在這種情況下，請比較事件調用中鍵值資料與在檔案名中使用它的方式之間的差異。

在檔案名中：

* 資料源密鑰更改為 `dpid` 從 `d_src`。

* 創意和活動ID表示類別，而不是實際標識符。

![如何生成檔案名](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

請參閱 [元資料檔案的命名約定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。

### 檔案內容

在本示例中，檔案內容反映事件調用中傳遞的創意和活動ID。 此處的新元素是可讀名稱。 處理完後，此檔案中的名稱將作為選項出現在 [!UICONTROL Audience Optimization] 報告。

![元資料檔案的內容](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

請參閱 [元資料檔案的內容格式](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)。

### 檔案傳遞

命名並將資料添加到檔案後，將其發送到由 [!DNL Audience Manager]。 請參閱 [元資料檔案的傳遞方法](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)。

>[!MORELIKETHIS]
>
>* [用於Audience Optimization報告的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [透過像素呼叫擷取行銷活動的點按資料](../../../integration/media-data-integration/click-data-pixels.md)
>* [透過像素呼叫擷取行銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)

