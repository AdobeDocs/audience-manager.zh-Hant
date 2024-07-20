---
description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以便在Audience Manager中建立特徵。 將廣告伺服器的曝光數、點按數和轉換數擷取為特徵，而不需要附加畫素。
keywords: 可操作的記錄， alf， ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files]可讓您從廣告伺服器記錄檔擷取媒體資料，並使用資料在Audience Manager中建立特徵。 將廣告伺服器的曝光、點按和轉換擷取為特徵，而不需附加[畫素](../../integration/media-data-integration/impression-data-pixels.md)。

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)檔案中會指示程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files]可簡化您從廣告伺服器擷取曝光數、點按數和轉換次數的方式。 使用此資訊進行使用者細分，而不需手動將畫素媒體傳送行銷活動屬性至[!DNL Audience Manager]。

## 入門 {#getting-started}

若要開始使用[!UICONTROL Actionable Log Files]，您必須將記錄檔資料匯入[!DNL Audience Manager]。 以下連結將幫助您快速入門：

* 如需[!UICONTROL Google Campaign Manager]記錄檔，請參閱[將Google Campaign Manager資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *及*，請聯絡您的[!DNL Audience Manager]顧問。
* 如需[!UICONTROL Google Ad Manager] (先前為Google DFP)記錄檔，請參閱[將Google Ad Manager資料檔案匯入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *及*，請聯絡您的[!DNL Audience Manager]顧問。
* 如需其他廣告伺服器記錄檔，請參閱[資料和中繼資料檔案](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和*，請聯絡您的[!DNL Audience Manager]顧問。

如果您已將記錄檔資料匯入[!DNL Audience Manager]，請要求您的[!DNL Audience Manager]顧問或[客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html)為您啟用[!UICONTROL Actionable Log Files]。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的記錄檔 {#working-with-actionable-log-files}

透過[!UICONTROL Actionable Log Files]，廣告伺服器記錄檔中的資訊會以[!DNL Audience Manager]擷取，其方式與從即時網站互動擷取資料的方式相同。 [!DNL Audience Manager]會連線至您的廣告伺服器記錄儲存體、剖析記錄中的資訊，並將記錄資料作為可操作的訊號傳送至我們的[資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要設定規則型特徵，以擷取可操作的訊號。 瞭解如何在[Audience Manager使用者介面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)中設定規則型特徵，或使用我們的[大量管理工具](../../reference/bulk-management-tools/bulk-create.md)。 向下捲動至[可操作的訊號](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)區段，以取得您可在規則型特徵中使用的所有索引鍵清單。

>[!IMPORTANT]
>
>我們建議實作[!UICONTROL Actionable Log Files] *，而非* [畫素呼叫](../../integration/media-data-integration/impression-data-pixels.md)。 我們不建議同時使用這兩個選項，因為這會增加特徵的頻率計數。

## 可操作訊號 {#actionable-signals}

訊號是[!DNL Audience Manager]中的[最小資料單位](../../reference/signal-trait-segment.md)。 [!UICONTROL Actionable Log Files]可讓您從廣告伺服器記錄檔擷取廣告商、業務單位、創意和促銷活動在曝光事件、點選事件和轉換事件中的值，做為訊號。

>[!IMPORTANT]
>
>下列廣告伺服器支援[!UICONTROL Actionable Log Files]：
> <br>
>
> * [Google行銷活動管理員](#dcm-logs-signals)
> * [Google廣告管理員](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud、Flashtalking和Sizmek](#generic-logs-signals)

請記住，若要將此資訊用於對象建立和細分，您必須自行設定規則型特徵。

### Google Campaign Manager記錄檔中的可操作訊號 {#dcm-logs-signals}

此表格列出來自[!DNL Google Campaign Manager]記錄檔的可操作訊號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 記錄檔中的標題名稱 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>代表Google Campaign Manager中轉換活動的數值ID。 此欄位對應至Google Campaign Manager中的活動ID。 </p> <p> <p>提示：您可以從Google Campaign Manager擷取多個或特定的轉換活動。 從Google Campaign Manager使用<code> d_conversion = activity ID</code>為每個轉換活動建立特徵。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>此欄位對應至Google Campaign Manager中的轉換ID。 表示從Google Campaign Manager進行使用者轉換前的活動。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code>點按後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code>用於貼文印象轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code>用於不相符的轉換。 此轉換不符合先前的活動。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">曝光、點按或轉換事件的UTC日期和時間。 以自1970-01-01 00:00:00 UTC以來的微秒表示。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>廣告商資料來源的整合程式碼。 請注意，這與Audience Manager資料來源無關。</p> <p>此欄位對應至Google Campaign Manager中的廣告商群組ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。 此欄位對應至Google Campaign Manager的廣告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager提供的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google Campaign Manager提供的創作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 以USD為單位的銷售金額，乘以–6的冪。 乘以1.000.000即可看到金額。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>表示事件型別。 Audience Manager會從Google Campaign Manager記錄檔名稱中讀取事件型別，並將其轉換為可操作的訊號。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code>的曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code>點按。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code>進行轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>您用來擷取Google Campaign Manager資料的資料來源ID。 請參閱<a href="../../features/manage-datasources.md#create-data-source">如何建立資料Source</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

資料表中描述的訊號會在[!DNL Audience Manager]中擷取，就像即時`HTTP`呼叫一樣。 以下範例呼叫包含來自[!DNL Google Campaign Manager]的轉換事件資訊。 呼叫不一定要在範例呼叫中包含&#x200B;*所有*&#x200B;訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

對於平均大小為[!DNL Google Campaign Manager]且每行有200萬的記錄檔，從可操作訊號建立的任何特徵會在我們處理記錄後約一小時內實現。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager]記錄檔中提供的事件時間戳記將被接受，並傳遞給[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Campaign Manager]記錄檔中的資料列沒有時間戳記，我們會使用`HTTP`呼叫的時間做為事件時間戳記。
>* 如果[!DNL Google Campaign Manager]記錄檔中的資料列包含格式錯誤的時間戳記，我們會忽略整列。

<br> 

### 來自[!DNL Google Ad Manager]記錄檔的可操作訊號 {#ad-manager-logs-signals}

此表格列出來自[!DNL Google Ad Manager]記錄檔的可操作訊號：


| 記錄檔中的標題名稱 | 訊號 | 說明 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 已遞送廣告管理員條列專案的數值ID |
| `OrderId` | `d_orderid` | 包含已傳遞條列專案和創意的廣告管理員訂單數值ID。 |
| `CreativeId` | `d_creative` | 已傳送的廣告管理員創意的數值ID。 |
| `-` | `d_event` | 表示事件型別。 Audience Manager會從Ad Manager記錄檔名稱中讀取事件型別，並將其轉換為可操作的訊號。 接受的值為： <br> <ul><li>d_event =曝光的imp。</li><li>d_event =點選次數。</li><li>d_event =轉換和活動的conv。</li></ul> |
| `-` | `d_src` | 您用來擷取Ad Manager資料的資料來源ID。 請參閱[如何建立資料Source](/help/using/features/manage-datasources.md)。 |

此表格中說明的訊號會以Audience Manager擷取，就像即時HTTP呼叫一樣。 以下範例呼叫包含來自Google Ad Manager的轉換事件資訊。 呼叫不一定要在範例呼叫中包含所有訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager]記錄檔中提供的事件時間戳記將被接受，並傳遞給[!UICONTROL Data Collection Servers]。
>
>
>* 如果[!DNL Google Ad Manager]記錄檔中的資料列沒有時間戳記，我們會使用`HTTP`呼叫的時間做為事件時間戳記。
>* 如果[!DNL Google Ad Manager]記錄檔中的資料列包含格式錯誤的時間戳記，我們會忽略整列。

<br> 

### 來自Adobe Advertising Cloud、Flashtalking和Sizmek廣告伺服器記錄的可操作訊號 {#generic-logs-signals}

首先，您必須將廣告伺服器記錄檔存放在我們的Amazon S3貯體中。 若要完成此操作，請閱讀Audience Optimization報告的[資料檔案和可操作的記錄檔](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和*，請聯絡您的[!DNL Audience Manager]顧問。 此表格列出來自廣告伺服器記錄檔的可操作訊號：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 記錄檔中的標題名稱 </th> 
   <th colname="col2" class="entry"> 訊號 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
   <th colname="col4" class="entry"> 範例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>指出是否符合轉換。 選項包括: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code>印象 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code>點按 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code>未歸因或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 曝光、點按或轉換事件的UTC日期和時間。 使用<code>yyyy-MM-dd HH:mm:ss</code>格式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>廣告商資料來源的整合程式碼。 請注意，此欄位與<a href="../../features/datasources-list-and-settings.md">Audience Manager資料來源無關。</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>記錄檔中的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>記錄檔中的創作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 購買或其他轉換金額。 資料型別： Float。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>表示事件型別。 Audience Manager會從記錄檔名稱讀取事件型別，並將其轉換為可操作的訊號。 請參閱<a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">記錄檔命名慣例</a>。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code>的曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code>點按。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code>進行轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>您用來擷取記錄檔資料的資料來源ID。 請參閱<a href="../../features/manage-datasources.md#create-data-source">如何建立資料Source</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

資料表中描述的訊號會在[!DNL Audience Manager]中擷取，就像即時`HTTP`呼叫一樣。 呼叫不一定要在範例呼叫中包含&#x200B;*所有*&#x200B;訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager使用者介面中使用可操作的訊號 {#actionable-signals-in-ui}

您可以在[訊號搜尋](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)介面中檢視您傳入的可操作訊號。

移至&#x200B;**對象資料** (1) > **訊號** (2) > **搜尋** (3)，並選取&#x200B;**可操作的記錄檔** (4)篩選器。

UI中的![可操作的訊號](/help/using/integration/assets/alf-in-signals.png)

若要使用可操作的訊號建立規則型特徵，請選取&#x200B;**可操作的記錄檔** (1)，選取要當作特徵規則使用的可操作訊號(2)，然後按&#x200B;**從選取的訊號建立特徵** (3)。

![從訊號建立特徵](/help/using/integration/assets/alf-create-trait.png)


## 使用個案 {#use-cases}

實作[!UICONTROL Actionable Log Files]的一個優點是，可以將[造訪間隔和頻率](../../features/segments/recency-and-frequency.md)控制項套用至任何包含可操作訊號的[規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)。 舉例來說，這可讓您在媒體行銷活動中，將使用者顯示特定創意內容的次數設為頻率上限。 閱讀[即時跨裝置隱藏](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)以瞭解如何執行此動作。 其他使用案例包括：

### 重新鎖定使用者

重新鎖定看到創意123但未點按或轉換的使用者，並向他們顯示創意456。 執行這個動作：

1. 建立特徵來擷取看過該創意的使用者。 假設您命名特徵[!DNL Creative Trait 123]。 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

2. 建立特徵來擷取按一下或轉換的使用者。 假設您將此專案命名為[!DNL Click and Converter]。 使用特徵規則：

   `d_event == click OR d_event=conv`

3. 建立區段來填入看到創意123但未點按或轉換的使用者。 將其命名為[!DNL Retarget Users]並使用區段規則：

   `Creative Trait 123 AND NOT Click and Converter`

4. 將區段[!DNL Retarget Users]對應到目的地，並使用creative 456定位目的地中的使用者。

### 在Audience Optimization報表或Audience Lab中使用Google Campaign Manager Floodlight活動

[Floodlight標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en)可讓廣告商追蹤使用者轉換。 透過[!UICONTROL Actionable Log Files]，您可以在[Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)或[Audience Lab](../../features/audience-lab/audience-lab.md)中追蹤[!DNL Google Campaign Manager]轉換：

1. 建立特徵並使用以下特徵規則從廣告伺服器記錄檔中擷取轉換：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager[!UICONTROL UI]中建立特徵時，請選取[!UICONTROL Conversion]做為[!UICONTROL Event Type]。

2. 一旦您建立特徵後，轉換就會開始在[!UICONTROL Audience Optimization Reports]和[!UICONTROL Audience Lab]中報告。

>[!MORELIKETHIS]
>
>* [將Google Campaign Manager資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受眾最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
