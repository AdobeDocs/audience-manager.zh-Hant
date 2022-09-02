---
description: 可操作的記錄檔可讓您從廣告伺服器記錄檔擷取媒體訊號，以在Audience Manager中建立特徵。 將來自廣告伺服器的曝光數、點按次數和轉換擷取為特徵，而不需附加像素。
keywords: 可操作日誌，alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 可操作的記錄檔
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 869bbe657072255e5ea3f0e68294f8f0e6cc966a
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 3%

---

# 可操作的記錄檔 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔擷取媒體資料，並使用資料建立Audience Manager中的特徵。 將來自廣告伺服器的曝光數、點按次數和轉換擷取為特徵，而不需附加 [像素](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)在本檔案中指出程式碼元素和選項。 如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 簡化從廣告伺服器擷取曝光數、點按和轉換的方式。 使用此資訊進行使用者細分，而無須手動像素媒體將促銷活動屬性傳送至 [!DNL Audience Manager].

## 快速入門 {#getting-started}

若要開始使用 [!UICONTROL Actionable Log Files]，您需要將記錄檔資料匯入 [!DNL Audience Manager]. 下列連結將協助您開始使用：

* 針對 [!UICONTROL Google Campaign Manager] 日誌，請參閱 [將Google Campaign Manager資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和* 聯繫 [!DNL Audience Manager] 顧問。
* 針對 [!UICONTROL Google Ad Manager] (原稱Google DFP)記錄檔，請參閱 [將Google Ad Manager資料檔案匯入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *和* 聯繫 [!DNL Audience Manager] 顧問。
* 如需其他廣告伺服器記錄檔，請參閱 [資料和中繼資料檔案](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和* 聯繫 [!DNL Audience Manager] 顧問。

如果您已將日誌資料導入 [!DNL Audience Manager]，詢問 [!DNL Audience Manager] 顧問或 [客戶服務](https://helpx.adobe.com/tw/contact/enterprise-support.ec.html) 啟用 [!UICONTROL Actionable Log Files] 為了你。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的記錄檔 {#working-with-actionable-log-files}

使用 [!UICONTROL Actionable Log Files]，則廣告伺服器記錄檔的資訊會擷取至 [!DNL Audience Manager] 就像從即時網站互動中擷取資料的方式。 [!DNL Audience Manager] 連線至您的廣告伺服器記錄儲存、剖析記錄中的資訊，並將記錄資料以可操作訊號的形式傳送至我們的 [資料收集伺服器](../../reference/system-components/components-data-collection.md#dcs-pcs).

您仍需設定規則型特徵來擷取可操作的訊號。 請參閱 [Audience Manager使用者介面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或使用 [大量管理工具](../../reference/bulk-management-tools/bulk-create.md). 向下捲動至 [可操作訊號](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 區段，取得可在規則型特徵中使用的所有索引鍵清單。

>[!IMPORTANT]
>
>建議實作 [!UICONTROL Actionable Log Files] *而非*  [像素呼叫](../../integration/media-data-integration/impression-data-pixels.md). 我們不鼓勵使用這兩種選項，因為這會增加特徵的頻率計數。

## 可操作訊號 {#actionable-signals}

訊號為 [最小資料單位](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 可讓您從廣告伺服器記錄檔中，將廣告商、業務單位、創意和促銷活動值擷取到曝光事件、點擊事件和轉換事件中，做為訊號。

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] 支援下列廣告伺服器：
> 
> * [Google行銷活動經理](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud、Flashtalking和Sizmek](#generic-logs-signals)


請記住，若要將此資訊用於建立和劃分受眾，您必須自行設定規則型特徵。

### 來自Google Campaign Manager記錄檔的可操作訊號 {#dcm-logs-signals}

表格列出 [!DNL Google Campaign Manager] 日誌檔案：

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
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>代表Google促銷活動管理員中轉換活動的數值ID。 此欄位對應至Google促銷活動管理員的活動ID。 </p> <p> <p>提示：您可以從Google促銷活動管理員擷取多個或特定的轉換活動。 使用建立特徵 <code> d_conversion = activity ID</code> 來自Google促銷活動管理員的每個轉換活動。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>僅適用於轉換事件。 </p> <p>此欄位對應至Google促銷活動管理員中的轉換ID。 指出從Google促銷活動管理員使用者轉換前的活動。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 用於點按後轉換。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 貼文印象轉換。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 不符合的轉換。 轉換無法與先前的活動相符。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">曝光、點按或轉換事件的UTC日期和時間。 自1970-01-01 00以來以微秒錶示:00:00 UTC。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>廣告商資料來源的整合代碼。 請注意，這與Audience Manager資料來源無關。</p> <p>此欄位會對應至Google促銷活動管理員中的廣告商群組ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>業務單位ID。 此欄位會對應至Google Campaign Manager中的廣告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google促銷活動管理員提供的促銷活動ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>由Google促銷活動管理員提供的創作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 銷售額以美元計，為–6。 用1.000.000乘以1美元。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從Google促銷活動管理員記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以取得曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按一下。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> ，以轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>您用來擷取Google Campaign Manager資料的資料來源ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料來源</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的訊號會擷取至 [!DNL Audience Manager] 即時 `HTTP` 呼叫。 以下範例呼叫包含的轉換事件相關資訊來自 [!DNL Google Campaign Manager]. 呼叫不一定必須包含 *all* 範例呼叫中的訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

對於平均大小 [!DNL Google Campaign Manager] 記錄檔包含200萬行，任何根據可操作訊號建立的特徵，都會在處理記錄後約一小時內實現。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>中提供的事件時間戳記 [!DNL Google Campaign Manager] 記錄會接受並傳遞至 [!UICONTROL Data Collection Servers].
>
>* 如果時間戳記不適用於 [!DNL Google Campaign Manager] 記錄檔，我們會使用 `HTTP` 以事件時間戳記呼叫。
>* 若 [!DNL Google Campaign Manager] 記錄檔包含格式錯誤的時間戳記，我們會忽略整列。


<br> 

### 來自的可操作訊號 [!DNL Google Ad Manager] 記錄 {#ad-manager-logs-signals}

表格列出 [!DNL Google Ad Manager] 日誌檔案：


| 記錄檔中的標題名稱 | 訊號 | 說明 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 傳遞的廣告管理員條列項目的數值ID |
| `OrderId` | `d_orderid` | 包含已傳送條列項目和創意素材的廣告管理員訂單數值ID。 |
| `CreativeId` | `d_creative` | 傳遞的廣告管理員創意內容數值ID。 |
| `-` | `d_event` | 指出事件類型。 Audience Manager會從廣告管理員記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 接受的值為： <br> <ul><li>d_event = imp以表示曝光數。</li><li>d_event =點按次數。</li><li>d_event =轉換和活動的conv。</li></ul> |
| `-` | `d_src` | 您用來擷取廣告管理員資料的資料來源ID。 請參閱 [如何建立資料來源](/help/using/features/manage-datasources.md). |

表格中描述的訊號會以Audience Manager擷取，如即時HTTP呼叫。 以下範例呼叫包含來自Google廣告管理員的轉換事件的資訊。 呼叫不一定必須將所有訊號包含在範例呼叫中。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>中提供的事件時間戳記 [!DNL Google Ad Manager] 記錄會接受並傳遞至 [!UICONTROL Data Collection Servers].
>
>* 如果時間戳記不適用於 [!DNL Google Ad Manager] 記錄檔，我們會使用 `HTTP` 以事件時間戳記呼叫。
>* 若 [!DNL Google Ad Manager] 記錄檔包含格式錯誤的時間戳記，我們會忽略整列。


<br> 

### 來自Adobe Advertising Cloud、Flashtalking和Sizmek廣告伺服器記錄的可操作訊號 {#generic-logs-signals}

首先，您必須將廣告伺服器記錄放入我們的Amazon S3儲存貯體。 若要完成此操作，請閱讀 [Audience Optimization報表的資料檔案和可操作的記錄檔](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和* 聯繫 [!DNL Audience Manager] 顧問。 下表列出廣告伺服器記錄檔中可操作的訊號：

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
   <td colname="col3"> <p>指出轉換是否相符。 選項包括: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 曝光數 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 按一下 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 未歸因或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 曝光、點按或轉換事件的UTC日期和時間。 使用 <code>yyyy-MM-dd HH:mm:ss</code> 格式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>廣告商資料來源的整合代碼。 請注意，此欄位與 <a href="../../features/datasources-list-and-settings.md">Audience Manager資料來源。</a></p></td> 
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
   <td colname="col3"> 購買或其他轉換金額。 資料類型：漂浮。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指出事件類型。 Audience Manager會從記錄檔名稱中讀取事件類型，並將其轉換為可操作的訊號。 請參閱 <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日誌檔案命名約定</a>. </p> <p>接受的值為： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以取得曝光數。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按一下。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> ，以轉換。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用於捕獲日誌資料的資料源的ID。 請參閱 <a href="../../features/manage-datasources.md#create-data-source"> 如何建立資料來源</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表格中描述的訊號會擷取至 [!DNL Audience Manager] 即時 `HTTP` 呼叫。 呼叫不一定必須包含 *all* 範例呼叫中的訊號。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager使用者介面中使用可操作的訊號 {#actionable-signals-in-ui}

您可以在 [訊號搜尋](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 介面。

前往 **對象資料** (1)> **訊號** (2)> **搜尋** (3)並選取 **可操作的記錄檔** (4)過濾器。

![UI中可操作的訊號](/help/using/integration/assets/alf-in-signals.png)

若要使用您的可操作訊號建立規則型特徵，請選取 **可操作的記錄檔** (1)，選取您要作為特徵規則使用的可操作訊號(2)，然後按 **從選取的訊號建立特徵** (3)。

![從訊號建立特徵](/help/using/integration/assets/alf-create-trait.png)


## 使用個案 {#use-cases}

實施的一個好處 [!UICONTROL Actionable Log Files] 是要套用的選項 [使用頻率](../../features/segments/recency-and-frequency.md) 控制項 [規則型特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 包含可操作的訊號。 舉例來說，這可讓您以頻率上限在媒體行銷活動中，顯示使用者特定創意內容的次數。 閱讀 [即時跨裝置隱藏功能](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) 來學習如何做。 其他使用案例包括：

### 重新定位使用者

重新定位看過創意123但未點按或轉換的使用者，並顯示創意456。 執行動作:

1. 建立特徵以擷取看到創意內容的使用者。 假設您為特徵命名 [!DNL Creative Trait 123]. 使用特徵規則：

   `d_creative == 123 AND d_event == imp`

2. 建立特徵以擷取點按或轉換的使用者。 假設你給這個命名 [!DNL Click and Converter]. 使用特徵規則：

   `d_event == click OR d_event=conv`

3. 建立區段以填入看到創意123但未點按或轉換的使用者。 為其命名 [!DNL Retarget Users] 和使用區段規則：

   `Creative Trait 123 AND NOT Click and Converter`

4. 對應區段 [!DNL Retarget Users] 使用creative 456到目的地並定位目的地中的使用者。

### 在「Audience Optimization報表」或Audience Lab中使用Google Campaign Manager Floodlight活動

[Floodlight標籤](https://support.google.com/dcm/partner/answer/4293719?hl=en) 讓廣告商可追蹤使用者轉換。 使用 [!UICONTROL Actionable Log Files]，您可以追蹤 [!DNL Google Campaign Manager] 轉換 [Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 或 [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 建立特徵並使用下列特徵規則來從廣告伺服器記錄檔擷取轉換：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager中建立特徵時 [!UICONTROL UI]，選取 [!UICONTROL Conversion] 作為 [!UICONTROL Event Type].

2. 建立特徵後，系統就會開始針對 [!UICONTROL Audience Optimization Reports] 和 [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [將Google Campaign Manager資料檔案匯入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受眾最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

