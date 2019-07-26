---
description: 中繼資料檔案會連結具有您可讀取及瞭解名稱的數值ID。「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。
seo-description: 中繼資料檔案會連結具有您可讀取及瞭解名稱的數值ID。「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。
seo-title: 中繼資料檔案的概述和對應
solution: Audience Manager
title: 中繼資料檔案的概述和對應
uuid: 70df7f11-69c5-4873-a69 d-8f93 f94 e9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

中繼資料檔案會連結具有您可讀取及瞭解名稱的數值ID。「對象最佳化」報表會在各種報表選項功能表中顯示可讀名稱。

## 概述 {#overview}

檢閱中繼資料及其使用方式。中繼資料檔案必須附有資料檔案。中繼資料檔案內容會將資料檔案資訊與報表功能表中相關、人力可讀標籤相符。For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### 中繼資料檔案包含其他資料的資料

中繼資料檔案包含其他類型資料的相關資訊。To help you understand how this works, let’s review how [!DNL Audience Manager] receives data.

During an impression or click event, [!DNL Audience Manager] receives data in an URL string known as an *event call*.

事件呼叫會將資訊組織成已定義索引鍵值組的集合。索引鍵值對中的值包含數值資料。中繼資料檔案包含與每個索引鍵值配對中ID對應的名稱和其他可讀資訊。

### 中繼資料連結ID至可讀名稱

中繼資料檔案是將數值ID連結至可讀名稱的必要項目。As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. 沒有中繼資料檔案，此創意素材在選項選單中會顯示為1234。

不過，格式正確的中繼資料檔案可將此創意連結至實際名稱，例如「廣告商創意A」，這是您可以在報表中讀取並辨識的名稱。

### 何時需要中繼資料檔案

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. 沒有整合，我們仍然可以內嵌資料，但報表選項會顯示數值ID而非描述性名稱。

![](assets/metadata_menu.png)

## File Mappings {#file-mappings}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. 如果您需要使用中繼資料檔案，它會包含與這些索引鍵值配對中值對應的人類可讀資訊。這些索引鍵的值只接受整數(資料類型INT)。Note, *italics* indicates a variable placeholder. 其他元素是常數或索引鍵，不會變更。

>[!IMPORTANT]
>
>If you're using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

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
   <td colname="col2"> <p> <code>d_ adsc= <i>資料來源ID或整合代碼</i></code> </p> <p>這是廣告商的資料來源ID或建立資料來源時提供的整合代碼。See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu= <i>業務單位ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促銷活動 </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign= <i>促銷活動ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_ creative= <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受個不同的機碼值配對： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ change= <i>提供廣告之交換的ID</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site= <i>網站上提供廣告的ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入順序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io= <i>插入順序ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_ src= <i>資料來源ID</i></code> </p> <p>This is the <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic </p> </td> 
   <td colname="col2"> <p> <code>d_ tacic= <i>tatic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直(Vertical) </p> </td> 
   <td colname="col2"> <p> <code>d_ vert= <i>垂直ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

這些金鑰值配對傳入的ID有助於建立中繼資料檔案名稱及其內容。以下章節和插圖說明如何運作。這些範例會建立包含促銷活動中創意的檔案名稱，但其他組合是可能的。

### 活動呼叫

In this example we'll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. 為此，我們需要從事件呼叫擷取創意、促銷活動和資料來源ID。

![](assets/metadata_file_event.png)

### 檔案名稱

檔案名稱是以創意、促銷活動和資料來源ID為基礎。在此情況下，請比較事件呼叫中的關鍵值資料與檔案名稱中的使用方式之間的差異。

在檔案名稱中：

* The data source key changes to `dpid` from `d_src`.

* 創意和促銷活動ID代表類別，而非實際識別碼。

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 檔案內容

在此範例中，檔案內容反映了在事件呼叫上傳入的創意和促銷活動ID。此處的新元素為可讀名稱。Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 檔案傳送

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_贊_ this]
>
>* [觀眾最佳化報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [透過像素呼叫擷取促銷活動點擊資料](../../../integration/media-data-integration/click-data-pixels.md)
>* [透過像素呼叫擷取促銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md)

