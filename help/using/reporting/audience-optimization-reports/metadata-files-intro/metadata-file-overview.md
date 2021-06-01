---
description: 中繼資料檔案會連結數值ID與您可讀取和了解的名稱。 Audience Optimization報表會在各種報表選項功能表中顯示可讀名稱。
seo-description: 中繼資料檔案會連結數值ID與您可讀取和了解的名稱。 Audience Optimization報表會在各種報表選項功能表中顯示可讀名稱。
seo-title: 中繼資料檔案的概述與對應
solution: Audience Manager
title: 中繼資料檔案的概述與對應
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: 記錄檔
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# 中繼資料檔案的概述與對應{#overview-and-mappings-for-metadata-files}

中繼資料檔案會連結數值ID與您可讀取和了解的名稱。 Audience Optimization報表會在各種報表選項功能表中顯示可讀名稱。

## 概述 {#overview}

中繼資料及其使用方式的審核。 中繼資料檔案必須附有資料檔案。 元資料檔案內容將資料檔案資訊與報告菜單中相關、人類可讀的標籤匹配。 如需詳細資訊，請參閱[資料檔案以取得Audience Optimization報表和可操作的記錄檔](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)。

### 中繼資料檔案包含其他資料的相關資料

中繼資料檔案包含其他資料類型的相關資訊。 為協助您了解其運作方式，我們來檢閱[!DNL Audience Manager]接收資料的方式。

在曝光或點按事件期間， [!DNL Audience Manager]會接收URL字串中的資料，稱為&#x200B;*事件呼叫*。

事件呼叫會將資訊組織成一組已定義的索引鍵值配對。 機碼值組中的值包含數值資料。 中繼資料檔案包含與每個索引鍵/值組中之ID對應的名稱和其他可讀資訊。

### 中繼資料連結ID至可讀名稱

必須將數值ID與可讀名稱系結，才需要中繼資料檔案。 例如，假設事件呼叫包含機碼值組中的創作ID，如下所示：`d_creative:1234`。 若沒有中繼資料檔案，此創意內容會在選項功能表中顯示為1234。

不過，格式正確的中繼資料檔案可將此創意連結回「廣告商創意A」之類的實名稱，「廣告商創意A」是您可在報表中讀取和識別的名稱。

### 何時需要元資料檔案

首先，當您想使用[Audience Optimization報表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)時，事件呼叫中需要中繼資料檔案和下列所有參數。

其次，如果您要將自己的資料發送到[!DNL Audience Manager]，或想查看報表中未整合的其他提供者的資料，則需要元資料檔案。 例如， [!DNL Audience Manager]與Google的[按兩下Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)(DCM)整合。 由於此關係，[!DNL Audience Manager]可將ID與報告選項使用的名稱和說明相關聯。 若沒有整合，我們仍可內嵌資料，但報表選項會顯示數值ID而非描述性名稱。

![中繼資料功能表影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 檔案映射{#file-mappings}

下表列出了保存[!UICONTROL Audience Optimization]報告所使用資料的鍵值值對。 如果您需要使用中繼資料檔案，其中會包含與這些索引鍵值配對中的值相對應的人類看得懂的資訊。 這些鍵的值僅接受整數（資料類型為INT）。 注意， *斜體*&#x200B;表示變數預留位置。 其他元素為常數或索引鍵，不會變更。

>[!IMPORTANT]
>
>如果您使用[!UICONTROL Audience Optimization]報表，事件呼叫中需要這些值的&#x200B;*all*。

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
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>這是廣告商建立資料來源時提供的資料來源ID或整合代碼。 請參閱<a href="../../../features/manage-datasources.md#create-data-source">建立資料源</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>業務單位(BU) </p> </td> 
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
   <td colname="col2"> <p>接受2個不同的索引鍵值配對： </p> 
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
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>這是用於提供中繼資料資訊（例如DFA、Atlas、GBM、MediaMath等）的平台的<a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings">資料來源</a> ID。 </p> </td> 
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

## 事件呼叫ID如何形成檔案名稱、內容和傳送路徑{#how-ids-shape-file-names}

這些索引鍵值配對所傳入的ID有助於建立中繼資料檔案名稱及其內容。 以下章節和圖例說明其運作方式。 這些範例會建立包含行銷活動中創意素材名稱的檔案，但可能有其他組合。

### 事件呼叫

在此範例中，我們將建立中繼資料檔案，將創作名稱帶入[!UICONTROL Audience Optimization]報表。 若要這麼做，我們需要從事件呼叫中擷取創意內容、行銷活動和資料來源ID。

![事件呼叫影像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 檔案名稱

檔案名稱以創作、行銷活動和資料來源ID為基礎。 在此情況下，請比較事件呼叫中索引鍵值資料與在檔案名稱中使用方式之間的差異。

在檔案名中：

* 資料源密鑰從`d_src`更改為`dpid`。

* 創意和行銷活動ID代表類別，而非實際識別碼。

![檔案名如何構建](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

請參閱[中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。

### 檔案內容

在此範例中，檔案內容會反映在事件呼叫中傳入的創作和促銷活動ID。 此處的新元素是可讀名稱。 處理後，此檔案中的名稱會以選項的形式顯示在[!UICONTROL Audience Optimization]報表的「創作」功能表中。

![元資料檔案的內容](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

請參閱[中繼資料檔案的內容格式](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)。

### 檔案傳送

為檔案命名並新增資料後，請將其傳送至[!DNL Audience Manager]提供的Amazon S3儲存目錄。 請參閱[中繼資料檔案的傳送方法](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)。

>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
* [透過像素呼叫擷取行銷活動的點按資料](../../../integration/media-data-integration/click-data-pixels.md)
* [透過像素呼叫擷取行銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)

